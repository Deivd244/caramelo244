let arvores = [];

function setup() {
  createCanvas(800, 600);
  background(135, 206, 235); // Céu azul
  
}

function draw() {
  desenharCenario();

  // Desenhar todas as árvores
  for (let arvore of arvores) {
    desenharArvore(arvore.x, arvore.y);
  }
}

function mousePressed() {
  // Adiciona uma nova árvore na posição do mouse
  if (mouseY > height / 2) { // só planta na grama
    arvores.push({x: mouseX, y: mouseY});
  }
}

function desenharCenario() {
  // Céu
  background(135, 206, 235);

  // Grama(marrom)
  noStroke();
  fill(34, 139, 34);
  rect(0, height / 2, width, height / 2);

  // Texto
  fill(255);
  textSize(24);
  textAlign(CENTER, TOP);
  text("Clique na grama para plantar uma árvore ", width / 2, 10);
}

function desenharArvore(x, y) {
  // Tronco
  fill(139, 69, 19);
  rect(x - 5, y - 40, 10, 40);

  // Copa
  fill(34, 139, 34);
  ellipse(x, y - 50, 40, 40);
}
