<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Estadística interactiva | Medidas y rango</title>
<style>
:root{--ink:#17233b;--muted:#53627a;--paper:#f5f7fb;--card:#fff;--blue:#2457c5;--teal:#087e8b;--gold:#f3b33d;--line:#dce3ef;--good:#18794e;--bad:#b42318}
*{box-sizing:border-box}body{margin:0;background:var(--paper);color:var(--ink);font-family:system-ui,-apple-system,Segoe UI,Roboto,Arial,sans-serif;line-height:1.6}
header{background:linear-gradient(135deg,#172e67,#2457c5 60%,#087e8b);color:#fff;padding:44px 20px 38px}
.hero{max-width:1050px;margin:auto}.eyebrow{text-transform:uppercase;letter-spacing:.12em;font-size:.78rem;font-weight:800;opacity:.85}
h1{font-size:clamp(2rem,5vw,3.4rem);line-height:1.1;margin:.45rem 0 1rem}.hero p{max-width:760px;font-size:1.1rem;color:#eef4ff}
nav{display:flex;gap:9px;flex-wrap:wrap;margin-top:24px}nav a{color:white;text-decoration:none;border:1px solid #ffffff66;border-radius:999px;padding:7px 13px;font-size:.9rem}nav a:hover{background:#ffffff22}
main{max-width:1050px;margin:28px auto;padding:0 18px 50px}.section{margin:30px 0;scroll-margin-top:15px}.section h2{font-size:1.65rem;margin:0 0 12px}.section-intro{color:var(--muted);margin-top:-5px}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(225px,1fr));gap:15px}.card{background:var(--card);border:1px solid var(--line);border-radius:18px;padding:20px;box-shadow:0 5px 18px #1a31500a}.card h3{margin:.1rem 0 .6rem;font-size:1.12rem}.symbol{display:inline-grid;place-items:center;width:42px;height:42px;border-radius:12px;background:#e8efff;color:var(--blue);font-size:1.2rem;font-weight:800;margin-bottom:8px}
.formula{background:#eef4ff;border-left:4px solid var(--blue);padding:12px 15px;border-radius:8px;font-weight:650;margin:12px 0}.data{display:flex;gap:8px;flex-wrap:wrap;margin:12px 0}.chip{background:#e9f4f5;color:#075c65;border-radius:9px;padding:7px 11px;font-weight:750}
button{border:0;background:var(--blue);color:white;border-radius:10px;padding:10px 15px;font-weight:750;cursor:pointer;font-size:.95rem}button:hover{filter:brightness(1.08)}button.secondary{background:#e9eef8;color:var(--ink)}button.teal{background:var(--teal)}
input[type=number],input[type=text]{width:100%;padding:10px 11px;border:1px solid #c8d2e2;border-radius:9px;font:inherit;color:var(--ink);background:#fff}label{display:block;font-weight:650;margin:9px 0 4px}.interactive{background:#fff;border:1px solid var(--line);border-radius:18px;padding:20px}
.row{display:grid;grid-template-columns:repeat(auto-fit,minmax(145px,1fr));gap:12px}.result{background:#f2f6ff;border-radius:12px;padding:12px}.result small{display:block;color:var(--muted)}.result strong{font-size:1.3rem}
.feedback{margin-top:12px;padding:12px;border-radius:10px;display:none}.feedback.show{display:block}.feedback.good{background:#e8f6ee;color:#145b39}.feedback.bad{background:#fff0ee;color:#8c2119}
details{background:white;border:1px solid var(--line);border-radius:12px;padding:13px 16px;margin:10px 0}summary{font-weight:750;cursor:pointer}
table{width:100%;border-collapse:collapse;background:white;border-radius:12px;overflow:hidden}th,td{text-align:left;padding:11px;border-bottom:1px solid var(--line)}th{background:#eaf0fb}
.exercise{background:#fff;border:1px solid var(--line);border-radius:15px;padding:17px;margin:13px 0}.exercise p{margin-top:0}.exercise .answer-row{display:grid;grid-template-columns:repeat(auto-fit,minmax(135px,1fr));gap:10px}.exercise .answer-row label{font-size:.9rem}
.progress-wrap{height:10px;background:#e0e7f3;border-radius:99px;overflow:hidden;margin:10px 0}.progress{height:100%;width:0;background:linear-gradient(90deg,var(--blue),var(--teal));transition:width .25s}
footer{text-align:center;color:var(--muted);padding:25px;border-top:1px solid var(--line)}
@media(max-width:560px){header{padding-top:32px}.card,.interactive{padding:16px}th,td{padding:8px;font-size:.9rem}}
</style>
</head>
<body>
<header>
 <div class="hero">
  <div class="eyebrow">Aula digital · Estadística</div>
  <h1>¿Qué nos dicen los datos?</h1>
  <p>Aprende a calcular e interpretar la media, la mediana, la moda y el rango con ejemplos, herramientas interactivas.</p>
  <nav><a href="#conceptos">Conceptos</a><a href="#ejemplo">Ejemplo guiado</a><a href="#laboratorio">Calculadora</a><a href="#recursos">Recursos</a><a href="#ejercicios">10 ejercicios</a></nav>
 </div>
</header>
<main>
<section class="section" id="conceptos">
 <h2>1. Cuatro ideas clave</h2>
 <p class="section-intro">Las medidas de tendencia central describen el centro de un conjunto de datos. El rango nos habla de qué tan separados están sus extremos.</p>
 <div class="grid">
  <article class="card"><div class="symbol">x̄</div><h3>Media aritmética</h3><p>Es el promedio. Se suman todos los valores y se divide entre la cantidad de datos.</p><div class="formula">Media = suma de los datos ÷ cantidad</div><p><b>Ejemplo:</b> 2, 4 y 6 → (2 + 4 + 6) ÷ 3 = <b>4</b>.</p></article>
  <article class="card"><div class="symbol">Me</div><h3>Mediana</h3><p>Es el valor central cuando los datos están ordenados de menor a mayor.</p><p>Si hay una cantidad par de datos, se promedian los dos valores centrales.</p><div class="formula">Par: mediana = (central 1 + central 2) ÷ 2</div><p><b>Ejemplo:</b> 1, 3, 5 → mediana = <b>3</b>.</p></article>
  <article class="card"><div class="symbol">Mo</div><h3>Moda</h3><p>Es el valor que aparece con mayor frecuencia. Puede haber una moda, varias modas o ninguna si todos aparecen igual número de veces.</p><p><b>Ejemplo:</b> 2, 2, 3, 5 → moda = <b>2</b>.</p></article>
  <article class="card"><div class="symbol">R</div><h3>Rango</h3><p>Es la diferencia entre el valor máximo y el valor mínimo. Describe la amplitud entre los extremos.</p><div class="formula">Rango = máximo − mínimo</div><p><b>Ejemplo:</b> 3, 4, 8, 10 → 10 − 3 = <b>7</b>.</p></article>
 </div>
 <div class="card" style="margin-top:15px"><h3>Pasos para no equivocarte</h3><ol><li>Cuenta cuántos datos hay.</li><li>Ordena los datos para hallar la mediana.</li><li>Suma y divide para hallar la media.</li><li>Cuenta las repeticiones para hallar la moda.</li><li>Resta el mínimo al máximo para hallar el rango.</li></ol></div>
</section>

<section class="section" id="ejemplo">
 <h2>2. Ejemplo guiado</h2>
 <p>Diez estudiantes registraron cuántas horas estudiaron durante el fin de semana:</p>
 <div class="data"><span class="chip">2</span><span class="chip">3</span><span class="chip">1</span><span class="chip">4</span><span class="chip">2</span><span class="chip">5</span><span class="chip">3</span><span class="chip">2</span><span class="chip">6</span><span class="chip">2</span></div>
 <div class="card">
  <h3>Resolvamos paso a paso</h3>
  <p><b>1. Ordenamos:</b> 1, 2, 2, 2, 2, 3, 3, 4, 5, 6.</p>
  <p><b>2. Media:</b> la suma es 30; 30 ÷ 10 = <b>3 horas</b>.</p>
  <p><b>3. Mediana:</b> hay 10 datos, por eso promediamos el 5.º y 6.º: (2 + 3) ÷ 2 = <b>2,5 horas</b>.</p>
  <p><b>4. Moda:</b> el 2 aparece cuatro veces, más que cualquier otro valor. La moda es <b>2 horas</b>.</p>
  <p><b>5. Rango:</b> máximo 6 − mínimo 1 = <b>5 horas</b>.</p>
  <div class="formula">Interpretación: el promedio es 3 horas, el valor más frecuente es 2 horas y la diferencia entre el mayor y el menor registro es de 5 horas.</div>
 </div>
</section>

<section class="section" id="laboratorio">
 <h2>3. Laboratorio de datos</h2>
 <p class="section-intro">Escribe números separados por comas y pulsa “Calcular”. Prueba cómo cambian las medidas al modificar los datos.</p>
 <div class="interactive">
  <label for="dataset">Conjunto de datos</label>
  <input id="dataset" type="text" value="2, 3, 1, 4, 2, 5, 3, 2, 6, 2" aria-describedby="datasetHelp">
  <p id="datasetHelp" style="color:var(--muted);font-size:.9rem">Introduce al menos un número. Usa comas o espacios para separar los valores.</p>
  <button id="calculate">Calcular medidas</button> <button class="secondary" id="reset">Restablecer ejemplo</button>
  <div id="calcFeedback" class="feedback" role="status"></div>
  <div class="grid" style="margin-top:15px">
   <div class="result"><small>Media</small><strong id="meanOut">—</strong></div><div class="result"><small>Mediana</small><strong id="medianOut">—</strong></div><div class="result"><small>Moda</small><strong id="modeOut">—</strong></div><div class="result"><small>Rango</small><strong id="rangeOut">—</strong></div>
  </div>
  <p><b>Datos ordenados:</b> <span id="sortedOut">—</span></p>
 </div>
</section>

<section class="section" id="recursos">
 <h2>4. Recursos para aprender</h2>
 <div class="grid">
  <article class="card"><h3>🧠 Tarjetas de memoria</h3><p>Intenta responder antes de revelar la definición.</p>
   <details><summary>¿Cómo calculo la media?</summary>Sumo todos los datos y divido el resultado entre la cantidad de datos.</details>
   <details><summary>¿Qué hago si hay una cantidad par de datos?</summary>Ordeno los datos, identifico los dos valores centrales y calculo su promedio.</details>
   <details><summary>¿Puede haber más de una moda?</summary>Sí. Si dos o más valores comparten la frecuencia máxima, todos son modas.</details>
   <details><summary>¿Qué indica un rango grande?</summary>Que existe una mayor diferencia entre el valor máximo y el mínimo; no describe por sí solo cómo se distribuyen los demás datos.</details>
  </article>
  <article class="card"><h3>📋 Tabla de frecuencias</h3><p>Una tabla de frecuencias muestra cuántas veces aparece cada valor. Es útil para encontrar la moda.</p>
   <table><thead><tr><th>Horas</th><th>Frecuencia</th></tr></thead><tbody><tr><td>1</td><td>1</td></tr><tr><td>2</td><td>4</td></tr><tr><td>3</td><td>2</td></tr><tr><td>4</td><td>1</td></tr><tr><td>5</td><td>1</td></tr><tr><td>6</td><td>1</td></tr></tbody></table>
  </article>
  <article class="card"><h3>🔎 Piensa como estadístico</h3><p>La media puede cambiar mucho si aparece un valor extremo. La mediana suele ser más resistente a esos valores, mientras que la moda indica lo más frecuente.</p><p>Por eso conviene elegir la medida según la pregunta que queremos responder.</p></article>
 </div>
</section>

<section class="section" id="ejercicios">
 <h2>5. ¡Tu turno! Diez ejercicios</h2>
 <p class="section-intro">Resuelve los ejercicios y escribe tus respuestas. Al terminar, pulsa “Revisar respuestas”. En preguntas de interpretación, compara tu razonamiento con la explicación.</p>
 <div class="card">
  <b>Progreso</b> <span id="progressText">0 de 10 respondidos</span>
  <div class="progress-wrap"><div class="progress" id="progressBar"></div></div>
 </div>
 <div id="exerciseList"></div>
 <button id="checkAll">Revisar respuestas</button> <button class="secondary" id="clearAll">Borrar respuestas</button>
 <div id="scoreFeedback" class="feedback" role="status"></div>
</section>
</main>
<footer>Estadística interactiva · Aprende, calcula, interpreta y practica.</footer>
<script>
const $=id=>document.getElementById(id);
const fmt=n=>Number.isInteger(n)?String(n):String(Math.round(n*100)/100).replace('.',',');
function stats(nums){
 const s=[...nums].sort((a,b)=>a-b), n=s.length, sum=nums.reduce((a,b)=>a+b,0);
 const med=n%2?s[(n-1)/2]:(s[n/2-1]+s[n/2])/2;
 const counts=new Map();s.forEach(v=>counts.set(v,(counts.get(v)||0)+1));
 const maxFreq=Math.max(...counts.values()); const modes=[...counts].filter(([v,c])=>c===maxFreq).map(([v])=>v);
 return {s,mean:sum/n,median:med,modes:maxFreq===1?[]:modes,range:s[n-1]-s[0],maxFreq};
}
function calc(){
 const raw=$('dataset').value.trim(), nums=raw.split(/[,\s;]+/).filter(Boolean).map(Number);
 const fb=$('calcFeedback');fb.className='feedback show';
 if(!raw||nums.some(n=>!Number.isFinite(n))){fb.classList.add('bad');fb.textContent='Revisa los datos: escribe únicamente números separados por comas o espacios.';return}
 if(nums.length>500){fb.classList.add('bad');fb.textContent='Para mantener la página ágil, introduce como máximo 500 datos.';return}
 const st=stats(nums);fb.className='feedback show good';fb.textContent=`Se analizaron ${nums.length} dato(s).`;
 $('meanOut').textContent=fmt(st.mean);$('medianOut').textContent=fmt(st.median);$('modeOut').textContent=st.modes.length?st.modes.map(fmt).join(', '):'Sin moda';$('rangeOut').textContent=fmt(st.range);$('sortedOut').textContent=st.s.map(fmt).join(', ');
}
$('calculate').addEventListener('click',calc);$('reset').addEventListener('click',()=>{$('dataset').value='2, 3, 1, 4, 2, 5, 3, 2, 6, 2';calc()});calc();

const exercises=[
 {q:'Calcula la media de 4, 6, 8 y 10.',hint:'Suma los cuatro valores y divide entre 4.',fields:[['Respuesta', 'mean']],ans:{mean:7},exp:'(4 + 6 + 8 + 10) ÷ 4 = 7.'},
 {q:'Encuentra la mediana de 3, 9, 5, 1 y 7.',hint:'Ordena los datos y busca el valor central.',fields:[['Mediana','median']],ans:{median:5},exp:'Ordenados: 1, 3, 5, 7, 9. El valor central es 5.'},
 {q:'Encuentra la moda de 4, 2, 4, 3, 2, 4, 5.',hint:'Cuenta las repeticiones de cada valor.',fields:[['Moda','mode']],ans:{mode:4},exp:'El 4 aparece tres veces; es la moda.'},
 {q:'Calcula el rango de 12, 7, 19, 4 y 15.',hint:'Resta el menor valor al mayor.',fields:[['Rango','range']],ans:{range:15},exp:'19 − 4 = 15.'},
 {q:'Calcula la media y el rango de 5, 5, 5, 5.',hint:'Todos los valores son iguales.',fields:[['Media','mean'],['Rango','range']],ans:{mean:5,range:0},exp:'Media = 20 ÷ 4 = 5. Rango = 5 − 5 = 0.'},
 {q:'Halla la mediana de 2, 8, 4 y 10.',hint:'Como hay cuatro datos, promedia los dos centrales una vez ordenados.',fields:[['Mediana','median']],ans:{median:6},exp:'Ordenados: 2, 4, 8, 10. Mediana = (4 + 8) ÷ 2 = 6.'},
 {q:'Los tiempos (en minutos) son 8, 10, 10, 12 y 20. Calcula la moda y el rango.',hint:'La moda es el valor más frecuente.',fields:[['Moda','mode'],['Rango','range']],ans:{mode:10,range:12},exp:'Moda = 10. Rango = 20 − 8 = 12 minutos.'},
 {q:'Un grupo obtuvo notas 3, 4, 4, 4 y 5. Calcula la media.',hint:'Suma las cinco notas y divide entre 5.',fields:[['Media','mean']],ans:{mean:4},exp:'(3 + 4 + 4 + 4 + 5) ÷ 5 = 4.'},
 {q:'Los datos son 2, 3, 3, 7 y 15. ¿Qué valor es la moda y cuál es el rango?',hint:'Busca el valor repetido y resta máximo − mínimo.',fields:[['Moda','mode'],['Rango','range']],ans:{mode:3,range:13},exp:'Moda = 3. Rango = 15 − 2 = 13.'},
 {q:'Un conjunto tiene media 6, mediana 5, moda 4 y rango 9. ¿Cuál de estas medidas se obtiene restando el mínimo al máximo?',hint:'Recuerda qué medida describe la diferencia entre los extremos.',fields:[['Respuesta numérica (escribe el valor)','interpret']],ans:{interpret:9},exp:'Es el rango: se calcula máximo − mínimo. En este caso, el rango es 9.'}
];
const list=$('exerciseList');
exercises.forEach((ex,i)=>{
 const el=document.createElement('article');el.className='exercise';
 const title=document.createElement('h3');title.textContent=`${i+1}. ${ex.q}`;el.appendChild(title);
 const hint=document.createElement('p');hint.style.color='var(--muted)';hint.textContent=ex.hint;el.appendChild(hint);
 const row=document.createElement('div');row.className='answer-row';
 ex.fields.forEach(([label,key])=>{const wrap=document.createElement('div');const lab=document.createElement('label');lab.htmlFor=`e${i}_${key}`;lab.textContent=label;const inp=document.createElement('input');inp.id=`e${i}_${key}`;inp.type='text';inp.inputMode='decimal';inp.placeholder='Tu respuesta';inp.dataset.exercise=i;inp.dataset.key=key;inp.setAttribute('aria-label',`Ejercicio ${i+1}: ${label}`);inp.addEventListener('input',updateProgress);wrap.append(lab,inp);row.appendChild(wrap)});
 el.appendChild(row);const fb=document.createElement('div');fb.id=`fb${i}`;fb.className='feedback';fb.setAttribute('aria-live','polite');el.appendChild(fb);list.appendChild(el);
});
function parseAnswer(v){return v.trim().replace(',','.')}
function updateProgress(){
 const inputs=[...document.querySelectorAll('#exerciseList input')], answered=inputs.filter(i=>i.value.trim()).length;
 $('progressText').textContent=`${answered} de 10 respondidos`; $('progressBar').style.width=(answered/inputs.length*100)+'%';
}
function checkAll(){
 let correct=0,attempted=0;
 exercises.forEach((ex,i)=>{
  let exCorrect=true,exAttempted=false;
  ex.fields.forEach(([label,key])=>{
   const val=parseAnswer($(`e${i}_${key}`).value);
   if(val!=='')exAttempted=true;
   if(key==='mode'){
    const expected=String(ex.ans[key]); if(val!==expected)exCorrect=false;
   } else if(val===''||!Number.isFinite(Number(val))||Math.abs(Number(val)-ex.ans[key])>0.011)exCorrect=false;
  });
  if(exAttempted)attempted++;
  if(exCorrect){correct++;$('fb'+i).className='feedback show good';$('fb'+i).textContent='¡Correcto! '+ex.exp}
  else{$('fb'+i).className='feedback show bad';$('fb'+i).textContent=(exAttempted?'Revisa tu respuesta. ':'Aún no has respondido todo. ')+ex.exp}
 });
 const f=$('scoreFeedback');f.className='feedback show '+(correct===10?'good':'');f.textContent=`Resultado: ${correct} de 10 ejercicios correctos. Has intentado ${attempted} de 10. Revisa las explicaciones y vuelve a intentarlo.`;
}
$('checkAll').addEventListener('click',checkAll);
$('clearAll').addEventListener('click',()=>{document.querySelectorAll('#exerciseList input').forEach(i=>i.value='');document.querySelectorAll('#exerciseList .feedback').forEach(f=>{f.className='feedback';f.textContent=''});$('scoreFeedback').className='feedback';$('scoreFeedback').textContent='';updateProgress()});
</script>
</body>
</html>
