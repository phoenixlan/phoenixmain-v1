<script>
import { onMount } from "svelte";
import * as twgl from "twgl.js";


    let canvas;
    onMount(() => {
        const gl = canvas.getContext('webgl');
        gl.disable(gl.CULL_FACE);

        gl.enable(gl.BLEND);
        gl.blendFunc(gl.SRC_ALPHA, gl.ONE_MINUS_SRC_ALPHA);

        gl.enable(gl.DEPTH_TEST);
        gl.depthFunc(gl.LESS);

    const vs = `
attribute vec4 position;
uniform mat4 u_matrix;

void main() {
   gl_Position = u_matrix * position;
}
`;
    const fs = `
precision mediump float;
uniform vec4 color;
void main() {
  gl_FragColor = color;
}
`;

    const vs2 = `
attribute vec4 position;
attribute vec2 texcoord;

uniform mat4 u_matrix;

varying vec2 v_texcoord;

void main() {
   gl_Position = u_matrix * position;
   v_texcoord = texcoord;
}
`;
    const fs2 = `
precision mediump float;
varying vec2 v_texcoord;
uniform sampler2D u_texture;
void main() {
  gl_FragColor = texture2D(u_texture, v_texcoord);
}
`;

"use strict";

    const m4 = twgl.m4;
    // compiles shaders, links program, looks up locations
    const cubeProgramInfo = twgl.createProgramInfo(gl, [vs, fs]);
    const texProgramInfo = twgl.createProgramInfo(gl, [vs2, fs2]);

    const positionList = [];

    const zmax = 20;
    for(let x = -100; x < 100; x++) {
        positionList.push(x);
        positionList.push(0);
        positionList.push(0);

        positionList.push(x);
        positionList.push(0);
        positionList.push(zmax);
    }

    for(let z = 0; z <= zmax; z++) {
        positionList.push(-100);
        positionList.push(0);
        positionList.push(z);

        positionList.push(100);
        positionList.push(0);
        positionList.push(z);
    }

    const cubeArrays = {
        position: positionList
    };

    const octahedronArrays = {
        position: [
            0, 1, 0,

            1, 0, -1,
            1, 0, 1,
            -1, 0, 1,
            -1, 0, -1,

            0, -1, 0
        ],
        indices: [
            0, 1, 2,
            0, 2, 3,
            0, 3, 4,
            0, 4, 1,
            5, 1, 2,
            5, 2, 3,
            5, 3, 4,
            5, 4, 1
        ]
    };

    const quadArrays = {
        position: {
        numComponents: 2,
        data: [
            0, 0,
            1, 0,
            0, 1,
            0, 1,
            1, 0,
            1, 1,
        ],
        },
        texcoord: [
        0, 0,
        1, 0,
        0, 1,
        0, 1,
        1, 0,
        1, 1,
        ],
    };
    // calls gl.createBuffer, gl.bindBuffer, gl.bufferData for each array
    const cubeBufferInfo = twgl.createBufferInfoFromArrays(gl, cubeArrays);
    const quadBufferInfo = twgl.createBufferInfoFromArrays(gl, quadArrays);
    const octahedronBufferInfo = twgl.createBufferInfoFromArrays(gl, octahedronArrays);

    // using mips only works if we make texture power of 2 (in WebGL1)
    // WebGL2 doesn't have that limit
    const fbWidth = 512;
    const fbHeight = 512;
    // calls gl.createTexture, gl.bindTexture, gl.texImage2D, gl.texParameteri
    // calls gl.createRenderbuffer, gl.bindRenderbuffer, gl.renderbufferStorage
    // calls gl.createFramebuffer, gl.bindFramebuffer, gl.framebufferTexture2D, gl.framebufferRenderbuffer
    const fbInfo = twgl.createFramebufferInfo(gl, [
        { format: gl.RGBA, min: gl.LINEAR_MIPMAP_LINEAR, wrap: gl.CLAMP_TO_EDGE, },
        { format: gl.DEPTH_STENCIL, },
    ], fbWidth, fbHeight);

    // extract the created texture
    const cubeTexture = fbInfo.attachments[0];


    const lowResFBWidth = 256;
    const lowResFBHeight = 256;
    const lowResFBInfo = twgl.createFramebufferInfo(gl, [
        { format: gl.RGBA, mag: gl.NEAREST, wrap: gl.CLAMP_TO_EDGE, }
    ], lowResFBWidth, lowResFBHeight);

    // get the texture what was just created.
    const lowResTexture = lowResFBInfo.attachments[0];

    function drawTexture(gl, texture, srcWidth, srcHeight, dstWidth, dstHeight) {
        const dstRatio = dstWidth / dstHeight;
        let drawWidth = dstWidth;
        let drawHeight = dstHeight;
        if(dstRatio > 1) {
            drawHeight = srcHeight * drawWidth / srcWidth;
        } else {
            drawWidth =  srcWidth * drawHeight / srcHeight;
        }
        const m = m4.ortho(0, dstWidth, 0, dstHeight, -1, 1);
        m4.translate(m, [
            (dstWidth - drawWidth) / 2, 
            (dstHeight - drawHeight) / 2,
            0], m);
        m4.scale(m, [drawWidth, drawHeight, 1], m);

        gl.useProgram(texProgramInfo.program);
        // calls gl.bindBuffer, gl.enableVertexAttribArray, gl.vertexAttribPointer
        twgl.setBuffersAndAttributes(gl, texProgramInfo, quadBufferInfo);
        // calls gl.uniformXXX, gl.activeTexture, gl.bindTexture
        twgl.setUniforms(texProgramInfo, {
        u_matrix: m,
        u_texture: texture,
        });
        // calls gl.drawArrays or gl.drawElements
        twgl.drawBufferInfo(gl, quadBufferInfo);
    }

    function render(time) {
        time *= 0.001;
        twgl.resizeCanvasToDisplaySize(gl.canvas);

        // draw cube to the texture

        // calls gl.bindFramebuffer, gl.viewport
        twgl.bindFramebufferInfo(gl, fbInfo);

        const fov = 30 * Math.PI / 180;
        const aspect = fbWidth / fbHeight;
        const zNear = 0.5;
        const zFar = 40;
        {

            const projection = m4.perspective(fov, aspect, zNear, zFar);
            gl.clearColor(0x56/256, 0x1e/256, 0x80/256, 1.0);
            gl.clear(gl.COLOR_BUFFER_BIT | gl.DEPTH_BUFFER_BIT);

            const eye = [0, 1, 0];
            const target = [0, 0, 10];
            const up = [0, 1, 0];

            const camera = m4.lookAt(eye, target, up);
            const view = m4.inverse(camera);
            const viewProjection = m4.multiply(projection, view);
            //const world = m4.rotationY(time);
            const world = m4.translation([(time*0.2)%1, 0, 0])

            gl.useProgram(cubeProgramInfo.program);

            // calls gl.bindBuffer, gl.enableVertexAttribArray, gl.vertexAttribPointer
            twgl.setBuffersAndAttributes(gl, cubeProgramInfo, cubeBufferInfo);
            // calls gl.uniformXXX
            twgl.setUniforms(cubeProgramInfo, {
                u_matrix: m4.multiply(viewProjection, world),
                color: [1, 1, 1, 1]
            });
            // calls gl.drawArrays or gl.drawElements
            twgl.drawBufferInfo(gl, cubeBufferInfo, gl.LINES);
        }
        // Draw the octahedrons
        const octahedronColors = [
            [0x14/256, 0xc2/256, 0xd7/256, 0.7],
            [0xF4/256, 0x51/256, 0xa0/256, 0.7]
        ];
        const octahedronVectors = [
            twgl.v3.create(1, 0.5, -3),
            twgl.v3.create(-2, -1, 3)
        ];
        for(let i = 0; i < 2; i++)
        {
            const projection = m4.perspective(fov, aspect, 5, 100);
            const eye = [0, 0, -10];
            const target = [0, 0, 0];
            const up = [0, 1, 0];

            const camera = m4.lookAt(eye, target, up);
            const rotationAxis = twgl.v3.add(octahedronVectors[i], twgl.v3.create(
                Math.sin(time*0.2)*2, 
                Math.cos(time*0.3), 
                Math.sin(time*0.15)*3
            ));
            const model = m4.axisRotation(twgl.v3.normalize(rotationAxis), (time+i)*1);
            const view = m4.inverse(camera);
            const modelViewProjection = m4.multiply(projection, m4.multiply(view, model) );
            //const world = m4.rotationY(time);

            // calls gl.bindBuffer, gl.enableVertexAttribArray, gl.vertexAttribPointer
            twgl.setBuffersAndAttributes(gl, cubeProgramInfo, octahedronBufferInfo);
            // calls gl.uniformXXX
            twgl.setUniforms(cubeProgramInfo, {
                u_matrix: modelViewProjection,
                color: octahedronColors[i]            
            });
            // calls gl.drawArrays or gl.drawElements
            twgl.drawBufferInfo(gl, octahedronBufferInfo, gl.TRIANGLES);
        }

        // first generate mips
        gl.bindTexture(gl.TEXTURE_2D, cubeTexture);
        gl.generateMipmap(gl.TEXTURE_2D);

        // draw the texture to the lowResTexture.

        // calls gl.bindFramebuffer, gl.viewport 
        twgl.bindFramebufferInfo(gl, lowResFBInfo);
        drawTexture(gl, cubeTexture, fbWidth, fbHeight, lowResFBWidth, lowResFBHeight);

        // draw the low-res texture to the canvas

        // calls gl.bindFramebuffer, gl.viewport 
        twgl.bindFramebufferInfo(gl, null);
        gl.clearColor(0x56/256, 0x1e/256, 0x80/256, 1.0);
        gl.clear(gl.COLOR_BUFFER_BIT | gl.DEPTH_BUFFER_BIT);
        drawTexture(gl, lowResTexture, lowResFBWidth, lowResFBHeight, gl.canvas.clientWidth, gl.canvas.clientHeight);

        requestAnimationFrame(render);
    }
    requestAnimationFrame(render);


});


</script>

<canvas bind:this={canvas}>

</canvas>

<style>
    canvas {
        position:absolute;
        top: 0px;
        left: 0px;
        width: 100%;
        height: 100%;
    }
</style>