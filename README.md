let amigos = [];

function agregarAmigo() {
  const nombre = document.getElementById('nombreInput').value;

  if (nombre === "") {
    alert("Espacio vacío, por favor ingrese un nombre");
  } else {
    amigos.push(nombre);
    document.getElementById('nombreInput').value = ""; 
    actualizarListaAmigos(); 
  }
}

function actualizarListaAmigos() {
  const lista = document.getElementById('listaAmigos');

  lista.innerHTML = "";

 
  for (let i = 0; i < amigos.length; i++) {
    const li = document.createElement('li');
    li.textContent = amigos[i]; 
    lista.appendChild(li); 
  }
}

function sorteoAmigo() {
  if (amigos.length === 0) {
    alert("No hay amigos disponibles para el sorteo.");
    return;
  }

  const indiceAleatorio = Math.floor(Math.random() * amigos.length);

  const amigoSorteado = amigos[indiceAleatorio];

  }
  document.getElementById('resultadoSorteo').innerHTML = `El amigo sorteado es: ${amigoSorteado}`; 
