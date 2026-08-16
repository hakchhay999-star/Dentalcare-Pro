# index. html <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<meta name="theme-color" content="#07111f">
<title>DentalCare Pro</title>

<style>
:root{
  --black:#07111f;
  --black2:#0d1b2d;
  --blue:#1677ff;
  --blue2:#0758c9;
  --white:#fff;
  --bg:#f4f7fb;
  --line:#dce5ef;
  --text:#102033;
  --muted:#6b7b90;
  --green:#159a61;
  --red:#d94d55;
  --shadow:0 10px 30px rgba(7,17,31,.08);
}

*{box-sizing:border-box}

body{
  margin:0;
  font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Arial,sans-serif;
  background:var(--bg);
  color:var(--text);
}

button,input,select,textarea{font:inherit}
button{cursor:pointer}

.sidebar{
  position:fixed;
  left:0;
  top:0;
  bottom:0;
  width:245px;
  padding:20px 14px;
  color:white;
  background:linear-gradient(180deg,#040a12,#0c1d33);
}

.brand{
  display:flex;
  align-items:center;
  gap:10px;
  padding:6px 9px 28px;
}

.logo{
  width:43px;
  height:43px;
  display:grid;
  place-items:center;
  border-radius:13px;
  background:linear-gradient(135deg,#45adff,#075ed9);
  font-size:23px;
}

.brand b{font-size:18px}
.brand small{
  display:block;
  color:#8fa5bd;
  margin-top:2px;
}

.nav button{
  width:100%;
  border:0;
  background:none;
  color:#b9c8d9;
  text-align:left;
  padding:12px;
  margin:3px 0;
  border-radius:9px;
}

.nav button:hover,
.nav button.active{
  color:white;
  background:#ffffff12;
}

.sidebar-foot{
  position:absolute;
  bottom:20px;
  left:18px;
  color:#8195ad;
  font-size:11px;
}

.main{
  margin-left:245px;
  min-height:100vh;
  padding:24px;
}

.top{
  display:flex;
  align-items:center;
  justify-content:space-between;
  margin-bottom:20px;
}

.top h1{
  margin:0;
  font-size:27px;
}

.top p{
  margin:4px 0;
  color:var(--muted);
}

.btn{
  border:0;
  border-radius:9px;
  padding:10px 14px;
  background:var(--blue);
  color:white;
  font-weight:700;
}

.btn:hover{background:var(--blue2)}

.btn.secondary{
  color:var(--text);
  background:white;
  border:1px solid var(--line);
}

.btn.danger{
  color:var(--red);
  background:white;
  border:1px solid #efcaca;
}

.grid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:14px;
}

.card{
  background:white;
  border:1px solid var(--line);
  border-radius:14px;
  padding:17px;
  box-shadow:var(--shadow);
}

.stat small{color:var(--muted)}
.stat strong{
  display:block;
  font-size:28px;
  margin-top:7px;
}

.section{margin-top:17px}

.section-head{
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:10px;
  margin-bottom:12px;
}

.section-head h2{
  margin:0;
  font-size:17px;
}

.page{display:none}
.page.active{display:block}

.search{
  width:260px;
  padding:10px;
  border:1px solid var(--line);
  border-radius:9px;
}

.table-wrap{overflow:auto}

.table{
  width:100%;
  border-collapse:collapse;
}

.table th,
.table td{
  padding:11px 8px;
  text-align:left;
  border-bottom:1px solid var(--line);
  font-size:13px;
  white-space:nowrap;
}

.table th{
  color:var(--muted);
  font-weight:600;
}

.badge{
  display:inline-block;
  padding:4px 8px;
  border-radius:20px;
  background:#eaf2ff;
  color:#0865d6;
  font-size:11px;
  font-weight:700;
}

.badge.green{
  background:#e9f8f0;
  color:#128454;
}

.badge.red{
  background:#fff0f0;
  color:#bd3d45;
}

.empty{
  text-align:center;
  color:var(--muted);
  padding:30px;
}

.form{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:12px;
}

.form.three{
  grid-template-columns:repeat(3,1fr);
}

.full{grid-column:1/-1}

label{
  display:block;
  margin-bottom:5px;
  color:#506175;
  font-size:12px;
  font-weight:700;
}

input,select,textarea{
  width:100%;
  padding:10px;
  border:1px solid var(--line);
  border-radius:9px;
  background:white;
  color:var(--text);
}

textarea{
  min-height:90px;
  resize:vertical;
}

.modal{
  display:none;
  position:fixed;
  inset:0;
  z-index:30;
  padding:18px;
  overflow:auto;
  background:#030b16b8;
}

.modal.open{
  display:flex;
  align-items:center;
  justify-content:center;
}

.modal-box{
  width:min(1100px,100%);
  max-height:94vh;
  overflow:auto;
  border-radius:16px;
  background:white;
}

.modal-head{
  position:sticky;
  top:0;
  z-index:5;
  display:flex;
  align-items:center;
  gap:8px;
  padding:15px 18px;
  background:white;
  border-bottom:1px solid var(--line);
}

.modal-head h2{
  flex:1;
  margin:0;
  font-size:20px;
}

.close{
  width:34px;
  height:34px;
  border:0;
  border-radius:8px;
  background:#eef2f7;
  font-size:20px;
}

.tabs{
  display:flex;
  gap:6px;
  padding:11px 18px;
  overflow:auto;
  border-bottom:1px solid var(--line);
}

.tabs button{
  border:0;
  background:#f2f5f9;
  padding:9px 11px;
  border-radius:8px;
  white-space:nowrap;
}

.tabs button.active{
  color:#0865d6;
  background:#e8f2ff;
  font-weight:700;
}

.pane{
  display:none;
  padding:18px;
}

.pane.active{display:block}

.tooth-grid{
  display:grid;
  grid-template-columns:repeat(16,1fr);
  gap:6px;
  margin:12px 0;
}

.tooth{
  padding:5px;
  text-align:center;
  border:1px solid var(--line);
  border-radius:8px;
  background:#fbfdff;
}

.tooth b{
  display:block;
  color:#0865d6;
  font-size:11px;
}

.tooth select{
  padding:3px;
  margin-top:4px;
  font-size:10px;
}

.tooth.missing{
  background:#fff0f0;
  border-color:#e8b5b8;
}

.tooth.treated{
  background:#eaf8f1;
  border-color:#b8e3ce;
}

.history-row{
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:10px;
  padding:11px;
  margin:8px 0;
  border:1px solid var(--line);
  border-radius:10px;
}

.plan-row{
  display:grid;
  grid-template-columns:1fr 130px 140px 40px;
  gap:7px;
  margin-bottom:8px;
}

.xray-grid{
  display:grid;
  grid-template-columns:repeat(auto-fill,minmax(190px,1fr));
  gap:12px;
}

.xray{
  overflow:hidden;
  border:1px solid var(--line);
  border-radius:10px;
}

.xray img{
  width:100%;
  height:150px;
  display:block;
  object-fit:cover;
  background:#111;
}

.xray-info{
  padding:9px;
  font-size:12px;
}

.mobile-nav{display:none}

.toast{
  display:none;
  position:fixed;
  right:18px;
  bottom:18px;
  z-index:50;
  padding:12px 16px;
  color:white;
  background:var(--black);
  border-radius:9px;
}

.print-report{display:none}

@media(max-width:900px){
  .grid{grid-template-columns:repeat(2,1fr)}
  .sidebar{width:210px}
  .main{margin-left:210px}
  .tooth-grid{grid-template-columns:repeat(8,1fr)}
}

@media(max-width:650px){
  .sidebar{display:none}

  .main{
    margin:0;
    padding:14px;
    padding-bottom:75px;
  }

  .grid,
  .form,
  .form.three{
    grid-template-columns:1fr;
  }

  .top{
    flex-direction:column;
    align-items:flex-start;
  }

  .search{width:100%}

  .mobile-nav{
    display:flex;
    position:fixed;
    z-index:20;
    left:0;
    right:0;
    bottom:0;
    justify-content:space-around;
    padding:7px;
    background:var(--black);
  }

  .mobile-nav button{
    border:0;
    background:none;
    color:#b9c8d9;
    font-size:11px;
  }

  .mobile-nav button.active{color:white}

  .modal{padding:6px}

  .plan-row{
    grid-template-columns:1fr 1fr;
  }

  .plan-row button{
    grid-column:1/-1;
  }

  .tooth-grid{
    grid-template-columns:repeat(4,1fr);
  }
}

@media print{
  body{background:white}
  .sidebar,
  .top,
  .mobile-nav,
  .no-print{
    display:none!important;
  }

  .main{
    margin:0;
    padding:0;
  }

  .page{display:none!important}

  .print-report{
    display:block!important;
  }
}
</style>
</head>

<body>

<aside class="sidebar">
  <div class="brand">
    <div class="logo">🦷</div>
    <div>
      <b>DentalCare Pro</b>
      <small>Clinic Management</small>
    </div>
  </div>

  <div class="nav">
    <button class="active" onclick="navigate('dashboard',this)">📊 Dashboard</button>
    <button onclick="navigate('patients',this)">👥 Patients</button>
    <button onclick="navigate('appointments',this)">📅 Appointments</button>
  </div>

  <div class="sidebar-foot">
    DentalCare Pro<br>
    Local browser application
  </div>
</aside>

<main class="main">

<header class="top">
  <div>
    <h1 id="pageTitle">Dashboard</h1>
    <p id="pageSubtitle">Premium dental clinic management</p>
  </div>

  <button class="btn" onclick="newPatient()">+ New Patient</button>
</header>

<!-- DASHBOARD -->

<section id="dashboard" class="page active">

<div class="grid">

<div class="card stat">
<small>Total Patients</small>
<strong id="totalPatients">0</strong>
</div>

<div class="card stat">
<small>Appointments Today</small>
<strong id="todayAppointments">0</strong>
</div>

<div class="card stat">
<small>Open Treatments</small>
<strong id="openTreatments">0</strong>
</div>

<div class="card stat">
<small>X-rays Stored</small>
<strong id="totalXrays">0</strong>
</div>

</div>

<div class="card section">

<div class="section-head">
<h2>Upcoming Appointments</h2>
<button class="btn secondary" onclick="navigate('appointments')">
View All
</button>
</div>

<div class="table-wrap">
<table class="table">
<thead>
<tr>
<th>Date</th>
<th>Time</th>
<th>Patient</th>
<th>Doctor</th>
<th>Purpose</th>
<th>Status</th>
</tr>
</thead>

<tbody id="dashboardAppointments"></tbody>

</table>
</div>

</div>

<div class="card section">

<div class="section-head">
<h2>Recent Patients</h2>
<button class="btn secondary" onclick="navigate('patients')">
Patients
</button>
</div>

<div class="table-wrap">

<table class="table">

<thead>
<tr>
<th>Name</th>
<th>Phone</th>
<th>Last Visit</th>
<th></th>
</tr>
</thead>

<tbody id="recentPatients"></tbody>

</table>

</div>
</div>

</section>


<!-- PATIENTS -->

<section id="patients" class="page">

<div class="card">

<div class="section-head">

<h2>Patient Database</h2>

<input
id="patientSearch"
class="search"
placeholder="Search name, phone or ID"
oninput="renderPatients()">

</div>

<div class="table-wrap">

<table class="table">

<thead>
<tr>
<th>ID</th>
<th>Patient</th>
<th>Phone</th>
<th>DOB</th>
<th>Last Visit</th>
<th>Action</th>
</tr>
</thead>

<tbody id="patientTable"></tbody>

</table>

</div>

</div>

</section>


<!-- APPOINTMENTS -->

<section id="appointments" class="page">

<div class="card">

<div class="section-head">

<h2>Appointments</h2>

<button class="btn" onclick="newAppointment()">
+ Appointment
</button>

</div>

<div class="table-wrap">

<table class="table">

<thead>
<tr>
<th>Date</th>
<th>Time</th>
<th>Patient</th>
<th>Doctor</th>
<th>Purpose</th>
<th>Status</th>
<th></th>
</tr>
</thead>

<tbody id="appointmentTable"></tbody>

</table>

</div>

</div>

</section>

</main>


<nav class="mobile-nav">

<button class="active" onclick="navigate('dashboard',this)">
📊<br>Home
</button>

<button onclick="navigate('patients',this)">
👥<br>Patients
</button>

<button onclick="navigate('appointments',this)">
📅<br>Appointments
</button>

</nav>


<!-- PATIENT MODAL -->

<div class="modal" id="patientModal">

<div class="modal-box">

<div class="modal-head">

<h2 id="recordTitle">Patient Record</h2>

<button class="btn secondary no-print" onclick="printPatientReport()">
🖨 Print Report
</button>

<button class="close" onclick="closeModal('patientModal')">
×
</button>

</div>


<div class="tabs">

<button class="active" onclick="openTab('chart',this)">
🦷 Dental Chart
</button>

<button onclick="openTab('history',this)">
📋 Treatment History
</button>

<button onclick="openTab('xray',this)">
🩻 X-rays
</button>

<button onclick="openTab('plan',this)">
📝 Treatment Plan
</button>

<button onclick="openTab('information',this)">
👤 Patient Information
</button>

</div>


<!-- CHART -->

<div id="chart" class="pane active">

<div class="card">

<h3>FDI World Dental Federation Tooth Numbering</h3>

<div id="upperTeeth" class="tooth-grid"></div>

<div id="lowerTeeth" class="tooth-grid"></div>

</div>

</div>


<!-- HISTORY -->

<div id="history" class="pane">

<div class="card">

<h3>Add Treatment History</h3>

<br>

<div class="form">

<div>
<label>Date</label>
<input id="historyDate" type="date">
</div>

<div>
<label>Doctor</label>
<input id="historyDoctor">
</div>

<div>
<label>Tooth (FDI)</label>
<input id="historyTooth" placeholder="36">
</div>

<div>
<label>Treatment</label>
<input id="historyTreatment" placeholder="Composite restoration">
</div>

<div class="full">
<label>Clinical Notes</label>
<textarea id="historyNotes"></textarea>
</div>

</div>

<br>

<button class="btn" onclick="addTreatmentHistory()">
Add Treatment
</button>

</div>

<div id="historyList"></div>

</div>


<!-- XRAY -->

<div id="xray" class="pane">

<div class="card">

<h3>Dental X-ray Upload</h3>

<br>

<div class="form three">

<div>
<label>X-ray Image</label>
<input id="xrayFile" type="file" accept="image/*">
</div>

<div>
<label>Type</label>
<select id="xrayType">
<option>Panoramic</option>
<option>Periapical</option>
<option>Bitewing</option>
<option>CBCT</option>
<option>Other</option>
</select>
</div>

<div>
<label>Date</label>
<input id="xrayDate" type="date">
</div>

</div>

<br>

<button class="btn" onclick="uploadXray()">
Upload X-ray
</button>

</div>

<div id="xrayList" class="xray-grid"></div>

</div>


<!-- PLAN -->

<div id="plan" class="pane">

<div class="card">

<h3>Treatment Plan</h3>

<br>

<div id="planRows"></div>

<button class="btn secondary" onclick="addPlanRow()">
+ Add Treatment
</button>

<button class="btn" onclick="saveTreatmentPlan()">
Save Plan
</button>

</div>

</div>


<!-- INFORMATION -->

<div id="information" class="pane">

<div class="card">

<h3>Patient Information</h3>

<br>

<div class="form">

<div>
<label>Full Name</label>
<input id="patientName">
</div>

<div>
<label>Phone</label>
<input id="patientPhone">
</div>

<div>
<label>Date of Birth</label>
<input id="patientDob" type="date">
</div>

<div>
<label>Gender</label>
<select id="patientGender">
<option>Not specified</option>
<option>Male</option>
<option>Female</option>
<option>Other</option>
</select>
</div>

<div class="full">
<label>Address</label>
<input id="patientAddress">
</div>

<div class="full">
<label>Medical / General Notes</label>
<textarea id="patientNotes"></textarea>
</div>

</div>

<br>

<button class="btn" onclick="savePatientInformation()">
Save Patient
</button>

</div>

</div>

</div>

</div>


<!-- APPOINTMENT MODAL -->

<div class="modal" id="appointmentModal">

<div class="modal-box" style="max-width:650px">

<div class="modal-head">

<h2>New Appointment</h2>

<button class="close" onclick="closeModal('appointmentModal')">
×
</button>

</div>

<div style="padding:20px">

<div class="form">

<div>
<label>Patient</label>
<select id="appointmentPatient"></select>
</div>

<div>
<label>Doctor</label>
<input id="appointmentDoctor">
</div>

<div>
<label>Date</label>
<input id="appointmentDate" type="date">
</div>

<div>
<label>Time</label>
<input id="appointmentTime" type="time">
</div>

<div>
<label>Purpose</label>
<input id="appointmentPurpose" placeholder="Check-up, extraction...">
</div>

<div>
<label>Status</label>
<select id="appointmentStatus">
<option>Scheduled</option>
<option>Completed</option>
<option>Cancelled</option>
</select>
</div>

</div>

<br>

<button class="btn" onclick="saveAppointment()">
Save Appointment
</button>

</div>

</div>

</div>


<!-- PRINT REPORT -->

<div id="printReport" class="print-report">

<h1>Dental Patient Report</h1>

<div id="printPatientInformation"></div>

<h2>Dental Chart</h2>
<div id="printDentalChart"></div>

<h2>Treatment History</h2>
<div id="printTreatmentHistory"></div>

<h2>Treatment Plan</h2>
<div id="printTreatmentPlan"></div>

<h2>X-rays</h2>
<div id="printXrays"></div>

</div>


<div class="toast" id="toast"></div>


<script>

const today = new Date().toISOString().slice(0,10);

const FDI_TEETH = [
18,17,16,15,14,13,12,11,
21,22,23,24,25,26,27,28,
48,47,46,45,44,43,42,41,
31,32,33,34,35,36,37,38
];

let patients =
JSON.parse(localStorage.getItem("dentalcare_patients") || "[]");

let appointments =
JSON.parse(localStorage.getItem("dentalcare_appointments") || "[]");

let currentPatientId = null;


function saveDatabase(){

localStorage.setItem(
"dentalcare_patients",
JSON.stringify(patients)
);

localStorage.setItem(
"dentalcare_appointments",
JSON.stringify(appointments)
);

updateDashboard();

}


function showToast(message){

const toast=document.getElementById("toast");

toast.textContent=message;

toast.style.display="block";

setTimeout(()=>{
toast.style.display="none";
},1800);

}


function navigate(page,button){

document.querySelectorAll(".page")
.forEach(p=>p.classList.remove("active"));

document.getElementById(page)
.classList.add("active");

document.querySelectorAll(".nav button,.mobile-nav button")
.forEach(b=>b.classList.remove("active"));

if(button) button.classList.add("active");

document.getElementById("pageTitle")
.textContent =
page.charAt(0).toUpperCase()+page.slice(1);

document.getElementById("pageSubtitle")
.textContent =
page==="dashboard"
?"Premium dental clinic management"
:"Manage your clinic records";

updateDashboard();

}


function closeModal(id){

document.getElementById(id)
.classList.remove("open");

}


function openTab(tab,button){

document.querySelectorAll(".pane")
.forEach(p=>p.classList.remove("active"));

document.getElementById(tab)
.classList.add("active");

document.querySelectorAll(".tabs button")
.forEach(b=>b.classList.remove("active"));

button.classList.add("active");

}


function newPatient(){

currentPatientId=null;

document.getElementById("recordTitle")
.textContent="New Patient";

setPatientFields({});

document.querySelectorAll(".tabs button")
.forEach((b,i)=>b.classList.toggle("active",i===4));

document.querySelectorAll(".pane")
.forEach(p=>p.classList.remove("active"));

document.getElementById("information")
.classList.add("active");

document.getElementById("patientModal")
.classList.add("open");

}


function openPatient(id){

currentPatientId=id;

const patient=patients.find(p=>p.id===id);

if(!patient)return;

document.getElementById("recordTitle")
.textContent=patient.name+" — Patient Record";

setPatientFields(patient);

renderDentalChart();
renderTreatmentHistory();
renderXrays();
renderTreatmentPlan();

openTab(
"chart",
document.querySelector(".tabs button")
);

document.getElementById("patientModal")
.classList.add("open");

}


function setPatientFields(patient){

document.getElementById("patientName").value =
patient.name || "";

document.getElementById("patientPhone").value =
patient.phone || "";

document.getElementById("patientDob").value =
patient.dob || "";

document.getElementById("patientGender").value =
patient.gender || "Not specified";

document.getElementById("patientAddress").value =
patient.address || "";

document.getElementById("patientNotes").value =
patient.notes || "";

}


function savePatientInformation(){

let patient;

if(currentPatientId){

patient=patients.find(
p=>p.id===currentPatientId
);

}else{

patient={
id:"P"+Date.now().toString().slice(-6),
name:"",
phone:"",
dob:"",
gender:"Not specified",
address:"",
notes:"",
lastVisit:"",
toothChart:{},
history:[],
xrays:[],
plan:[]
};

patients.unshift(patient);

currentPatientId=patient.id;

}

patient.name =
document.getElementById("patientName")
.value.trim() || "Unnamed Patient";

patient.phone =
document.getElementById("patientPhone").value;

patient.dob =
document.getElementById("patientDob").value;

patient.gender =
document.getElementById("patientGender").value;

patient.address =
document.getElementById("patientAddress").value;

patient.notes =
document.getElementById("patientNotes").value;

saveDatabase();

document.getElementById("recordTitle")
.textContent=patient.name+" — Patient Record";

showToast("Patient information saved");

}


function renderDentalChart(){

const patient=patients.find(
p=>p.id===currentPatientId
);

if(!patient)return;

patient.toothChart=patient.toothChart||{};

function buildChart(element,start,end){

document.getElementById(element).innerHTML =
FDI_TEETH.slice(start,end).map(tooth=>{

const condition =
patient.toothChart[tooth] || "";

const className =
condition==="Missing"
?"missing"
:condition
?"treated"
:"";

return `

<div class="tooth ${className}">

<b>${tooth}</b>

<select
onchange="updateTooth(${tooth},this.value)">

<option value="">Healthy</option>

<option ${condition==="Caries"?"selected":""}>
Caries
</option>

<option ${condition==="Restored"?"selected":""}>
Restored
</option>

<option ${condition==="Missing"?"selected":""}>
Missing
</option>

<option ${condition==="Root Canal"?"selected":""}>
Root Canal
</option>

<option ${condition==="Crown"?"selected":""}>
Crown
</option>

<option ${condition==="Extraction Planned"?"selected":""}>
Extraction Planned
</option>

</select>

</div>

`;

}).join("");

}

buildChart("upperTeeth",0,16);

buildChart("lowerTeeth",16,32);

}


function updateTooth(tooth,value){

const patient=patients.find(
p=>p.id===currentPatientId
);

patient.toothChart=patient.toothChart||{};

if(value)
patient.toothChart[tooth]=value;
else
delete patient.toothChart[tooth];

saveDatabase();

renderDentalChart();

}


function addTreatmentHistory(){

const patient=patients.find(
p=>p.id===currentPatientId
);

if(!patient)return;

const treatment =
document.getElementById("historyTreatment")
.value.trim();

if(!treatment){

showToast("Enter a treatment");

return;

}

patient.history=patient.history||[];

patient.history.unshift({

date:
document.getElementById("historyDate").value
||today,

doctor:
document.getElementById("historyDoctor").value,

tooth:
document.getElementById("historyTooth").value,

treatment:treatment,

notes:
document.getElementById("historyNotes").value

});

patient.lastVisit=today;

saveDatabase();

document.getElementById("historyDoctor").value="";
document.getElementById("historyTooth").value="";
document.getElementById("historyTreatment").value="";
document.getElementById("historyNotes").value="";

renderTreatmentHistory();

showToast("Treatment history added");

}


function renderTreatmentHistory(){

const patient=patients.find(
p=>p.id===currentPatientId
);

const history=patient?.history||[];

document.getElementById("historyList")
.innerHTML=history.map((item,index)=>`

<div class="history-row">

<div>

<b>${item.treatment}</b>

${item.tooth
?" · Tooth "+item.tooth
:""}

<br>

<small>
${item.date}
· ${item.doctor||"No doctor"}
${item.notes?" · "+item.notes:""}
</small>

</div>

<button
class="btn danger"
onclick="deleteHistory(${index})">

Delete

</button>

</div>

`).join("") ||

'<div class="empty">No treatment history.</div>';

}


function deleteHistory(index){

const patient=patients.find(
p=>p.id===currentPatientId
);

patient.history.splice(index,1);

saveDatabase();

renderTreatmentHistory();

}


function uploadXray(){

const file =
document.getElementById("xrayFile")
.files[0];

if(!file){

showToast("Choose an X-ray image");

return;

}

const reader=new FileReader();

reader.onload=function(){

const patient=patients.find(
p=>p.id===currentPatientId
);

patient.xrays=patient.xrays||[];

patient.xrays.unshift({

name:file.name,

type:
document.getElementById("xrayType").value,

date:
document.getElementById("xrayDate").value||today,

data:reader.result

});

saveDatabase();

document.getElementById("xrayFile").value="";

renderXrays();

showToast("X-ray uploaded");

};

reader.readAsDataURL(file);

}


function renderXrays(){

const patient=patients.find(
p=>p.id===currentPatientId
);

const xrays=patient?.xrays||[];

document.getElementById("xrayList")
.innerHTML=xrays.map((x,index)=>`

<div class="xray">

<img src="${x.data}" alt="Dental X-ray">

<div class="xray-info">

<b>${x.type}</b>

<br>${x.date}

<br>${x.name}

<br><br>

<button
class="btn danger"
onclick="deleteXray(${index})">

Delete

</button>

</div>

</div>

`).join("") ||

'<div class="empty">No X-rays uploaded.</div>';

}


function deleteXray(index){

const patient=patients.find(
p=>p.id===currentPatientId
);

patient.xrays.splice(index,1);

saveDatabase();

renderXrays();

}


function addPlanRow(data={}){

const row=document.createElement("div");

row.className="plan-row";

row.innerHTML=`

<input
placeholder="Treatment"
value="${data.treatment||""}">

<input
placeholder="FDI tooth"
value="${data.tooth||""}">

<select>

<option ${data.status==="Planned"?"selected":""}>
Planned
</option>

<option ${data.status==="In Progress"?"selected":""}>
In Progress
</option>

<option ${data.status==="Completed"?"selected":""}>
Completed
</option>

</select>

<button
class="btn danger"
onclick="this.parentElement.remove()">

×

</button>

`;

document.getElementById("planRows")
.appendChild(row);

}


function renderTreatmentPlan(){

const patient=patients.find(
p=>p.id===currentPatientId
);

document.getElementById("planRows").innerHTML="";

(patient?.plan||[]).forEach(addPlanRow);

if(!(patient?.plan||[]).length)
addPlanRow();

}


function saveTreatmentPlan(){

const patient=patients.find(
p=>p.id===currentPatientId
);

const rows=
document.querySelectorAll(".plan-row");

patient.plan=
[...rows]
.map(row=>({

treatment:row.children[0].value,

tooth:row.children[1].value,

status:row.children[2].value

}))
.filter(x=>x.treatment);

saveDatabase();

showToast("Treatment plan saved");

}


function newAppointment(){

document.getElementById("appointmentPatient")
.innerHTML=patients.map(p=>`

<option value="${p.id}">
${p.name} (${p.id})
</option>

`).join("") ||
"<option>No patients</option>";

document.getElementById("appointmentDate")
.value=today;

document.getElementById("appointmentTime")
.value="09:00";

document.getElementById("appointmentDoctor").value="";
document.getElementById("appointmentPurpose").value="";

document.getElementById("appointmentModal")
.classList.add("open");

}


function saveAppointment(){

appointments.push({

id:Date.now(),

patientId:
document.getElementById("appointmentPatient")
.value,

doctor:
document.getElementById("appointmentDoctor")
.value,

date:
document.getElementById("appointmentDate")
.value,

time:
document.getElementById("appointmentTime")
.value,

purpose:
document.getElementById("appointmentPurpose")
.value,

status:
document.getElementById("appointmentStatus")
.value

});

saveDatabase();

closeModal("appointmentModal");

showToast("Appointment saved");

}


function renderPatients(){

const search =
(document.getElementById("patientSearch")
.value||"")
.toLowerCase();

const list=patients.filter(patient=>
(
patient.name+" "+
patient.phone+" "+
patient.id
)
.toLowerCase()
.includes(search)
);

document.getElementById("patientTable")
.innerHTML=list.map(patient=>`

<tr>

<td>${patient.id}</td>

<td><b>${patient.name}</b></td>

<td>${patient.phone||"—"}</td>

<td>${patient.dob||"—"}</td>

<td>${patient.lastVisit||"—"}</td>

<td>

<button
class="btn"
onclick="openPatient('${patient.id}')">

Open Record

</button>

</td>

</tr>

`).join("") ||

'<tr><td colspan="6" class="empty">No patients found.</td></tr>';

}


function renderAppointments(){

const sorted=[...appointments]
.sort((a,b)=>
(a.date+a.time)
.localeCompare(b.date+b.time)
);

document.getElementById("appointmentTable")
.innerHTML=sorted.map(item=>{

const patient=patients.find(
p=>p.id===item.patientId
);

return `

<tr>

<td>${item.date}</td>

<td>${item.time}</td>

<td>${patient?.name||"Unknown"}</td>

<td>${item.doctor||"—"}</td>

<td>${item.purpose||"—"}</td>

<td>

<span class="badge
${item.status==="Completed"?"green":
item.status==="Cancelled"?"red":""}">

${item.status}

</span>

</td>

<td>

<button
class="btn danger"
onclick="deleteAppointment(${item.id})">

Delete

</button>

</td>

</tr>

`;

}).join("") ||

'<tr><td colspan="7" class="empty">No appointments.</td></tr>';

}


function deleteAppointment(id){

appointments=
appointments.filter(x=>x.id!==id);

saveDatabase();

}


function updateDashboard(){

document.getElementById("totalPatients")
.textContent=patients.length;

document.getElementById("todayAppointments")
.textContent=
appointments.filter(x=>
x.date===today &&
x.status!=="Cancelled"
).length;

document.getElementById("openTreatments")
.textContent=
patients.reduce(
(total,p)=>
total+
(p.plan||[])
.filter(x=>x.status!=="Completed").length,
0
);

document.getElementById("totalXrays")
.textContent=
patients.reduce(
(total,p)=>total+(p.xrays||[]).length,
0
);


const upcoming=
appointments
.filter(x=>
x.date>=today &&
x.status!=="Cancelled"
)
.sort((a,b)=>
(a.date+a.time)
.localeCompare(b.date+b.time)
)
.slice(0,5);

document.getElementById("dashboardAppointments")
.innerHTML=upcoming.map(item=>{

const patient=patients.find(
p=>p.id===item.patientId
);

return `

<tr>

<td>${item.date}</td>
<td>${item.time}</td>
<td>${patient?.name||"Unknown"}</td>
<td>${item.doctor||"—"}</td>
<td>${item.purpose||"—"}</td>

<td>
<span class="badge">
${item.status}
</span>
</td>

</tr>

`;

}).join("") ||

'<tr><td colspan="6" class="empty">No upcoming appointments.</td></tr>';


document.getElementById("recentPatients")
.innerHTML=patients.slice(0,5).map(patient=>`

<tr>

<td>${patient.name}</td>

<td>${patient.phone||"—"}</td>

<td>${patient.lastVisit||"—"}</td>

<td>

<button
class="btn"
onclick="openPatient('${patient.id}')">

Open

</button>

</td>

</tr>

`).join("") ||

'<tr><td colspan="4" class="empty">No patients yet.</td></tr>';

renderPatients();
renderAppointments();

}


function printPatientReport(){

const patient=patients.find(
p=>p.id===currentPatientId
);

if(!patient)return;


document.getElementById("printPatientInformation")
.innerHTML=`

<p>
<b>Name:</b> ${patient.name}
&nbsp;&nbsp;
<b>ID:</b> ${patient.id}
&nbsp;&nbsp;
<b>Phone:</b> ${patient.phone||"—"}
</p>

<p>
<b>Date of Birth:</b> ${patient.dob||"—"}
&nbsp;&nbsp;
<b>Gender:</b> ${patient.gender||"—"}
</p>

<p>
<b>Address:</b> ${patient.address||"—"}
</p>

<p>
<b>Medical / General Notes:</b>
${patient.notes||"—"}
</p>

`;


document.getElementById("printDentalChart")
.innerHTML=FDI_TEETH.map(tooth=>`

<span style="
display:inline-block;
padding:6px;
margin:3px;
border:1px solid #aaa;
border-radius:5px">

<b>${tooth}</b>:
${patient.toothChart?.[tooth]||"Healthy"}

</span>

`).join("");


document.getElementById("printTreatmentHistory")
.innerHTML=(patient.history||[]).map(item=>`

<p>

<b>${item.date} — ${item.treatment}</b>

${item.tooth?
" · Tooth "+item.tooth:
""}

<br>

${item.doctor||""}

<br>

${item.notes||""}

</p>

`).join("")||"No treatment history.";


document.getElementById("printTreatmentPlan")
.innerHTML=(patient.plan||[]).map(item=>`

<p>

<b>${item.treatment}</b>

${item.tooth?
" · Tooth "+item.tooth:
""}

— ${item.status}

</p>

`).join("")||"No treatment plan.";


document.getElementById("printXrays")
.innerHTML=(patient.xrays||[]).map(x=>`

<p>
<b>${x.type}</b>
— ${x.date}
— ${x.name}
</p>

`).join("")||"No X-rays uploaded.";


setTimeout(()=>{
window.print();
},100);

}


document.getElementById("historyDate").value=today;
document.getElementById("xrayDate").value=today;

updateDashboard();

</script>

</body>
</html>