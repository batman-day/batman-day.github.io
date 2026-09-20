<!doctype html>
<html lang="es">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>¡HAPPY BATMAN DAY CARIÑO!</title>
<link rel="icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Ctext y='.9em' font-size='90'%3E%F0%9F%A6%87%3C/text%3E%3C/svg%3E">
<link href="https://fonts.googleapis.com/css2?family=Yellowtail&display=swap" rel="stylesheet">
<style>
html, body { height: 100%; margin: 0; }
body {
  background: #050912;
  overflow: hidden;
  color: #b9c7dd;
  font-family: system-ui, sans-serif;
  -webkit-tap-highlight-color: transparent;
  -webkit-user-select: none;
  user-select: none;
}

#cielo {
  position: fixed;
  inset: 0;
  background:
    radial-gradient(120% 55% at 50% 100%, rgba(96,130,184,.42), rgba(96,130,184,0) 72%),
    linear-gradient(#060b16, #0e1a2d 45%, #22354f);
}

#nubes {
  position: fixed;
  top: 0;
  left: 0;
  animation: pasar 240s linear infinite;
}
@keyframes pasar { to { transform: translateX(-50%); } }

#escena {
  position: fixed;
  inset: 0;
  width: 100%;
  height: 100%;
}

#vineta {
  position: fixed;
  inset: 0;
  pointer-events: none;
  background: radial-gradient(ellipse at 50% 45%, transparent 55%, rgba(0,0,0,.55));
}

.titila { animation: titila 5s steps(1,end) infinite; }
@keyframes titila {
  0%, 46%, 100% { opacity: .9; }
  48% { opacity: .1; }
  52% { opacity: .9; }
  54% { opacity: .1; }
  60% { opacity: .9; }
}

.antena { animation: antena 2.6s ease-in-out infinite; }
@keyframes antena {
  0%, 60%, 100% { opacity: .15; }
  30% { opacity: 1; }
}

#faro { cursor: pointer; }
#faro .lente { fill: #22324b; transition: fill .35s; }
#faro .resplandor, #faro .piso { opacity: 0; transition: opacity .5s; }
.on #faro .lente { fill: #fffbe2; }
.on #faro .resplandor, .on #faro .piso { opacity: 1; }

#faro .onda {
  fill: none;
  stroke: #f5dc8f;
  stroke-width: 2;
  transform-box: fill-box;
  transform-origin: center;
  animation: onda 2.6s ease-out infinite;
}
@keyframes onda {
  from { transform: scale(.75); opacity: .75; }
  to { transform: scale(1.7); opacity: 0; }
}
.tocado #faro .onda { display: none; }

#haz { opacity: 0; pointer-events: none; transition: opacity .6s; }
.on #haz {
  opacity: 1;
  pointer-events: auto;
  cursor: pointer;
  animation: prender 1.1s linear both;
}
@keyframes prender {
  0% { opacity: 0 }
  10% { opacity: .9 }
  18% { opacity: .12 }
  32% { opacity: .85 }
  42% { opacity: .25 }
  58%, 100% { opacity: 1 }
}

#zoom { transform-origin: 0 0; }
.on #zoom { animation: crecer 1s cubic-bezier(.2,.8,.2,1) both; }
@keyframes crecer {
  from { transform: scale(.55) }
  to { transform: scale(1) }
}

#murcielago, #recado { opacity: 0; transition: opacity .3s; }
.on #murcielago { opacity: .92; transition: opacity .9s .55s; }
.on #recado { opacity: .92; transition: opacity 1s 1.15s; }

#pista {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 24px;
  margin: 0;
  text-align: center;
  font-size: 15px;
  text-shadow: 0 1px 8px rgba(0,0,0,.8);
  pointer-events: none;
  transition: opacity .6s;
}
.tocado #pista { opacity: 0; }

</style>
</head>
<body>

<div id="cielo"></div>
<canvas id="nubes"></canvas>

