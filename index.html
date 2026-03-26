<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<title>MGP ELEC - Devis / Facture PRO</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/xlsx/dist/xlsx.full.min.js"></script>

<style>
body { font-family: Arial; margin: 20px; }
img { height: 80px; }
input { margin: 5px; padding: 8px; }
button { padding: 10px; margin: 5px; cursor: pointer; }
canvas { border:1px solid #000; }
</style>
</head>

<body>

<img src="logo-png.png">

<h2>Créer devis / facture</h2>

<input type="text" id="nom" placeholder="Nom client"><br>
<input type="number" id="ht" placeholder="Montant HT"><br>

<label>TVA (%) :</label>
<input type="number" id="tva" value="8.5"><br><br>

<button onclick="saveDevis()">💾 Enregistrer devis</button>
<button onclick="toFacture()">➡️ Transformer en facture</button>
<button onclick="exportPDF()">📄 Export PDF</button>
<button onclick="exportExcel()">📊 Export Excel</button>

<h3>Signature client</h3>
<canvas id="signature" width="300" height="100"></canvas>
<br>
<button onclick="clearSign()">Effacer</button>

<hr>

<h2>Historique</h2>
<div id="list"></div>

<script>
let devis = JSON.parse(localStorage.getItem("devis")) || [];
let factures = JSON.parse(localStorage.getItem("factures")) || [];

function numero(type){
    let date = new Date();
    return type + "-" + date.getFullYear() + "-" + Date.now();
}

function calcul(){
    let ht = parseFloat(document.getElementById("ht").value);
    let tva = parseFloat(document.getElementById("tva").value);

    let montantTVA = ht * (tva/100);
    let ttc = ht + montantTVA;

    return {ht, tva, montantTVA, ttc};
}

function saveDevis(){
    let nom = document.getElementById("nom").value;
    let calc = calcul();

    let d = {
        num: numero("DEV"),
        nom,
        ...calc
    };

    devis.push(d);
    localStorage.setItem("devis", JSON.stringify(devis));
    afficher();
}

function toFacture(){
    let nom = document.getElementById("nom").value;
    let calc = calcul();

    let f = {
        num: numero("FAC"),
        nom,
        ...calc
    };

    factures.push(f);
    localStorage.setItem("factures", JSON.stringify(factures));
    afficher();
}

function afficher(){
    let div = document.getElementById("list");
    div.innerHTML = "<h3>Devis</h3>";

    devis.forEach(d=>{
        div.innerHTML += `${d.num} - ${d.nom} - ${d.ttc} €<br>`;
    });

    div.innerHTML += "<h3>Factures</h3>";

    factures.forEach(f=>{
        div.innerHTML += `${f.num} - ${f.nom} - ${f.ttc} €<br>`;
    });
}

async function exportPDF(){
    const { jsPDF } = window.jspdf;
    let doc = new jsPDF();

    let nom = document.getElementById("nom").value;
    let calc = calcul();

    doc.text("MGP ELEC", 10, 10);
    doc.text("Client : " + nom, 10, 20);
    doc.text("HT : " + calc.ht + " €", 10, 30);
    doc.text("TVA : " + calc.montantTVA + " €", 10, 40);
    doc.text("TTC : " + calc.ttc + " €", 10, 50);

    // signature
    let canvas = document.getElementById("signature");
    let img = canvas.toDataURL("image/png");
    doc.addImage(img, 'PNG', 10, 60, 60, 30);

    doc.save("document.pdf");
}

function exportExcel(){
    let data = [...devis, ...factures];

    let ws = XLSX.utils.json_to_sheet(data);
    let wb = XLSX.utils.book_new();
    XLSX.utils.book_append_sheet(wb, ws, "Documents");

    XLSX.writeFile(wb, "MGP_ELEC.xlsx");
}

// signature
let canvas = document.getElementById("signature");
let ctx = canvas.getContext("2d");
let draw = false;

canvas.addEventListener("mousedown", ()=> draw=true);
canvas.addEventListener("mouseup", ()=> draw=false);
canvas.addEventListener("mousemove", drawSign);

function drawSign(e){
    if(!draw) return;
    ctx.lineWidth = 2;
    ctx.lineTo(e.offsetX, e.offsetY);
    ctx.stroke();
}

function clearSign(){
    ctx.clearRect(0,0,canvas.width,canvas.height);
}

afficher();
</script>

</body>
</html>
