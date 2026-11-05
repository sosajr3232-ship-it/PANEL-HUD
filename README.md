
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>OneState RP Panel</title>
<style>
body {
 background:#10131c;
 color:white;
 font-family:Arial;
 margin:0;
}
header {
 background:#20283a;
 padding:20px;
 text-align:center;
 color:orange;
}
nav {
 display:flex;
 flex-wrap:wrap;
 justify-content:center;
 gap:8px;
 padding:12px;
}
button {
 background:#303c52;
 color:white;
 border:1px solid orange;
 padding:12px;
 border-radius:8px;
}
main {padding:15px}
section {
 display:none;
 background:#20283a;
 padding:18px;
 border-radius:12px;
}
section.active {display:block}
h2 {color:orange}
input {
 padding:12px;
 width:90%;
 margin:8px;
 border-radius:6px;
 border:0;
}
.card {
 background:#303c52;
 padding:14px;
 margin:10px 0;
 border-radius:8px;
}
</style>
</head>
<body>

<header>
<h1>ONESTATE RP</h1>
<p>PERSONAL PANEL 2.0</p>
</header>

<nav>
<button onclick="openTab('inicio')">Inicio</button>
<button onclick="openTab('personaje')">Personaje</button>
<button onclick="openTab('admin')">Admin</button>
<button onclick="openTab('ajustes')">Ajustes</button>
</nav>

<main>

<section id="inicio" class="active">
<h2>Panel principal</h2>
<div class="card">Bienvenido a OneState RP</div>
<div class="card">Panel visual independiente</div>
<button onclick="alert('Panel activado')">Activar panel</button>
</section>

<section id="personaje">
<h2>Estadísticas</h2>
<div class="card">
Nombre: <span id="nombre">Jugador</span>
</div>
<div class="card">
Nivel: <span id="nivel">1</span>
</div>
<input id="nuevo" placeholder="Nombre del personaje">
<button onclick="guardar()">Guardar nombre</button>
</section>

<section id="admin">
<h2>Administración</h2>
<div class="card">Configuración visual</div>
<input placeholder="Nombre del servidor">
<button onclick="alert('Configuración guardada')">Guardar</button>
</section>

<section id="ajustes">
<h2>Personalización</h2>
<button onclick="color()">Cambiar color</button>
<button onclick="reset()">Restablecer panel</button>
</section>

</main>

<script>
function openTab(id) {
 document.querySelectorAll('section')
 .forEach(s=>s.classList.remove('active'));
 document.getElementById(id).classList.add('active');
}

function guardar() {
 let n=document.getElementById('nuevo').value;
 if(n.trim()) {
 document.getElementById('nombre').textContent=n;
 localStorage.setItem('nombre',n);
 }
}

function color() {
 document.body.style.background='#182b40';
}

function reset() {
 localStorage.clear();
 location.reload();
}

let saved=localStorage.getItem('nombre');
if(saved) document.getElementById('nombre').textContent=saved;
</script>

</body>
</html>