<svg id="escena" viewBox="0 0 1600 900" preserveAspectRatio="xMidYMax slice" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="nieblaLejos" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0" stop-color="#2a3f5e" stop-opacity="0"/>
      <stop offset="1" stop-color="#2a3f5e" stop-opacity=".75"/>
    </linearGradient>
    <linearGradient id="nieblaMedio" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0" stop-color="#1c2d47" stop-opacity="0"/>
      <stop offset="1" stop-color="#1c2d47" stop-opacity=".6"/>
    </linearGradient>
    <linearGradient id="nieblaPiso" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0" stop-color="#3a5479" stop-opacity="0"/>
      <stop offset="1" stop-color="#3a5479" stop-opacity=".28"/>
    </linearGradient>

    <linearGradient id="cono" gradientUnits="userSpaceOnUse" x1="0" y1="584" x2="0" y2="250">
      <stop offset="0" stop-color="#fff6c8" stop-opacity=".78"/>
      <stop offset=".6" stop-color="#fff3b8" stop-opacity=".38"/>
      <stop offset="1" stop-color="#fff3b8" stop-opacity=".26"/>
    </linearGradient>
    <radialGradient id="disco">
      <stop offset="0" stop-color="#fffbe0" stop-opacity=".97"/>
      <stop offset=".62" stop-color="#fff5c2" stop-opacity=".9"/>
      <stop offset=".9" stop-color="#fff0a8" stop-opacity=".78"/>
      <stop offset="1" stop-color="#fff0a8" stop-opacity="0"/>
    </radialGradient>
    <radialGradient id="halo">
      <stop offset="0" stop-color="#fff3b8" stop-opacity=".32"/>
      <stop offset="1" stop-color="#fff3b8" stop-opacity="0"/>
    </radialGradient>
    <radialGradient id="brillo">
      <stop offset="0" stop-color="#fff6c8" stop-opacity=".85"/>
      <stop offset="1" stop-color="#fff6c8" stop-opacity="0"/>
    </radialGradient>

    <filter id="suave" x="-20%" y="-5%" width="140%" height="110%">
      <feGaussianBlur stdDeviation="3.5"/>
    </filter>
    <filter id="apenas" x="-10%" y="-10%" width="120%" height="120%">
      <feGaussianBlur stdDeviation=".8"/>
    </filter>

    <path id="ala" d="M-0.5,-27 L5,-34 L10,-51 L18,-32
      C48,-44 92,-54 132,-40
      Q126,-8 104,12
      Q92,-3 76,-2
      Q71,14 59,27
      Q52,11 40,7
      Q36,20 25,30
      Q20,11 14,4
      Q12,18 -0.5,30 Z"/>
  </defs>

  <g id="lejos"></g>
  <rect x="0" y="400" width="1600" height="500" fill="url(#nieblaLejos)"/>
  <g id="medio"></g>
  <rect x="0" y="480" width="1600" height="420" fill="url(#nieblaMedio)"/>

  <g id="haz">
    <polygon points="760,584 605,250 995,250 840,584" fill="url(#cono)" filter="url(#suave)"/>
    <g id="proyeccion" transform="translate(800,250)">
      <g id="zoom">
      <ellipse rx="330" ry="230" fill="url(#halo)"/>
      <ellipse rx="210" ry="140" fill="url(#disco)"/>
      <g id="murcielago" fill="#0f1725" filter="url(#apenas)" transform="translate(0,-30) scale(.68)">
        <use href="#ala"/>
        <use href="#ala" transform="scale(-1,1)"/>
      </g>
      <text id="recado" y="60" text-anchor="middle" fill="#0f1725" filter="url(#apenas)"
            font-family="Yellowtail, 'Brush Script MT', cursive" font-size="40">Te amo mi amorcito</text>
      </g>
    </g>
  </g>

  <g id="cerca"></g>
  <rect x="0" y="640" width="1600" height="260" fill="url(#nieblaPiso)"/>

  <g id="faro" transform="translate(800,690) scale(1.4)">
    <ellipse class="piso" cy="-1" rx="52" ry="3.5" fill="#fff3b8" fill-opacity=".16"/>
    <circle cy="-48" r="60" fill="transparent"/>
    <circle class="onda" cy="-76" r="38"/>
    <rect x="-36" y="-8" width="72" height="8" fill="#0a111d"/>
    <path d="M-16,-8 L-11,-32 L11,-32 L16,-8 Z" fill="#0c1422"/>
    <rect x="-38" y="-56" width="6" height="22" rx="2" fill="#0c1422"/>
    <rect x="32" y="-56" width="6" height="22" rx="2" fill="#0c1422"/>
    <rect x="-33" y="-76" width="66" height="46" rx="4" fill="#111b2e" stroke="#2f4364" stroke-width="1.5"/>
    <path d="M-33,-64 H33 M-33,-52 H33 M-33,-40 H33" stroke="#1c2b45" stroke-width="2"/>
    <ellipse cy="-76" rx="35" ry="10" fill="#0c1422" stroke="#2f4364" stroke-width="1.5"/>
    <ellipse class="lente" cy="-76" rx="29" ry="7.5"/>
    <circle class="resplandor" cy="-78" r="64" fill="url(#brillo)"/>
  </g>
