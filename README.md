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
