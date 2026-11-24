# Playing with chart.js

<div>
  <canvas id="myChart"></canvas>
</div>

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

<script>
  const ctx = document.getElementById('myChart');
  const chartData = {{ site.data.sampleData | jsonify}};

  new Chart(ctx, {
    type: 'line',
    data: {
      labels: chartData.map(x => x.SnapshotDay),
      datasets: [{
        label: 'Available Apartments',
        data: chartData.map(x => x.Inventory),
        borderWidth: 1
      }]
    },
    options: {
      scales: {
        y: {
          beginAtZero: true
        }
      }
    }
  });
</script>
{{ site.data.sampleData | jsonify}};
