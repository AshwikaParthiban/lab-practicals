<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Virtual Lab Simulation</title>
<style>
/* ------------------ GLOBAL STYLE ------------------ */
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #eef2f3;
}
header {
    background: #003366;
    color: white;
    padding: 20px;
    text-align: center;
}
.container {
    width: 80%;
    margin: 30px auto;
}

/* ------------------ DASHBOARD ------------------ */
.card {
    background: white;
    padding: 20px;
    border-radius: 10px;
    width: 300px;
    box-shadow: 0 0 10px #aaa;
    margin-bottom: 20px;
}
.btn {
    background: #0077cc;
    color: white;
    padding: 10px 15px;
    text-decoration: none;
    display: inline-block;
    border-radius: 6px;
    margin-top: 10px;
    cursor: pointer;
}
.btn:hover { background: #005fa3; }
.danger { background: #cc0000; }
.danger:hover { background: #990000; }

.hidden { display: none; }

/* ------------------ LAB SIMULATION ------------------ */
#lab-area {
    margin-top: 40px;
    text-align: center;
}
#beaker {
    width: 150px;
    height: 200px;
    border: 4px solid #555;
    margin: 0 auto;
    position: relative;
    border-radius: 0 0 20px 20px;
    background: white;
}
#liquid {
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 0;
    background: #00aaff;
    transition: height 1s ease;
}
.controls {
    margin-top: 20px;
    text-align: center;
}
.backBtn {
    cursor: pointer;
    color: #0077cc;
    font-weight: bold;
    text-decoration: underline;
}
</style>
</head>

<body>

<header>
    <h1>Virtual Science Lab</h1>
</header>

<div class="container">

    <!-- ===================== DASHBOARD PAGE ====================== -->
    <div id="dashboardPage">
        <h2>Dashboard</h2>
        <p>Select a lab activity:</p>

        <div class="card">
            <h3>Chemistry Simulation</h3>
            <p>Mix chemicals and observe reactions.</p>
            <span class="btn" onclick="goToSimulation()">Open Simulation</span>
        </div>
    </div>


    <!-- ===================== SIMULATION PAGE ====================== -->
    <div id="simulationPage" class="hidden">
        <span class="backBtn" onclick="goToDashboard()">← Back to Dashboard</span>

        <h2>Chemistry Virtual Lab</h2>

        <div id="lab-area">
            <div id="beaker">
                <div id="liquid"></div>
            </div>
        </div>

        <div class="controls">
            <button id="startBtn" class="btn">Start Experiment</button>
            <button id="resetBtn" class="btn danger">Reset</button>
        </div>
    </div>

</div>


<!-- ===================== JAVASCRIPT FUNCTIONALITY ====================== -->
<script>
/* Page Navigation */
function goToSimulation() {
    document.getElementById("dashboardPage").classList.add("hidden");
    document.getElementById("simulationPage").classList.remove("hidden");
}
function goToDashboard() {
    document.getElementById("simulationPage").classList.add("hidden");
    document.getElementById("dashboardPage").classList.remove("hidden");
}

/* Lab Simulation Buttons */
document.getElementById("startBtn").addEventListener("click", () => {
    document.getElementById("liquid").style.height = "100%";
});

document.getElementById("resetBtn").addEventListener("click", () => {
    document.getElementById("liquid").style.height = "0%";
});
</script>

</body>
</html>
