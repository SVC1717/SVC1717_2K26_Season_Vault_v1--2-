
const KEY='svc1717_builds_v1_stats';
let builds=JSON.parse(localStorage.getItem(KEY)||'[]');
let imageData='';
const $=id=>document.getElementById(id);

function save(){localStorage.setItem(KEY,JSON.stringify(builds));render();}
function showPage(name){
 document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
 $(name+'Page').classList.add('active');
 document.querySelectorAll('.nav').forEach(b=>b.classList.toggle('active',b.dataset.page===name));
 $('title').textContent=document.querySelector('.nav[data-page="'+name+'"]').textContent.trim();
}
function esc(v){return String(v??'').replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));}
function pct(v){return v!==''&&v!=null?Number(v).toFixed(1)+'%':'—';}
function winPct(b){const w=Number(b.wins||0),l=Number(b.losses||0),t=w+l;return t?((w/t)*100).toFixed(1)+'%':'—';}

function card(b){
 return `<article class="card">
 ${b.image?`<img src="${b.image}" alt="${esc(b.name)}">`:`<div class="img-placeholder">UPLOAD SCREENSHOT</div>`}
 <div class="card-body"><h4>${esc(b.name)}</h4>
 <div class="meta">${esc(b.position||'No position')} • ${esc(b.height||'No height')}<br>${esc(b.archetype||'No archetype')}<br>Version ${esc(b.version||'1.0')} • ${esc(b.caps||0)} caps</div>
 <div class="mini-stats">
  <div><span>3PT%</span><strong>${pct(b.three)}</strong></div>
  <div><span>PPG</span><strong>${esc(b.ppg||'—')}</strong></div>
  <div><span>W-L</span><strong>${esc(b.wins||0)}-${esc(b.losses||0)}</strong></div>
 </div>
 <div class="card-actions"><button onclick="viewBuild('${b.id}')">View</button><button onclick="editBuild('${b.id}')">Edit</button><button onclick="deleteBuild('${b.id}')">Delete</button></div>
 </div></article>`;
}
function render(){
 $('buildGrid').innerHTML=builds.length?builds.map(card).join(''):'<div>No builds yet. Click Add Build.</div>';
 $('recentBuilds').innerHTML=builds.length?builds.slice(0,3).map(card).join(''):'<div>No builds yet.</div>';
 $('buildCount').textContent=builds.length;
 const threes=builds.map(b=>Number(b.three)).filter(n=>!isNaN(n)&&n>0);
 $('avg3pt').textContent=threes.length?(threes.reduce((a,b)=>a+b,0)/threes.length).toFixed(1)+'%':'0%';
 $('totalWins').textContent=builds.reduce((s,b)=>s+Number(b.wins||0),0);
 $('totalLosses').textContent=builds.reduce((s,b)=>s+Number(b.losses||0),0);
}
function resetForm(){
 $('buildForm').reset();$('buildId').value='';$('version').value='1.0';$('caps').value=0;imageData='';$('preview').classList.add('hidden');$('dialogTitle').textContent='Add Build';
}
function openAdd(){resetForm();$('buildDialog').showModal();}
window.editBuild=id=>{
 const b=builds.find(x=>x.id===id); if(!b)return; resetForm();$('dialogTitle').textContent='Edit Build';
 Object.keys(b).forEach(k=>{if($(k)&&k!=='image')$(k).value=b[k]??'';});
 $('buildId').value=b.id; imageData=b.image||''; if(imageData){$('preview').src=imageData;$('preview').classList.remove('hidden');}
 $('buildDialog').showModal();
}
window.deleteBuild=id=>{const b=builds.find(x=>x.id===id);if(b&&confirm('Delete '+b.name+'?')){builds=builds.filter(x=>x.id!==id);save();}}
const item=(l,v)=>`<div class="detail-item"><span>${esc(l)}</span><strong>${esc(v||'—')}</strong></div>`;
window.viewBuild=id=>{
 const b=builds.find(x=>x.id===id);if(!b)return;
 $('detail').innerHTML=`<div class="modal-head"><div><div class="small">BUILD PAGE</div><h3>${esc(b.name)}</h3></div><button class="close" onclick="$('detailDialog').close()">✕</button></div>
 ${b.image?`<img class="detail-image" src="${b.image}">`:''}
 <h4>Build Information</h4><div class="detail-grid">${item('Position',b.position)}${item('Height',b.height)}${item('Weight',b.weight)}${item('Wingspan',b.wingspan)}${item('Archetype',b.archetype)}${item('Version',b.version)}${item('Cap Breakers',b.caps)}</div>
 <h4>Jump Shot</h4><div class="detail-grid">${item('Base',b.base)}${item('Release 1',b.release1)}${item('Release 2',b.release2)}${item('Blend',b.blend)}</div>
 <h4>Build Stats</h4><div class="detail-grid">${item('FG%',pct(b.fg))}${item('3PT%',pct(b.three))}${item('FT%',pct(b.ft))}${item('PPG',b.ppg)}${item('APG',b.apg)}${item('RPG',b.rpg)}${item('SPG',b.spg)}${item('BPG',b.bpg)}${item('Wins',b.wins)}${item('Losses',b.losses)}${item('Win %',winPct(b))}${item('Rating',b.rating?b.rating+'/10':'—')}${item('Best Game',b.bestGame)}</div>
 <h4>Notes</h4><p>${esc(b.notes||'No notes yet.')}</p>`;
 $('detailDialog').showModal();
}
$('imageInput').addEventListener('change',e=>{const f=e.target.files[0];if(!f)return;const r=new FileReader();r.onload=()=>{imageData=r.result;$('preview').src=imageData;$('preview').classList.remove('hidden')};r.readAsDataURL(f);});
$('buildForm').addEventListener('submit',e=>{
 e.preventDefault(); const id=$('buildId').value||crypto.randomUUID();
 const fields=['name','position','height','weight','wingspan','archetype','version','caps','base','release1','release2','blend','fg','three','ft','ppg','apg','rpg','spg','bpg','wins','losses','bestGame','rating','notes'];
 const b={id,image:imageData}; fields.forEach(k=>b[k]=$(k).value.trim());
 const i=builds.findIndex(x=>x.id===id); if(i>=0)builds[i]=b;else builds.unshift(b);
 save();$('buildDialog').close();showPage('builds');
});
$('enterBtn').onclick=()=>{$('cover').classList.add('hidden');$('app').classList.remove('hidden')};
$('quickAdd').onclick=openAdd;$('heroAdd').onclick=openAdd;$('addBuild').onclick=openAdd;
$('closeBtn').onclick=()=>$('buildDialog').close();$('cancelBtn').onclick=()=>$('buildDialog').close();
document.querySelectorAll('.nav').forEach(b=>b.onclick=()=>showPage(b.dataset.page));
render();