</svg>

<div id="vineta"></div>
<p id="pista">Toca el faro cariño</p>

<script>
var s = 1;
function rnd() {
  s = Math.sin(s) * 43758.5453;
  return s - Math.floor(s);
}

var SVG = "http://www.w3.org/2000/svg";
function nodo(tipo, attrs, papa) {
  var e = document.createElementNS(SVG, tipo);
  for (var k in attrs) e.setAttribute(k, attrs[k]);
  papa.appendChild(e);
  return e;
}

var capas = {
  lejos: { color:'#16263d', semilla:19, min:34, max:78,  alto:[340,560], luz:.07, vw:4, vh:6, sx:5, sy:7,  op:.55, torres:true },
  medio: { color:'#0e1a2e', semilla:44, min:46, max:104, alto:[450,650], luz:.15, vw:5, vh:7, sx:6, sy:9,  op:.8,  torres:true },
  cerca: { color:'#070d19', semilla:8,  min:62, max:138, alto:[545,760], luz:.11, vw:6, vh:8, sx:8, sy:11, op:.9,  torres:false }
};

function caja(x, y, an, al) {
  return 'M' + x + ',' + y + 'h' + an + 'v' + al + 'h' + (-an) + 'z';
}

function armarCapa(nombre) {
  var c = capas[nombre];
  var g = document.getElementById(nombre);
  var siluetas = '', calidas = '', frias = '';
  var parpadeo = [], antenas = [];
  s = c.semilla;

  function edificio(x, an, techo, plano) {
    var d = caja(x, techo, an, 920 - techo);
    var tipo = plano ? 'plano' : remate();

    if (tipo === 'aguja') {
      var base = an * (.42 + rnd() * .18);
      var h = 46 + rnd() * 84;
      var cx = x + an / 2;
      d += 'M' + (cx - base/2) + ',' + (techo+1) + 'L' + cx + ',' + (techo-h) + 'L' + (cx + base/2) + ',' + (techo+1) + 'z';
      if (c.torres && rnd() < .7) antenas.push([cx, techo - h + 2]);
    } else if (tipo === 'antena') {
      var tw = 5 + rnd() * 6, th = 34 + rnd() * 70;
      var tx = x + an * (.25 + rnd() * .5);
      d += caja(tx, techo - th, tw, th + 2);
      d += caja(tx + tw/2 - .7, techo - th - 22, 1.4, 24);
      if (c.torres) antenas.push([tx + tw/2, techo - th - 22]);
    } else if (tipo === 'escalon') {
      var an2 = an * (.5 + rnd() * .2), h2 = 16 + rnd() * 34;
      d += caja(x + (an - an2)/2, techo - h2, an2, h2 + 2);
    } else if (tipo === 'corona') {
      var n = Math.max(3, Math.floor(an / 14)), w = an / n;
      for (var i = 0; i < n; i += 2) d += caja(x + i*w, techo - 7, w, 8);
    } else if (tipo === 'gotico') {
      var p = 9 + rnd() * 6;
      d += 'M' + x + ',' + (techo+1) + 'L' + (x + p/2) + ',' + (techo - 30 - rnd()*20) + 'L' + (x+p) + ',' + (techo+1) + 'z';
      d += 'M' + (x+an-p) + ',' + (techo+1) + 'L' + (x+an-p/2) + ',' + (techo - 30 - rnd()*20) + 'L' + (x+an) + ',' + (techo+1) + 'z';
    }
    siluetas += d;

    var cols = Math.max(1, Math.floor((an - 8) / c.sx));
    var filas = Math.floor((900 - techo - 30) / c.sy);
    var ox = x + (an - cols*c.sx)/2 + (c.sx - c.vw)/2;
    for (var col = 0; col < cols; col++) {
      for (var f = 0; f < filas; f++) {
        if (rnd() > c.luz) continue;
        var wx = ox + col*c.sx, wy = techo + 8 + f*c.sy;
        if (wy > 860) continue;
        if (rnd() < .12) frias += caja(wx, wy, c.vw, c.vh);
        else calidas += caja(wx, wy, c.vw, c.vh);
        if (rnd() < .012 && nombre !== 'lejos') parpadeo.push([wx, wy]);
      }
    }
  }

  function remate() {
    var v = rnd();
    if (v < .26) return 'aguja';
    if (v < .36) return 'antena';
    if (v < .46) return 'escalon';
    if (v < .56) return 'corona';
    if (v < .62) return 'gotico';
    return 'plano';
  }

  function fila(desde, hasta, techoDe) {
    var x = desde;
    while (x < hasta) {
      var an = c.min + rnd() * (c.max - c.min);
      if (x + an > hasta - 30) an = hasta - x;
      if (an < 20) break;
      edificio(x, an, techoDe(x + an/2), false);
      x += an - rnd() * 6;
    }
  }

  function techo(cx) {
    var d = Math.abs(cx - 800);
    if (nombre === 'cerca' && d < 330) return 585 + rnd() * 55;
    if (nombre !== 'cerca' && d < 300) return (nombre === 'lejos' ? 565 : 605) + rnd() * 55;
    return c.alto[0] + rnd() * (c.alto[1] - c.alto[0]);
  }

  if (nombre === 'cerca') {
    fila(-40, 680, techo);
    edificio(680, 240, 690, true);
    fila(920, 1640, techo);
  } else {
    fila(-40, 1640, techo);
  }

  nodo('path', { d: siluetas, fill: c.color }, g);
  if (calidas) nodo('path', { d: calidas, fill: '#f3c969', 'fill-opacity': c.op }, g);
  if (frias) nodo('path', { d: frias, fill: '#bcd6ff', 'fill-opacity': c.op * .8 }, g);

  parpadeo.forEach(function (p, i) {
    var r = nodo('rect', { x:p[0], y:p[1], width:c.vw, height:c.vh, fill:'#f3c969', 'class':'titila' }, g);
    r.style.animationDelay = -(i * 1.37 % 5).toFixed(2) + 's';
    r.style.animationDuration = (4 + i % 4) + 's';
  });

  antenas.forEach(function (p, i) {
    var a = nodo('circle', { cx:p[0], cy:p[1], r:1.8, fill:'#ff5a4d', 'class':'antena' }, g);
    a.style.animationDelay = (-i * .7).toFixed(2) + 's';
  });
}

