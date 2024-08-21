Java
# let palavra;
let cor;

function setup() {
  createCanvas(400, 400);
  cor = color(random(0,255), random(0,255), random(0,255));

  palavra = palavraAleatoria();
  
}

function palavraAleatoria() {
  
  let palavras = ["amor", "carinho", "atenção", "lealdade", "respeito", "compreenção"];
  
  return random(palavras);
}

function inicializaCores() {
  background("white");
  fill(cor);
  textSize(64);
  textAlign(CENTER, CENTER);
}

function palavraParcial(minimo, maximo) {
  let quantidade = map(mouseX, minimo, maximo, 1, palavra.length);
  let parcial = palavra.substring(0, quantidade);
  return parcial;
}

function draw() {
  
  inicializaCores();

  let parcial = palavraParcial(0, width);
    
  text(parcial, 200, 200);
  
  if (mouseIsPressed){
    cor = color(random(0,255), random(0,255), random(0,255), random(0,100));
  }
}

<!DOCTYPE html>
<html lang="en">
  <head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.8.0/p5.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.8.0/addons/p5.sound.min.js"></script>
    <link rel="stylesheet" type="text/css" href="style.css">
    <meta charset="utf-8" />

  </head>
  <body>
    <main>
    </main>
    <script src="sketch.js"></script>
  </body>
</html>

html, body {
  margin: 0;
  padding: 0;
}
canvas {
  display: block;
}
