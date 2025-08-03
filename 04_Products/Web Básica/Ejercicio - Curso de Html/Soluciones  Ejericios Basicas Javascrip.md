// 1. Medir el tiempo de renderizado
document.addEventListener('DOMContentLoaded', () => {
    const timeElapsed = performance.now() / 1000;
    console.log(`Tiempo de renderizado: ${timeElapsed.toFixed(2)} segundos`);
});

// 2. Trackear el mouse y cambiar fondo al hacer clic
document.addEventListener('mousemove', (event) => {
    document.getElementById('mouse-coords').textContent = `X: ${event.clientX}, Y: ${event.clientY}`;
});
document.addEventListener('click', () => {
    document.body.style.backgroundColor = `hsl(${Math.random() * 360}, 100%, 75%)`;
});

// 3. Temporizador en tiempo real
let timer = 0;
let interval = setInterval(() => {
    document.getElementById('timer').textContent = `Tiempo: ${timer++}s`;
}, 1000);

// 4. Detectar teclas presionadas
document.addEventListener('keydown', (event) => {
    document.getElementById('key-info').textContent = `Tecla presionada: ${event.key}`;
});

// 5. Contador de clics en un botón
document.getElementById('click-btn').addEventListener('click', () => {
    let count = parseInt(document.getElementById('click-count').textContent) || 0;
    document.getElementById('click-count').textContent = count + 1;
});

// 6. Animación de desplazamiento
window.addEventListener('scroll', () => {
    let scrollPercentage = (window.scrollY / (document.body.scrollHeight - window.innerHeight)) * 100;
    document.body.style.backgroundColor = `hsl(${scrollPercentage}, 100%, 75%)`;
});

// 7. Implementar modo oscuro
document.getElementById('dark-mode-btn').addEventListener('click', () => {
    document.body.classList.toggle('dark-mode');
    localStorage.setItem('darkMode', document.body.classList.contains('dark-mode'));
});

// 8. Contador regresivo
function countdown(targetDate) {
    setInterval(() => {
        let now = new Date().getTime();
        let difference = targetDate - now;
        let seconds = Math.floor((difference % (1000 * 60)) / 1000);
        document.getElementById('countdown').textContent = `Tiempo restante: ${seconds} segundos`;
    }, 1000);
}

// 9. Dibujar en un canvas
const canvas = document.getElementById('drawing-canvas');
const ctx = canvas.getContext('2d');
let drawing = false;
canvas.addEventListener('mousedown', () => drawing = true);
canvas.addEventListener('mouseup', () => drawing = false);
canvas.addEventListener('mousemove', (event) => {
    if (!drawing) return;
    ctx.lineTo(event.clientX, event.clientY);
    ctx.stroke();
});

// 10. Arrastrar y soltar
document.getElementById('draggable').addEventListener('dragstart', (event) => {
    event.dataTransfer.setData('text/plain', event.target.id);
});
document.getElementById('drop-zone').addEventListener('dragover', (event) => {
    event.preventDefault();
});
document.getElementById('drop-zone').addEventListener('drop', (event) => {
    event.preventDefault();
    const data = event.dataTransfer.getData('text');
    event.target.appendChild(document.getElementById(data));
});