armarCapa('lejos');
armarCapa('medio');
armarCapa('cerca');

var lienzo = document.getElementById('nubes');
function pintarNubes() {
  var an = Math.max(window.innerWidth, 700);
  var al = Math.round(window.innerHeight * .8);
  lienzo.width = an * 2;
  lienzo.height = al;
  lienzo.style.width = (an * 2) + 'px';
  lienzo.style.height = al + 'px';

  var ctx = lienzo.getContext('2d');
  s = 77;
  for (var i = 0; i < 80; i++) {
    var x = rnd() * an;
    var y = al * (.03 + rnd() * .82);
    var r = (30 + rnd() * 90) * (al / 300);
    var oscura = rnd() < .38;
    var tono = oscura ? '8,13,24' : '128,152,188';
    var a = oscura ? .10 + rnd() * .10 : .05 + rnd() * .07;
    for (var k = 0; k < 2; k++) {
      ctx.save();
      ctx.translate(x + k * an, y);
      ctx.scale(2.6, 1);
      var g = ctx.createRadialGradient(0, 0, 0, 0, 0, r);
      g.addColorStop(0, 'rgba(' + tono + ',' + a + ')');
      g.addColorStop(1, 'rgba(' + tono + ',0)');
      ctx.fillStyle = g;
      ctx.beginPath();
      ctx.arc(0, 0, r, 0, 6.2832);
      ctx.fill();
      ctx.restore();
    }
  }
}
pintarNubes();

var espera;
window.addEventListener('resize', function () {
  clearTimeout(espera);
  espera = setTimeout(pintarNubes, 150);
});

var prendido = false;
function prender() {
  prendido = !prendido;
  document.body.classList.toggle('on', prendido);
  document.body.classList.add('tocado');
}

document.getElementById('faro').addEventListener('click', prender);
document.getElementById('haz').addEventListener('click', prender);
</script>
</body>
</html>
