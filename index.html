<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>BRALIMA - V4.3 Contrôle Carburant</title>
<style>
body{font-family:Arial;background:#0f172a;color:#fff;padding:15px}
.card{background:#fff;color:#111;border-radius:14px;padding:16px;max-width:480px;margin:auto}
h2{text-align:center;color:#b91c1c}
label{font-weight:bold;font-size:13px;display:block;margin-top:12px}
input,select{width:100%;padding:11px;border:1px solid #ccc;border-radius:8px;margin-top:4px;font-size:15px}
.row{display:flex;gap:10px}
.row>div{flex:1}
.btns{display:flex;gap:8px;margin-top:6px}
.btns button{flex:1;padding:11px;border-radius:8px;border:2px solid #111;background:#fff;font-weight:bold;cursor:pointer}
.btns button.active{background:#111;color:#facc15}
.calc{width:100%;background:#dc2626;color:#fff;border:none;padding:14px;border-radius:10px;font-size:17px;font-weight:bold;margin-top:16px}
.result{margin-top:16px;padding:14px;border-radius:10px;background:#fef3c7;color:#111;display:none}
.result.vol{background:#fee2e2}
.result.ok{background:#dcfce7}
.small{font-size:12px;color:#666}
</style>
</head>
<body>
<div class="card">
<h2>BRALIMA - V4.3<br><span style="font-size:13px">CAMIONS SEULEMENT • CONTRÔLE CARBURANT</span></h2>

<label>Nom Entreprise Client (PRODUCTION)</label>
<input value="BRALIMA" id="entreprise">

<label>Type de Camion - PRODUCTION RDC</label>
<select id="camion" onchange="majConso()">
<option value="33">Scania P360 - 33L/100 - Bralima Boissons</option>
<option value="36">Mercedes Actros - 36L/100 - Bralima Boissons</option>
<option value="22">Isuzu FVR - 22L/100 - Distribution Légère</option>
<option value="28">MAN TGS - 28L/100 - Bralima</option>
</select>
<div class="small" id="infoCamion">Scania P360: 33L base => 42.9L ville Kin (+30%), 44.6L province (+35%)</div>

<label>Immatriculation / Plaque</label>
<input id="plaque" placeholder="Ex: 1234-AB-26">

<label>Type de Trajet - Congo</label>
<div class="btns">
<button id="btnVille" onclick="setTrajet('ville')" class="active">Ville Kin (+30% bouchon)</button>
<button id="btnProv" onclick="setTrajet('province')">Province (+35% collines)</button>
</div>

<label>Charge</label>
<div class="btns">
<button id="btnCharge" onclick="setCharge('charge')" class="active">Chargé</button>
<button id="btnVide" onclick="setCharge('vide')">Vide (retour) -20L</button>
</div>

<label>Destination - Production & Provinces</label>
<select id="destination"></select>

<!-- MODE PROVINCE -->
<div id="blocProvince">
<label>Distance (km)</label>
<div class="row"><div><input type="number" id="distance" value="350"></div>
<div><input type="number" id="consoBase" value="33" readonly><span class="small">Conso base L/100 (auto)</span></div></div>
</div>

<!-- MODE VILLE KIN -->
<div id="blocVille">
<label>Réservoir au Départ (L) - Sans capteur, jauge / tige</label>
<input type="number" id="resDep" value="200">
<label>Réservoir à l'Arrivée (L) - Sans capteur, jauge / tige</label>
<input type="number" id="resArr" value="170">
<div class="row">
<div><label>Nombre de Livraisons / Arrêts</label><input type="number" id="nbLiv" value="8"></div>
<div><label>Heure Départ</label><input type="time" id="hDep" value="07:00"></div>
<div><label>Heure Arrivée</label><input type="time" id="hArr" value="16:00"></div>
</div>
<div class="small">Exemple: 200L - 170L = 30L consommé réel. Si chauffeur déclare 50L, vol = 20L.</div>
</div>

<label>Carburant Déclaré (L) - Ce que le chauffeur dit avoir utilisé</label>
<input type="number" id="declare" value="180">

<label>Prix Carburant FC / L (Manuel)</label>
<input type="number" id="prix" value="2635">
<div class="small">Kinshasa officiel 2635 FC, Matadi 3000 FC, Province 3500 FC - Tu changes manuellement</div>

<button class="calc" onclick="calculer()">CALCULER - DÉTECTER VOL</button>

<div id="res" class="result"></div>
</div>

<script>
let trajet='ville', charge='charge';
const destVille=[
"Tournée Limete - Gombe - Kintambo",
"Tournée Limete - Ngaliema - Mont Ngafula",
"Tournée Limete - Masina - N'Djili",
"Tournée Dépôt - Gombe (Centre Ville)",
"Tournée Autre Commune Kinshasa"
];
const destProv=[
["Kinshasa - Matadi / Boma (350 Km)",350],
["Kinshasa - Kimpese (220 Km)",220],
["Kinshasa - Kananga (1200 Km)",1200],
["Kinshasa - Kikwit (550 Km)",550],
["Kinshasa - Lubumbashi (2200 Km)",2200]
];
function majConso(){
  let base=document.getElementById('camion').value;
  document.getElementById('consoBase').value=base;
  document.getElementById('infoCamion').innerText=`Base ${base}L => ${(base*1.3).toFixed(1)}L ville Kin (+30%), ${(base*1.35).toFixed(1)}L province (+35%)`;
  majDest();
}
function majDest(){
  let sel=document.getElementById('destination');
  sel.innerHTML='';
  if(trajet==='ville'){
    destVille.forEach(d=>{let o=document.createElement('option');o.text=d;sel.add(o)});
  } else {
    destProv.forEach(d=>{let o=document.createElement('option');o.text=d[0];o.value=d[1];sel.add(o)});
    document.getElementById('distance').value=sel.value;
  }
}
function setTrajet(t){
  trajet=t;
  document.getElementById('btnVille').classList.toggle('active',t==='ville');
  document.getElementById('btnProv').classList.toggle('active',t==='province');
  document.getElementById('blocVille').style.display=t==='ville'?'block':'none';
  document.getElementById('blocProvince').style.display=t==='province'?'block':'none';
  majDest();
}
function setCharge(c){
  charge=c;
  document.getElementById('btnCharge').classList.toggle('active',c==='charge');
  document.getElementById('btnVide').classList.toggle('active',c==='vide');
}
document.getElementById('destination').addEventListener('change',function(){
  if(trajet==='province') document.getElementById('distance').value=this.value;
});
function calculer(){
  let base=parseFloat(document.getElementById('camion').value);
  let declare=parseFloat(document.getElementById('declare').value)||0;
  let prix=parseFloat(document.getElementById('prix').value)||0;
  let consoReelle=0, attendu=0, explication='';
  if(trajet==='ville'){
    let dep=parseFloat(document.getElementById('resDep').value)||0;
    let arr=parseFloat(document.getElementById('resArr').value)||0;
    consoReelle=dep-arr;
    // Tolérance bouchon : +5L si +8 livraisons ou +8h tournée
    let nb=parseFloat(document.getElementById('nbLiv').value)||0;
    let tolerance = nb>=8 ? 5 : 2;
    attendu=consoReelle+tolerance;
    explication=`MODE VILLE KIN - SANS CAPTEUR<br>Réservoir: ${dep}L - ${arr}L = ${consoReelle}L consommé réel<br>Livraisons: ${nb} arrêts | Tolérance bouchon: +${tolerance}L<br>Conso acceptée max: ${attendu}L`;
  } else {
    let dist=parseFloat(document.getElementById('distance').value)||0;
    let coef = trajet==='province' ? 1.35 : 1.3;
    attendu = dist*base/100*coef;
    if(charge==='vide') attendu = Math.max(0, attendu-20);
    consoReelle=attendu; // en province on compare déclaré vs attendu
    explication=`MODE PROVINCE<br>Distance: ${dist} Km x ${base}L/100 x ${coef} = ${attendu.toFixed(1)}L attendu<br>Charge: ${charge==='vide'?'Vide (-20L)':'Chargé'}`;
  }
  let vol = declare - (trajet==='ville' ? consoReelle : attendu);
  // En ville, on enlève la tolérance du vol
  if(trajet==='ville'){
    let nb=parseFloat(document.getElementById('nbLiv').value)||0;
    let tol = nb>=8 ? 5 : 2;
    vol = declare - consoReelle - tol;
  }
  let volFC = vol>0 ? vol*prix : 0;
  let box=document.getElementById('res');
  box.style.display='block';
  if(vol>0){
    box.className='result vol';
    box.innerHTML=`<b>🚨 VOL DÉTECTÉ</b><br>${explication}<br><br>Déclaré: ${declare}L<br><b>Vol: ${vol.toFixed(1)}L = ${volFC.toLocaleString()} FC</b>`;
  } else {
    box.className='result ok';
    box.innerHTML=`<b>✅ OK - PAS DE VOL</b><br>${explication}<br><br>Déclaré: ${declare}L<br>Diff: ${vol.toFixed(1)}L - Dans la tolérance`;
  }
}
majConso(); setTrajet('ville');
</script>
</body>
</html>
