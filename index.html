<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Real-Time Acceleration Graph</title>
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-database.js"></script>
    <script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.16.9/xlsx.full.min.js"></script>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; background: #f4f4f4; }
        h2 { color: #333; }
        #chart_div { width: 100%; height: 400px; margin: auto; background: white; padding: 10px; border-radius: 8px; }
        button { padding: 10px 15px; margin: 10px; border: none; cursor: pointer; font-size: 16px; }
        #download { background: green; color: white; }
        #refresh { background: blue; color: white; }
    </style>
</head>
<body>

    <h2>Real-Time X-Axis Acceleration Graph</h2>
    <p>Latest Value: <span id="latestValue">Loading...</span> g</p>
    <p>Last Timestamp: <span id="lastTimestamp">Loading...</span></p>

    <div id="chart_div"></div>
    
    <button id="download">Download Data (Excel)</button>
    <button id="refresh">Refresh</button>

    <script>
        // Firebase Configuration (UPDATE with your credentials)
      const firebaseConfig = {
  apiKey: "AIzaSyCxrkRZ2sTwg8fivnLpzzCTLtrV3sY22wk",
  authDomain: "gload-9bbb7.firebaseapp.com",
  databaseURL: "https://gload-9bbb7-default-rtdb.asia-southeast1.firebasedatabase.app",
  projectId: "gload-9bbb7",
  storageBucket: "gload-9bbb7.firebasestorage.app",
  messagingSenderId: "906599077982",
  appId: "1:906599077982:web:c40399c0ff5f789abf3ccf"

};
       
        firebase.initializeApp(firebaseConfig);
        var database = firebase.database();

        // Load Google Charts
        google.charts.load('current', { packages: ['corechart', 'line'] });
        google.charts.setOnLoadCallback(drawChart);

        var chartData = [['Timestamp', 'Acceleration (g)']];
        var chart;
        var options = {
            title: 'Real-Time Acceleration Data',
            curveType: 'function',
            legend: { position: 'bottom' },
            hAxis: { title: 'Time' },
            vAxis: { title: 'Acceleration (g)', minValue: -2, maxValue: 2 }
        };

        function drawChart() {
            var data = google.visualization.arrayToDataTable(chartData);
            chart = new google.visualization.LineChart(document.getElementById('chart_div'));
            chart.draw(data, options);
        }

        function fetchData() {
            database.ref('/acceleration/data').limitToLast(20).on('value', function(snapshot) {
                if (snapshot.exists()) {
                    chartData = [['Timestamp', 'Acceleration (g)']];
                    snapshot.forEach(function(childSnapshot) {
                        var timestamp = new Date(parseInt(childSnapshot.key)).toLocaleTimeString();
                        var value = childSnapshot.val();
                        chartData.push([timestamp, value]);
                    });
                    drawChart();
                }
            });

            database.ref('/acceleration/last_value').on('value', function(snapshot) {
                if (snapshot.exists()) {
                    document.getElementById("latestValue").innerText = snapshot.val() + " g";
                }
            });

            database.ref('/acceleration/last_timestamp').on('value', function(snapshot) {
                if (snapshot.exists()) {
                    var lastTimestamp = new Date(parseInt(snapshot.val())).toLocaleString();
                    document.getElementById("lastTimestamp").innerText = lastTimestamp;
                }
            });
        }

        document.getElementById("refresh").addEventListener("click", function() {
            fetchData();
        });

        document.getElementById("download").addEventListener("click", function() {
            database.ref('/acceleration/data').once('value', function(snapshot) {
                if (snapshot.exists()) {
                    var ws_data = [["Timestamp", "Acceleration (g)"]];
                    snapshot.forEach(function(childSnapshot) {
                        ws_data.push([new Date(parseInt(childSnapshot.key)).toLocaleString(), childSnapshot.val()]);
                    });
                    var wb = XLSX.utils.book_new();
                    var ws = XLSX.utils.aoa_to_sheet(ws_data);
                    XLSX.utils.book_append_sheet(wb, ws, "AccelerationData");
                    XLSX.writeFile(wb, "Acceleration_Data.xlsx");
                } else {
                    alert("No data available to download.");
                }
            });
        });

        fetchData();
    </script>

</body>
</html>
