
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
 
</head>
<body>

  <h1>Festive Season Vehicle Sales Analysis - India (2025)</h1>
  <p><strong>Short description</strong>: Data-driven analysis of vehicle retail trends during the festive period in India. The project converts raw reports and PDF tables into clean datasets, runs exploratory analysis, and produces visual insights for consulting-style recommendations.</p>

  <div class="section">
    <h2>Project goals</h2>
    <ul>
      <li>Convert industry PDFs and reports into clean CSV/Excel files.</li>
      <li>Explore category-wise retail trends for 2W, 3W, PV, CV and subsegments.</li>
      <li>Visualize month-on-month and year-on-year changes and identify consumer/segment signals.</li>
      <li>Provide concise recommendations for OEMs, dealers and consultants.</li>
    </ul>
  </div>

  <div class="section">
    <h2>Repository structure</h2>
    <pre>
📁 data/              → raw and cleaned datasets (CSV, XLSX)
📁 notebooks/         → Colab / Jupyter notebooks with analysis
📁 visuals/           → exported charts and figures (PNG)
📄 README.html        → this file
    </pre>
  </div>

  <div class="section">
    <h2>Quickstart - run in Google Colab</h2>
    <p>Open a new Colab notebook and run the following steps to reproduce the analysis.</p>

    <ol>
      <li>Upload the project Excel or CSV files to Colab:
        <pre><code>from google.colab import files
uploaded = files.upload()</code></pre>
      </li>
      <li>Install libraries if needed:
        <pre><code>!pip install pandas matplotlib tabula-py camelot-py</code></pre>
        <div class="note">If you use tabula-py you may need to install Java in the Colab environment. For light table extraction consider copying tables into Google Sheets and exporting CSV.</div>
      </li>
      <li>Load data from a sheet:
        <pre><code>import pandas as pd
df_sales = pd.read_excel('Festive_Car_Data.xlsx', sheet_name='Sales')</code></pre>
      </li>
      <li>Run the example chart code (bar, line, stacked) and save PNGs:
        <pre><code>import matplotlib.pyplot as plt
summary = df_sales.groupby('Segment')['UnitsSold'].sum().reset_index()
summary.plot(kind='bar', x='Segment', y='UnitsSold')
plt.savefig('segment_sales.png', dpi=300)</code></pre>
      </li>
    </ol>
  </div>



  <div class="section">
    <h2>Suggested analyses</h2>
    <ul>
      <li>MoM and YoY growth by segment and month.</li>
      <li>Segment share during festival months (stacked charts).</li>
      <li>Correlation of promotional intensity and sales lift.</li>
      <li>Basic clustering for consumer segments using budget and likelihood to purchase.</li>
    </ul>
  </div>

  <div class="section">
    <h2>Visuals and deliverables</h2>
    <ul>
      <li>Charts: category distribution, month trend, stacked segment-month</li>
      <li>Short notebook that transforms PDFs to CSV and generates visuals</li>
      <li>CSV files and small readme explaining how to re-run</li>
    </ul>
  </div>

  <div class="section">
    <h2>Data sources</h2>
    <ul>
      <li>FADA Research - monthly retail reports (https://fada.in/s)</li>
      <li>SIAM - vehicle production and sales reports (https://www.siam.in/statistics.aspx?mpgid=8&pgidtrail=15)</li>
    </ul>
    <p class="note">Please verify source licensing and attribute appropriately when using proprietary data.</p>
  </div>

  <div class="section">
    <h2>How to contribute</h2>
    <p>Contributions are welcome. If you add new data sources or improve extraction scripts, please:</p>
    <ol>
      <li>Fork the repo</li>
      <li>Create a new branch</li>
      <li>Open a pull request with a short description of changes</li>
    </ol>
  </div>

  <div class="section">
    <h2>License</h2>
    <p>Choose a license that fits your goals. For most personal projects MIT is a simple option.</p>
    <pre><code>MIT License</code></pre>
  </div>

  <footer style="margin-top:28px; font-size:0.95em; color:#444;">
    <p>Created by Shreeya • Repo: <strong>festive-vehicle-sales-india</strong></p>
  </footer>

</body>
</html>

