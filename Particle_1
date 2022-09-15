// Daniel Shiffman
// https://thecodingtrain.com

// Particle System using ES6 Higher Order Array Functions
// Video: https://youtu.be/m9bRVQ_-DXY

// Original Challenge: CC78 - Simple Particle System
// https://youtu.be/UcdigVaIYAk

let particles;

function setup() {
  createCanvas(600, 400);

  particles = new Array(100).fill().map((p) => new Particle());
}

function draw() {
  background(0);
  for (let i = 0; i < 5; i++) {
    const p = new Particle();
    particles.push(p);
  }

  particles.sort((a, b) => a.col - b.col);

  particles.forEach((p) => p.update());
  particles.forEach((p) => p.show());

  // for (const particle of particles) {
  //   particle.update()
  //   particle.show()
  // }

  particles = particles.filter((p) => !p.finished());

  // const sumx = particles.reduce((x, p) => x + p.x, 0);
  // const sumy = particles.reduce((y, p) => y + p.y, 0);

  // const centerX = sumx / particles.length;
  // const centerY = sumy / particles.length;

  const sumV = particles.reduce((v, p) => v.add(p.x, p.y), createVector(0, 0));
  sumV.div(particles.length);

  fill(255, 0, 0);
  ellipse(sumV.x, sumV.y, 24, 24);
}
