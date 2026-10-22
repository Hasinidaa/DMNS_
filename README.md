<!DOCTYPE html>
<html lang="en"><head><meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>TransitIQ – Smarter Routes, Better Journeys</title>
<style>
:root{--bg:#f3f7f8;--card:#fff;--ink:#12303a;--mut:#5d7680;--line:#d9e5e8;--blue:#1e5fd1;--teal:#0f9d8f;--warn:#d98a00;--bad:#c9372c;--side:#0e2b3a;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media(prefers-color-scheme:dark){:root:not([data-theme=light]){--bg:#0b1a22;--card:#122733;--ink:#e3f0f3;--mut:#8fa9b2;--line:#23404e;--blue:#6aa3ff;--teal:#3cc9b9;--side:#081319}}
:root[data-theme=dark]{--bg:#0b1a22;--card:#122733;--ink:#e3f0f3;--mut:#8fa9b2;--line:#23404e;--blue:#6aa3ff;--teal:#3cc9b9;--side:#081319}
*{box-sizing:border-box}html{scroll-padding-top:env(safe-area-inset-top,0px)}
body{margin:0;background:var(--bg);color:var(--ink);font:15px/1.5 "Trebuchet MS","Segoe UI",system-ui,sans-serif}
.app{display:flex;min-height:100vh}
nav{width:210px;background:var(--side);color:#cfe3e8;padding:16px 10px;flex:none}
nav h1{font-size:20px;margin:0 8px 2px;color:#fff;letter-spacing:.3px}nav small{display:block;margin:0 8px 18px;color:#7fb3bd}
nav button{display:block;width:100%;text-align:left;background:none;border:0;color:inherit;padding:9px 10px;border-radius:6px;font:inherit;cursor:pointer}
nav button.on,nav button:hover{background:rgba(60,201,185,.18);color:#fff}
main{flex:1;padding:18px;min-width:0;max-width:1100px}
.top{display:flex;gap:10px;align-items:center;flex-wrap:wrap;margin-bottom:12px}.top h2{margin:0;flex:1;font-size:22px}
.badge{background:#fff3d6;color:#7a5200;border-radius:99px;padding:2px 10px;font-size:12px}
button.b,select,input,textarea{font:inherit;color:var(--ink);background:var(--card);border:1px solid var(--line);border-radius:6px;padding:6px 10px}
button.b{background:var(--blue);color:#fff;border:0;cursor:pointer}button.g{background:var(--card);color:var(--ink);border:1px solid var(--line)}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(150px,1fr));gap:10px;margin-bottom:12px}
.card{background:var(--card);border:1px solid var(--line);border-radius:10px;padding:12px;margin-bottom:12px;overflow-x:auto}
.kpi b{display:block;font-size:26px;color:var(--teal)}.kpi span{color:var(--mut);font-size:13px}
.two{display:grid;grid-template-columns:repeat(auto-fit,minmax(300px,1fr));gap:12px}
h3{margin:0 0 8px;font-size:16px}table{width:100%;border-collapse:collapse;font-size:14px}th,td{text-align:left;padding:6px 8px;border-bottom:1px solid var(--line)}
.row{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:10px}.low{color:var(--teal)}.mod{color:var(--blue)}.high{color:var(--warn)}.over{color:var(--bad)}
.hide{display:none}svg text{fill:var(--mut);font-size:11px}.note{color:var(--mut);font-size:13px}
.hero{background:linear-gradient(120deg,#1e5fd1,#0f9d8f);color:#fff;border-radius:12px;padding:22px;margin-bottom:12px}.hero h2{margin:0 0 4px;font-size:26px}
nav button{border-left:3px solid transparent;margin-bottom:2px}nav button.on{border-left-color:var(--teal);font-weight:600}
.card{box-shadow:0 1px 2px rgba(14,43,58,.06)}th{color:var(--mut);font-weight:600;font-size:13px}
.guest nav,.guest .top h2{display:none}.guest main{max-width:1100px;margin:0 auto;width:100%}
.auth{display:grid;grid-template-columns:1.15fr 1fr;min-height:calc(100vh - 90px);border-radius:16px;overflow:hidden;border:1px solid var(--line);box-shadow:0 10px 30px rgba(14,43,58,.15)}
.brand{background:linear-gradient(150deg,#0e2b3a,#1e5fd1 62%,#0f9d8f);color:#fff;padding:40px;display:flex;flex-direction:column;justify-content:center;gap:14px}
.brand .logo{font-size:20px;font-weight:700;letter-spacing:.4px}.brand h2{font-size:40px;line-height:1.1;margin:0}.brand p{margin:0;color:#cfe8ee;max-width:420px}
.brand ul{margin:0;padding:0;list-style:none;color:#e3f4f6}.brand li{padding:3px 0}.brand li:before{content:"";display:inline-block;width:8px;height:8px;border-radius:50%;background:#3cc9b9;margin-right:10px}
.panel{background:var(--card);padding:40px;display:flex;flex-direction:column;justify-content:center}.panel h3{font-size:22px}
.tabs{display:flex;gap:4px;background:var(--bg);padding:4px;border-radius:10px;margin-bottom:12px}.tabs button{flex:1;border:0;background:none;padding:8px;border-radius:8px;font:inherit;color:var(--mut);cursor:pointer}.tabs button.on{background:var(--card);color:var(--ink);font-weight:600;box-shadow:0 1px 3px rgba(0,0,0,.2)}
.panel label{display:block;font-size:13px;color:var(--mut);margin:10px 0 3px}.panel input{width:100%;padding:9px 12px}.panel .b{width:100%;padding:10px;margin-top:6px;font-weight:600}
:focus-visible{outline:2px solid var(--teal);outline-offset:2px}
@media(max-width:800px){.auth{grid-template-columns:1fr}.brand{padding:26px}.brand h2{font-size:28px}.panel{padding:26px}}
@media(max-width:700px){.app{flex-direction:column}nav{width:100%;display:flex;flex-wrap:wrap;gap:4px;padding:8px}nav h1,nav small{display:none}nav button{width:auto}}
</style></head><body><div class="app">
<nav id="nav"><h1>TransitIQ</h1><small>Smarter Routes, Better Journeys</small></nav>
<main>
<div class="top"><h2 id="title"></h2><span class="badge">Fictional sample data · simulated, not live</span><span id="who" class="note"></span><button class="b g" id="theme">Theme</button><button class="b g" id="out">Sign out</button></div>
<div id="view"></div></main></div>
<script>
// ---------- Seeded fictional data (deterministic) ----------
let s=7;const rnd=()=>(s=(s*16807)%2147483647)/2147483647;
const stops=[["Central Station",0,0],["Market Square",2,1],["City Hospital",4,0],["University Gate",6,2],["Lake Park",8,1],["Tech Park",10,0],["Riverside",4,4],["Old Town",2,5],["Airport Road",8,5]].map((x,i)=>({id:i,name:x[0],x:x[1],y:x[2]}));
const routes=[{id:"R1",name:"Central–Tech Park",stops:[0,1,2,3,4,5],min:[0,6,12,19,25,32],bus:2},{id:"R2",name:"Old Town–Airport",stops:[7,6,2,4,8],min:[0,8,15,22,30],bus:2},{id:"R3",name:"Central–Riverside",stops:[0,1,6],min:[0,7,14],bus:1}];
const buses=[["B101","R1",50,"Active"],["B102","R1",40,"In Service"],["B201","R2",60,"Active"],["B202","R2",45,"Maintenance"],["B301","R3",35,"Active"]].map((b,i)=>({id:b[0],route:b[1],cap:b[2],status:b[3],occ:Math.round(b[2]*(0.2+rnd()*0.95))}));
const trips=[],counts=[];const today=new Date("2026-10-15");
for(let d=0;d<28;d++)routes.forEach(r=>{for(let h=6;h<22;h++){const peak=(h>=8&&h<=9||h>=17&&h<=18)?2.2:1,base={R1:40,R2:28,R3:18}[r.id],dt=new Date(today-d*864e5).toISOString().slice(0,10);
const p=Math.round(base*peak*(0.7+rnd()*0.6)*(d<14?1.1:1));const delay=rnd()<.18?Math.round(4+rnd()*12):0;
trips.push({route:r.id,date:dt,hour:h,pax:p,delay});}});
const users={admin:{pw:"admin123",role:"Administrator"},operator:{pw:"operator123",role:"Operator"},passenger:{pw:"pass123",role:"Passenger"}};
let me=null,tab="dash",fb=[],favs=[],thresholds={mod:50,high:75,over:100};
const load=()=>{try{fb=JSON.parse(localStorage.tiqfb||"[]");favs=JSON.parse(localStorage.tiqfav||"[]")}catch(e){}};load();
const save=()=>{try{localStorage.tiqfb=JSON.stringify(fb);localStorage.tiqfav=JSON.stringify(favs)}catch(e){}};
const $=q=>document.querySelector(q),sn=id=>stops[id].name;
const cat=p=>p>=thresholds.over?["Overcrowded","over"]:p>=thresholds.high?["High","high"]:p>=thresholds.mod?["Moderate","mod"]:["Low","low"];
// ---------- Charts (inline SVG) ----------
function bars(labels,vals,color="var(--blue)",w=520,h=190){const m=Math.max(...vals,1),bw=(w-30)/vals.length;let o=`<svg viewBox="0 0 ${w} ${h}" width="100%" role="img">`;
vals.forEach((v,i)=>{const bh=(h-40)*v/m;o+=`<rect x="${30+i*bw+2}" y="${h-25-bh}" width="${bw-4}" height="${bh}" fill="${color}" rx="2"><title>${labels[i]}: ${v}</title></rect><text x="${30+i*bw+bw/2}" y="${h-10}" text-anchor="middle">${labels[i]}</text>`});
return o+`<text x="0" y="12">${m}</text></svg>`}
function line(a,b,w=520,h=190){const all=a.concat(b),m=Math.max(...all,1),st=(w-40)/(a.length-1||1),pt=v=>v.map((y,i)=>`${30+i*st},${h-25-(h-45)*y/m}`).join(" ");
return `<svg viewBox="0 0 ${w} ${h}" width="100%"><polyline fill="none" stroke="var(--teal)" stroke-width="2" points="${pt(a)}"/><polyline fill="none" stroke="var(--mut)" stroke-dasharray="4" points="${pt(b)}"/><text x="0" y="12">${m}</text><text x="30" y="${h-6}">solid: current · dashed: previous 14 days</text></svg>`}
// ---------- Views ----------
const nav={Administrator:["dash","planner","kar","map","routes","buses","reports","feedback"],Operator:["dash","buses","kar","map","routes"],Passenger:["planner","kar","map","favs","feedback"]};
const names={dash:"Dashboard",planner:"Route planner",map:"Network map",kar:"Karnataka live map",routes:"Routes",buses:"Buses",reports:"Reports",feedback:"Feedback",favs:"Saved routes"};
function flt(){const f=$("#fr"),fd=$("#fd");return{r:f?f.value:"all",d:fd?+fd.value:14}}
function dash(){const v=$("#view");v.innerHTML=`<div class="row"><select id="fr"><option value="all">All routes</option>${routes.map(r=>`<option value="${r.id}">${r.id} ${r.name}</option>`).join("")}</select><select id="fd"><option value="7">Last 7 days</option><option value="14" selected>Last 14 days</option><option value="28">Last 28 days</option></select></div><div id="d"></div>`;
$("#fr").onchange=$("#fd").onchange=drawDash;drawDash()}
function drawDash(){const {r,d}=flt(),end=today,cut=x=>(end-new Date(x))/864e5;
const cur=trips.filter(t=>cut(t.date)<d&&(r=="all"||t.route==r)),prev=trips.filter(t=>cut(t.date)>=d&&cut(t.date)<2*d&&(r=="all"||t.route==r));
const sum=a=>a.reduce((x,t)=>x+t.pax,0),pc=sum(cur),pp=sum(prev),late=cur.filter(t=>t.delay>0).length;
const bs=buses.filter(b=>r=="all"||b.route==r),act=bs.filter(b=>b.status!="Maintenance").length,occ=bs.reduce((x,b)=>x+b.occ/b.cap*100,0)/(bs.length||1);
const hr=[...Array(16)].map((_,i)=>cur.filter(t=>t.hour==i+6).reduce((x,t)=>x+t.pax,0)),pk=hr.indexOf(Math.max(...hr))+6;
const day=[...Array(d)].map((_,i)=>sum(trips.filter(t=>(r=="all"||t.route==r)&&cut(t.date)==d-1-i)));
const dayp=[...Array(d)].map((_,i)=>sum(trips.filter(t=>(r=="all"||t.route==r)&&cut(t.date)==2*d-1-i)));
const rv=routes.map(x=>[x.id,sum(cur.filter(t=>t.route==x.id))]);
const k=[["Total passengers",pc.toLocaleString()],["Active buses",act+" / "+bs.length],["Active routes",r=="all"?routes.length:1],["Bus stops",stops.length],["Avg occupancy",occ.toFixed(0)+"%"],["On-time trips",(100-late/(cur.length||1)*100).toFixed(1)+"%"],["Delayed trips",late],["Demand growth",(pp?((pc-pp)/pp*100).toFixed(1):0)+"%"]];
$("#d").innerHTML=`<div class="grid">${k.map(x=>`<div class="card kpi" style="margin:0"><b>${x[1]}</b><span>${x[0]}</span></div>`).join("")}</div>
<div class="two"><div class="card"><h3>Daily passengers vs previous period</h3>${line(day,dayp)}</div>
<div class="card"><h3>Passengers by hour (peak: ${pk}:00)</h3>${bars(hr.map((_,i)=>i+6),hr,"var(--teal)")}</div>
<div class="card"><h3>Route volumes</h3>${bars(rv.map(x=>x[0]),rv.map(x=>x[1]))}<p class="note">Most used: ${[...rv].sort((a,b)=>b[1]-a[1])[0][0]} · Least used: ${[...rv].sort((a,b)=>a[1]-b[1])[0][0]}</p></div>
<div class="card"><h3>Occupancy (latest record)</h3><table><tr><th>Bus</th><th>Load</th><th>Level</th></tr>${bs.map(b=>{const p=b.occ/b.cap*100,c=cat(p);return`<tr><td>${b.id}</td><td>${b.occ}/${b.cap} (${p.toFixed(0)}%)</td><td class="${c[1]}">${c[0]}</td></tr>`}).join("")}</table><p class="note">Thresholds %: Moderate ≥ ${thresholds.mod}, High ≥ ${thresholds.high}, Overcrowded ≥ ${thresholds.over}. Updated 15 Oct 2026 (sample).</p></div></div>
<div class="card"><h3>Recommendations (rule-based decision support)</h3>${recs(cur,d)}</div>`}
function recs(cur,d){const o=[];routes.forEach(x=>{const t=cur.filter(q=>q.route==x.id),del=t.filter(q=>q.delay).length/(t.length||1),avg=t.reduce((a,q)=>a+q.pax,0)/(t.length||1);
if(del>.2)o.push(`${x.id}: ${(del*100).toFixed(0)}% of trips delayed in last ${d} days → review schedule buffer.`);if(avg>35)o.push(`${x.id}: average ${avg.toFixed(0)} passengers per hourly trip (last ${d} days) → consider extra peak capacity.`);if(avg<22)o.push(`${x.id}: low utilisation, ${avg.toFixed(0)} per trip (last ${d} days) → review frequency.`)});
return o.length?"<ul>"+o.map(x=>`<li>${x}</li>`).join("")+"</ul>":"<p class=note>No rule triggered for this selection.</p>"}
// route search: Dijkstra over (stop) graph with transfer penalty
function search(a,b){const adj={};routes.forEach(r=>r.stops.forEach((s,i)=>{if(i<r.stops.length-1){const n=r.stops[i+1],w=r.min[i+1]-r.min[i];(adj[s]=adj[s]||[]).push([n,w,r.id]);(adj[n]=adj[n]||[]).push([s,w,r.id])}}));
const best={},q=[[0,a,null,[a],[]]];const res=[];
while(q.length){q.sort((x,y)=>x[0]-y[0]);const [c,n,rid,path,legs]=q.shift();const key=n+"|"+rid;if(best[key]!==undefined&&best[key]<=c)continue;best[key]=c;
if(n==b){res.push({cost:c,path,legs});if(res.length>3)break;continue}
(adj[n]||[]).forEach(([m,w,r])=>{if(path.includes(m))return;q.push([c+w+(rid&&rid!=r?8:0),m,r,[...path,m],[...legs,r]])})}
return res.filter((x,i,arr)=>arr.findIndex(y=>y.path.join()==x.path.join())==i).slice(0,3).map(x=>({...x,transfers:x.legs.filter((l,i)=>i&&l!=x.legs[i-1]).length}))}
function planner(){const opt=stops.map(s=>`<option value="${s.id}">${s.name}</option>`).join("");
$("#view").innerHTML=`<div class="card"><div class="row"><select id="a">${opt}</select><select id="z">${opt}</select><input type="date" value="2026-10-16"><input type="time" value="08:00"><button class="b" id="go">Search routes</button></div><div id="res"><p class="note">Pick a source and destination. Results come from the configured stop network; times are scheduled estimates, not live arrivals.</p></div></div>`;
$("#z").value=5;$("#go").onclick=()=>{const a=+$("#a").value,z=+$("#z").value;if(a==z){$("#res").innerHTML="<p class=over>Source and destination must be different.</p>";return}
const r=search(a,z);$("#res").innerHTML=r.length?r.map((x,i)=>{const id=x.legs[0]+">"+a+">"+z;return`<div class="card"><h3>Option ${i+1}${i==0?" (fastest)":""}: ${x.cost} min est. · ${x.transfers} transfer(s)</h3><p>${x.path.map(sn).join(" → ")}</p><p class="note">Routes: ${[...new Set(x.legs)].join(", ")} · Fare: not configured</p><button class="b g" data-f="${id}">Save favorite</button></div>`}).join(""):`<p class="mod">No route connects these stops in the current network. Try a different pair.</p>`;
document.querySelectorAll("[data-f]").forEach(b=>b.onclick=()=>{favs.push({t:`${sn(a)} to ${sn(z)}`,v:b.dataset.f});save();b.textContent="Saved"})}}
function map(){const sc=70,P=s=>`${30+s.x*sc*0.9},${30+s.y*sc*0.8}`,col=["#1e5fd1","#d98a00","#0f9d8f"];
$("#view").innerHTML=`<div class="card"><div class="row"><select id="hl"><option value="all">All routes</option>${routes.map(r=>`<option>${r.id}</option>`).join("")}</select><span class="note">Schematic map of fictional stops. Bus positions are simulated, not live GPS.</span></div><svg id="mp" viewBox="0 0 740 400" width="100%"></svg></div>`;
const draw=()=>{const h=$("#hl").value;$("#mp").innerHTML=routes.map((r,i)=>`<polyline fill="none" stroke="${col[i]}" stroke-width="${h==r.id?6:3}" opacity="${h=="all"||h==r.id?1:.15}" points="${r.stops.map(x=>P(stops[x])).join(" ")}"/>`).join("")+stops.map(s=>`<circle cx="${P(s).split(",")[0]}" cy="${P(s).split(",")[1]}" r="7" fill="var(--card)" stroke="var(--ink)" stroke-width="2"><title>${s.name}</title></circle><text x="${+P(s).split(",")[0]+9}" y="${+P(s).split(",")[1]-9}">${s.name}</text>`).join("")+
buses.filter(b=>b.status!="Maintenance"&&(h=="all"||b.route==h)).map((b,i)=>{const r=routes.find(x=>x.id==b.route),a=stops[r.stops[i%(r.stops.length-1)]],c=stops[r.stops[i%(r.stops.length-1)+1]],p=P({x:(a.x+c.x)/2,y:(a.y+c.y)/2}).split(",");return`<rect x="${p[0]-8}" y="${p[1]-6}" width="16" height="12" rx="3" fill="#c9372c"><title>${b.id} (simulated)</title></rect>`}).join("")};
$("#hl").onchange=draw;draw()}
function routesV(){$("#view").innerHTML=routes.map(r=>`<div class="card"><h3>${r.id} · ${r.name}</h3><table><tr><th>Stop</th><th>Offset (min)</th></tr>${r.stops.map((x,i)=>`<tr><td>${sn(x)}</td><td>${r.min[i]}</td></tr>`).join("")}</table><p class="note">Buses: ${buses.filter(b=>b.route==r.id).map(b=>b.id).join(", ")}</p></div>`).join("")+`<p class="note">Editing routes needs the backend database; this demo is read-only.</p>`}
function busesV(){$("#view").innerHTML=`<div class="card"><div class="row"><input id="q" placeholder="Search bus or route"><select id="st"><option value="">All statuses</option><option>Active</option><option>In Service</option><option>Maintenance</option></select></div><div id="bt"></div></div>`;
const d=()=>{const q=$("#q").value.toLowerCase(),s=$("#st").value,l=buses.filter(b=>(b.id+b.route).toLowerCase().includes(q)&&(!s||b.status==s));$("#bt").innerHTML=l.length?`<table><tr><th>Bus</th><th>Route</th><th>Capacity</th><th>Status</th><th>Occupancy</th></tr>${l.map(b=>`<tr><td>${b.id}</td><td>${b.route}</td><td>${b.cap}</td><td>${b.status}</td><td class="${cat(b.occ/b.cap*100)[1]}">${cat(b.occ/b.cap*100)[0]}</td></tr>`).join("")}</table>`:"<p class=note>No buses match these filters.</p>"};$("#q").oninput=$("#st").onchange=d;d()}
function reports(){const by={};trips.forEach(t=>{const k=t.route;by[k]=by[k]||{p:0,n:0,l:0,m:0};by[k].p+=t.pax;by[k].n++;by[k].l+=t.delay?1:0;by[k].m+=t.delay});
const rows=Object.entries(by).map(([k,v])=>[k,v.p,v.n,v.l,v.l?(v.m/v.l).toFixed(1):0]);
$("#view").innerHTML=`<div class="card"><h3>Route performance, last 28 days</h3><table><tr><th>Route</th><th>Passengers</th><th>Trips</th><th>Delayed</th><th>Avg delay (min)</th></tr>${rows.map(r=>`<tr>${r.map(c=>`<td>${c}</td>`).join("")}</tr>`).join("")}</table><p class="note">Generated ${new Date().toLocaleString()} · passengers are summed per trip, never from cumulative snapshots.</p><button class="b" id="csv">Download CSV</button> <span id="cs" class="note" role="status"></span> <button class="b g" onclick="print()">Print</button></div>`;
$("#csv").onclick=async()=>{const t="route,passengers,trips,delayed,avg_delay_min\n"+rows.map(r=>r.join(",")).join("\n"),st=$("#cs");let dl=null;try{dl=window.claude&&await window.claude.use("downloads")}catch(e){}
if(!dl){st.textContent="Downloads are not available in this view. Open the page in claude.ai to save the CSV.";return}
try{await dl.save({filename:"route_performance.csv",data:t});st.textContent="CSV saved."}catch(e){st.textContent=e&&e.code=="declined"?"Download cancelled.":"Could not save the CSV ("+((e&&e.code)||"error")+").")}}}
function feedback(){$("#view").innerHTML=`<div class="card"><h3>Submit feedback</h3><div class="row"><select id="c"><option>Delay</option><option>Overcrowding</option><option>Accessibility</option><option>Other</option></select><select id="fr">${routes.map(r=>`<option>${r.id}</option>`).join("")}</select></div><textarea id="m" rows="3" style="width:100%" placeholder="Describe the issue"></textarea><p id="e" class="over"></p><button class="b" id="s">Send</button></div><div class="card"><h3>Feedback history</h3><div id="h"></div></div>`;
const h=()=>{$("#h").innerHTML=fb.length?`<table><tr><th>Category</th><th>Route</th><th>Message</th><th>Status</th></tr>${fb.map((f,i)=>`<tr><td>${f.c}</td><td>${f.r}</td><td>${f.m}</td><td>${me.role=="Administrator"?`<select data-i="${i}">${["Open","In Progress","Resolved"].map(x=>`<option${x==f.s?" selected":""}>${x}</option>`).join("")}</select>`:f.s}</td></tr>`).join("")}</table>`:"<p class=note>No feedback yet.</p>";document.querySelectorAll("[data-i]").forEach(s=>s.onchange=()=>{fb[s.dataset.i].s=s.value;save()})};h();
$("#s").onclick=()=>{const m=$("#m").value.trim();if(m.length<5){$("#e").textContent="Enter at least 5 characters.";return}fb.unshift({c:$("#c").value,r:$("#fr").value,m,s:"Open"});save();$("#m").value="";$("#e").textContent="";h()}}
function favsV(){$("#view").innerHTML=`<div class="card">${favs.length?"<ul>"+favs.map(f=>`<li>${f.t}</li>`).join("")+"</ul>":"<p class=note>No saved routes yet. Save one from the route planner.</p>"}</div>`}
const KC={Bengaluru:[12.9716,77.5946],Mysuru:[12.2958,76.6394],Mangaluru:[12.9141,74.856],Hubballi:[15.3647,75.124],Belagavi:[15.8497,74.4977],Kalaburagi:[17.3297,76.8343],Shivamogga:[13.9299,75.5681],Davanagere:[14.4644,75.9218],Tumakuru:[13.3379,77.1173],Hassan:[13.0072,76.1004],Udupi:[13.3409,74.7421],Ballari:[15.1394,76.9214],Chitradurga:[14.2251,76.398],Madikeri:[12.4244,75.7382]};
const KR=[["KA-1 Bengaluru–Mysuru",["Bengaluru","Mysuru"]],["KA-2 Bengaluru–Belagavi",["Bengaluru","Tumakuru","Chitradurga","Davanagere","Hubballi","Belagavi"]],["KA-3 Bengaluru–Mangaluru",["Bengaluru","Hassan","Mangaluru"]],["KA-4 Mysuru–Mangaluru",["Mysuru","Madikeri","Mangaluru"]],["KA-5 Bengaluru–Shivamogga",["Bengaluru","Tumakuru","Davanagere","Shivamogga"]],["KA-6 Mangaluru–Shivamogga",["Mangaluru","Udupi","Shivamogga"]],["KA-7 Hubballi–Kalaburagi",["Hubballi","Ballari","Kalaburagi"]]];
const CL=["#1e5fd1","#d98a00","#0f9d8f","#c9372c","#7a4fd1","#2a8a3e","#b5527a"];
function kar(){const P=c=>[(c[1]-73.8)*100,(18.2-c[0])*103];let vb=[0,0,440,660];
const hv=(a,b)=>{const r=Math.PI/180,dl=(b[0]-a[0])*r,dn=(b[1]-a[1])*r,x=Math.sin(dl/2)**2+Math.cos(a[0]*r)*Math.cos(b[0]*r)*Math.sin(dn/2)**2;return 2*6371*Math.asin(Math.sqrt(x))*1.25};
const rt=KR.map(([n,s],i)=>{const pts=s.map(c=>KC[c]);const cum=[0];for(let k=1;k<pts.length;k++)cum.push(cum[k-1]+hv(pts[k-1],pts[k]));return{n,s,pts,cum,tot:cum[cum.length-1],i}});
const ist=()=>{const d=new Date(Date.now()+(330+new Date().getTimezoneOffset())*6e4);return d.getHours()*60+d.getMinutes()+d.getSeconds()/60};
const fmt=m=>{m=Math.round(m)%1440;return String(Math.floor(m/60)).padStart(2,"0")+":"+String(m%60).padStart(2,"0")};
const deps=r=>{const o=[];for(let h=5;h<=23;h+=2)[0,1].forEach(dir=>o.push({r,dir,dep:h*60+r.i*7+dir*30,dur:r.tot/50*60}));return o};
const pos=(t,m)=>{const r=t.r,f=(m-t.dep)/t.dur,tg=(t.dir?1-f:f)*r.tot;let k=1;while(k<r.cum.length-1&&r.cum[k]<tg)k++;const u=(tg-r.cum[k-1])/(r.cum[k]-r.cum[k-1]||1),a=r.pts[k-1],b=r.pts[k];return{ll:[a[0]+(b[0]-a[0])*u,a[1]+(b[1]-a[1])*u],next:t.dir?r.s[k-1]:r.s[k],eta:(t.dir?tg-r.cum[k-1]:r.cum[k]-tg)/50*60}};
const CO=Object.keys(KC).sort().map(c=>`<option>${c}</option>`).join("");
$("#view").innerHTML=`<div class="card"><h3>Plan a journey</h3><div class="row"><select id="jf" aria-label="From city">${CO}</select><button class="b g" id="jw" aria-label="Swap origin and destination">⇄</button><select id="jt" aria-label="To city">${CO}</select><button class="b" id="jg">Find buses</button></div><div id="jo"></div></div><div class="card"><h3>Data status</h3><table><tr><th>Data</th><th>Status</th><th>Shown as</th></tr><tr><td>Bus routes and timings</td><td>Sample schedule (fictional)</td><td>Scheduled, not live</td></tr><tr><td>Live bus GPS</td><td>No feed connected</td><td>Live tracking unavailable</td></tr><tr><td>Crowd levels</td><td>No source configured</td><td>Crowd information unavailable</td></tr><tr><td>Namma Metro</td><td>Not included until verified BMRCL data is imported</td><td>Unavailable</td></tr><tr><td>Street map</td><td>Tiles can't load on this page</td><td>Schematic map</td></tr></table></div><div class="card"><div class="row"><select id="kr"><option value="-1">All routes</option>${rt.map(r=>`<option value="${r.i}">${r.n}</option>`).join("")}</select><button class="b g" id="zi" aria-label="Zoom in">+</button><button class="b g" id="zo" aria-label="Zoom out">−</button><button class="b g" id="zr">Reset</button><span class="badge" id="clk"></span></div><p class="note">City positions are real. Roads are drawn as straight lines, with no street map tiles. Timings and bus positions are SIMULATED from a sample schedule at 50 km/h. They are not live KSRTC or BMTC data. Drag to pan, scroll or use +/− to zoom.</p><svg id="km" viewBox="0 0 440 660" width="100%" style="max-height:70vh;background:var(--bg);border-radius:8px;touch-action:none;cursor:grab"></svg></div><div class="two"><div class="card"><h3>Running now (simulated)</h3><div id="run"></div></div><div class="card"><h3>Timetable (sample)</h3><div id="tt"></div></div></div>`;
const draw=()=>{if(!$("#km")){clearInterval(window.tm);return}const sel=+$("#kr").value,m=ist(),k=vb[2]/440;$("#clk").textContent="IST "+fmt(m)+" · simulated";
const act=rt.filter(r=>sel<0||r.i==sel).flatMap(deps).filter(t=>m>=t.dep&&m<t.dep+t.dur).map(t=>({t,p:pos(t,m)}));
$("#km").innerHTML=rt.map(r=>`<polyline fill="none" stroke="${CL[r.i]}" stroke-width="${(sel==r.i?4:2)*k}" opacity="${sel<0||sel==r.i?.9:.15}" points="${r.pts.map(c=>P(c).join(",")).join(" ")}"/>`).join("")+Object.entries(KC).map(([n,c])=>{const p=P(c);return`<circle cx="${p[0]}" cy="${p[1]}" r="${4*k}" fill="var(--card)" stroke="var(--ink)" stroke-width="${1.5*k}"/><text x="${p[0]+6*k}" y="${p[1]-5*k}" style="font-size:${11*k}px">${n}</text>`}).join("")+act.map(({t,p})=>{const q=P(p.ll);return`<rect x="${q[0]-6*k}" y="${q[1]-4*k}" width="${12*k}" height="${8*k}" rx="${2*k}" fill="#c9372c"><title>${t.r.n} (simulated)</title></rect>`}).join("");
$("#run").innerHTML=act.length?`<table><tr><th>Route</th><th>To</th><th>Next stop</th><th>ETA</th></tr>${act.map(({t,p})=>`<tr><td>${t.r.n.split(" ")[0]}</td><td>${t.dir?t.r.s[0]:t.r.s[t.r.s.length-1]}</td><td>${p.next}</td><td>${fmt(m+p.eta)}</td></tr>`).join("")}</table>`:"<p class=note>No simulated buses are running on this route right now. Services run 05:00 to about midnight.</p>";
const R=rt[sel<0?0:sel],rows=flat(R).filter(t=>t.dep+t.dur>m).sort((a,b)=>a.dep-b.dep).slice(0,6);
$("#tt").innerHTML=`<p class="note">${R.n}${sel<0?" (pick a route above to see others)":""}</p><table><tr><th>Departs</th><th>From → To</th><th>Estimated stop times</th></tr>${rows.map(t=>{const st=t.dir?[...R.s].reverse():R.s,cu=t.dir?R.cum.map(c=>R.tot-c).reverse():R.cum;return`<tr><td>${fmt(t.dep)}${m>=t.dep?" (running)":""}</td><td>${st[0]} → ${st[st.length-1]}</td><td>${st.map((s,j)=>s+" "+fmt(t.dep+cu[j]/50*60)).join(" · ")}</td></tr>`}).join("")}</table>`};
const flat=R=>deps(R);
const sv=$("#km"),ap=()=>sv.setAttribute("viewBox",vb.join(" "));
const zoom=(f,cx,cy)=>{const nw=Math.min(440,Math.max(60,vb[2]*f)),r=nw/vb[2];vb=[cx-(cx-vb[0])*r,cy-(cy-vb[1])*r,nw,vb[3]*r];ap();draw()};
$("#zi").onclick=()=>zoom(.7,vb[0]+vb[2]/2,vb[1]+vb[3]/2);$("#zo").onclick=()=>zoom(1.4,vb[0]+vb[2]/2,vb[1]+vb[3]/2);$("#zr").onclick=()=>{vb=[0,0,440,660];ap();draw()};$("#kr").onchange=draw;
sv.onwheel=e=>{e.preventDefault();const b=sv.getBoundingClientRect();zoom(e.deltaY<0?.85:1.18,vb[0]+(e.clientX-b.left)/b.width*vb[2],vb[1]+(e.clientY-b.top)/b.height*vb[3])};
let dr=null;sv.onpointerdown=e=>{dr=[e.clientX,e.clientY];sv.setPointerCapture(e.pointerId)};sv.onpointerup=()=>dr=null;sv.onpointermove=e=>{if(!dr)return;const b=sv.getBoundingClientRect(),s=vb[2]/b.width;vb[0]-=(e.clientX-dr[0])*s;vb[1]-=(e.clientY-dr[1])*s;dr=[e.clientX,e.clientY];ap();draw()};
const nd=(l,after)=>deps(l.r).filter(t=>t.dir==l.dir).map(t=>t.dep+l.off/50*60).filter(x=>x>=after).sort((p,q)=>p-q)[0];
const leg=(r,x,y)=>{const i=r.s.indexOf(x),j=r.s.indexOf(y);if(i<0||j<0||i==j)return null;const d=i<j?0:1;return{r,x,y,dir:d,km:Math.abs(r.cum[i]-r.cum[j]),off:d?r.tot-r.cum[i]:r.cum[i]}};
const jr=()=>{const a=$("#jf").value,z=$("#jt").value,m=ist(),o=[];
if(a==z){$("#jo").innerHTML="<p class=over role=alert>Choose two different cities.</p>";return}
rt.forEach(r=>{const l=leg(r,a,z);if(l)o.push([l])});
rt.forEach(r1=>rt.forEach(r2=>{if(r1!=r2)Object.keys(KC).forEach(c=>{const l1=leg(r1,a,c),l2=leg(r2,c,z);if(l1&&l2&&c!=a&&c!=z)o.push([l1,l2])})}));
const res=o.map(ls=>{let t=m;const tm=[];for(const l of ls){const d=nd(l,t);if(d===undefined)return null;tm.push(d);t=d+l.km/50*60}return{ls,tm,arr:t,dep:tm[0]}}).filter(Boolean).sort((p,q)=>p.arr-q.arr).slice(0,4);
$("#jo").innerHTML=res.length?res.map((x,i)=>`<div class="card" style="margin-bottom:8px"><b>Option ${i+1}: depart ${fmt(x.dep)}, arrive ${fmt(x.arr)} (${Math.round(x.arr-x.dep)} min, ${x.ls.length-1} transfer(s))</b>${x.ls.map((l,k)=>`<p style="margin:4px 0">${l.r.n.split(" ")[0]}: ${l.x} ${fmt(x.tm[k])} → ${l.y} ${fmt(x.tm[k]+l.km/50*60)} · ${Math.round(l.km)} km</p>`).join("")}<p class="note">Scheduled (sample), not live · Crowd information unavailable · Fare not configured</p></div>`).join(""):"<p class=note>No journey with up to one transfer is left today in the sample network. Try another city pair.</p>"};
$("#jg").onclick=jr;$("#jw").onclick=()=>{const t=$("#jf").value;$("#jf").value=$("#jt").value;$("#jt").value=t;jr()};$("#jf").value="Bengaluru";$("#jt").value="Mysuru";jr();
draw();window.tm=setInterval(draw,2000)}
const V={kar,dash,planner,map,routes:routesV,buses:busesV,reports,feedback,favs:favsV};
function go(t){clearInterval(window.tm);tab=t;$("#title").textContent=names[t];document.querySelectorAll("nav button").forEach(b=>b.classList.toggle("on",b.dataset.t==t));V[t]()}
const sha=async t=>{try{const b=await crypto.subtle.digest("SHA-256",new TextEncoder().encode(t));return[...new Uint8Array(b)].map(x=>x.toString(16).padStart(2,"0")).join("")}catch(e){return t}};
let memU={};const getU=()=>{let s={};try{s=JSON.parse(localStorage.tiqusers||"{}")}catch(e){}return{...memU,...s}};
function enter(n,r){me={name:n,role:r};document.body.classList.remove("guest");$("#who").textContent=n+" ("+r+")";$("#out").classList.remove("hide");$("#nav").querySelectorAll("button").forEach(b=>b.remove());nav[r].forEach(t=>{const b=document.createElement("button");b.textContent=names[t];b.dataset.t=t;b.onclick=()=>go(t);$("#nav").appendChild(b)});go(nav[r][0])}
function login(mode){mode=mode||"in";const up=mode=="up";document.body.classList.add("guest");$("#nav").querySelectorAll("button").forEach(b=>b.remove());$("#out").classList.add("hide");$("#who").textContent="";
const f=(id,l,t,p)=>`<label for="${id}">${l}</label><input id="${id}" type="${t||"text"}" placeholder="${p||""}">`;
$("#view").innerHTML=`<div class="auth"><div class="brand"><div class="logo">TransitIQ</div><h2>Smarter Routes, Better Journeys</h2><p>Find the right bus, see how busy it is, and help operators run a network that fits real demand.</p>
<svg viewBox="0 0 420 90" width="100%" style="max-width:420px"><path d="M10 60 C80 10 140 80 210 40 S350 20 410 50" fill="none" stroke="#9fe4dc" stroke-width="4" stroke-linecap="round"/><g fill="#fff" stroke="#0e2b3a" stroke-width="3"><circle cx="10" cy="60" r="7"/><circle cx="115" cy="46" r="7"/><circle cx="210" cy="40" r="7"/><circle cx="315" cy="30" r="7"/><circle cx="410" cy="50" r="7"/></g><rect x="150" y="36" width="26" height="16" rx="4" fill="#f5b73b"/></svg>
<ul><li>Plan direct and connecting journeys</li><li>Track demand, delays and occupancy</li><li>Download reports and share feedback</li></ul></div>
<div class="panel"><div class="tabs"><button id="ti" class="${up?"":"on"}">Sign in</button><button id="tu" class="${up?"on":""}">Sign up</button></div><h3>${up?"Create your passenger account":"Welcome back"}</h3>
${up?f("n","Full name")+f("u","Username")+f("e","Email","email")+f("p","Password (8+ characters)","password")+f("c","Confirm password","password"):f("u","Username or email")+f("p","Password","password")}
<p id="er" class="over" role="alert"></p><button class="b" id="sub">${up?"Create account":"Sign in"}</button>
<p class="note">${up?"Accounts are saved in this browser only and start as Passenger.":"Development-only demo accounts: admin / admin123, operator / operator123, passenger / pass123."} This demo does not use a real server.</p></div></div>`;
$("#ti").onclick=()=>login("in");$("#tu").onclick=()=>login("up");const er=m=>$("#er").textContent=m;
$(".panel").onkeydown=e=>{if(e.key=="Enter")$("#sub").click()};
$("#sub").onclick=async()=>{const u=$("#u").value.trim().toLowerCase(),p=$("#p").value;
if(!up){const d=users[u],G=getU(),s=G[u]||Object.keys(G).map(k=>({k,...G[k]})).find(v=>v.email&&v.email.toLowerCase()==u);if(d&&d.pw===p)return enter(u,d.role);if(s&&s.pw===await sha(p))return enter(s.k||u,"Passenger");return er("Wrong username or password.")}
const n=$("#n").value.trim(),e=$("#e").value.trim(),c=$("#c").value;
if(n.length<2)return er("Enter your full name.");if(u.length<3)return er("Username needs at least 3 characters.");if(!/^\S+@\S+\.\S+$/.test(e))return er("Enter a valid email address.");if(p.length<8)return er("Password needs at least 8 characters.");if(p!==c)return er("Passwords do not match.");if(users[u]||getU()[u])return er("That username is taken. Choose another.");
const all=getU();all[u]={name:n,email:e,pw:await sha(p)};memU=all;try{localStorage.tiqusers=JSON.stringify(all)}catch(x){}enter(u,"Passenger")}}
function loginOld(){$("#nav").querySelectorAll("button").forEach(b=>b.remove());$("#who").textContent="";$("#out").classList.add("hide");$("#title").textContent="Welcome";
$("#view").innerHTML=`<div class="hero"><h2>TransitIQ</h2><div>Smarter Routes, Better Journeys. Plan trips, watch demand, and spot overcrowding.</div></div><div class="card" style="max-width:380px"><h3>Sign in</h3><div class="row"><input id="u" placeholder="Username"><input id="p" type="password" placeholder="Password"></div><p id="le" class="over"></p><button class="b" id="li">Sign in</button><p class="note">Development-only demo accounts: admin / admin123, operator / operator123, passenger / pass123. These are client-side demo logins, not real security.</p></div>`;
$("#li").onclick=()=>{const u=users[$("#u").value.trim()];if(!u||u.pw!==$("#p").value){$("#le").textContent="Wrong username or password.";return}me={name:$("#u").value.trim(),role:u.role};
$("#who").textContent=me.name+" ("+me.role+")";$("#out").classList.remove("hide");nav[me.role].forEach(t=>{const b=document.createElement("button");b.textContent=names[t];b.dataset.t=t;b.onclick=()=>go(t);$("#nav").appendChild(b)});go(nav[me.role][0])}}
$("#out").onclick=()=>{me=null;login()};$("#theme").onclick=()=>{const r=document.documentElement,d=getComputedStyle(r).getPropertyValue("--bg").trim()=="#0b1a22";r.dataset.theme=d?"light":"dark"};
login();
</script></body></html>
