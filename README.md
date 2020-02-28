# Directional-Light
let defaultVal = `let dirX = (mouseX / width - 0.5) * 2;
let dirY = (mouseY / height - 0.5) * 2;
directionalLight(0, 30, 250, -dirX, -dirY, -1);
ambientLight(15);
background(0);
noStroke();
push();
translate(-55,-55);
sphere(60);
pop();
translate(60, 60);
rotateY(radians(45));
rotateX(radians(45));
box(70);`;

//cool demo

//background(0);
//
//let p = createVector(150*Math.cos(frameCount/20),75*Math.cos(frameCount/20),110*Math.sin(frameCount/20));
//
//orbitControl();
//pointLight(255,255,180,p);
//ambientLight(30);
//stroke(20);
//sphere(100);
//noStroke();
//translate(p);
//ambientLight(255);
//sphere(5);


let textarea = document.querySelector('textarea');

function setup() {
  createCanvas(textarea.clientHeight,textarea.clientHeight,WEBGL);
  textarea.value = defaultVal;
}

function draw() {
  clear();

  try {
    eval(textarea.value);
    document.querySelector('#errormsg').innerHTML = "<br>";
  }
  catch (err) {
    document.querySelector('#errormsg').innerHTML = err;
  }
}
