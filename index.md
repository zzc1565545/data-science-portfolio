---
layout: default
---
<section class="hero">
  <p class="eyebrow">Data science portfolio / 01</p>
  <h1>Make the comparison.<br><em>Keep the context.</em></h1>
  <div class="intro-grid">
    <div><h2>ZHU ZHICHENG</h2><p>I am developing my data analysis and visualization skills through CISC7204 coursework. This portfolio connects a focused question to readable charts, reproducible code and explicit limitations.</p></div>
    <div class="skills"><p class="label">Skills practiced in this project</p><ul><li>Python &amp; reproducible scripts</li><li>Matplotlib &amp; visual comparison</li><li>Data validation &amp; unit tests</li><li>GitHub &amp; technical documentation</li></ul></div>
  </div>
</section>

<section id="project" class="project-section">
  <div class="section-top"><p class="eyebrow">Selected project / campus commute</p><span class="status">Ongoing · classmate review addressed</span></div>
  <h2 class="section-title">Fast on a typical day.<br>But how much time should you allow?</h2>
  <p class="lead">How does the ranking of four travel modes change when we compare typical journey time with a slower-journey benchmark?</p>
  <aside class="data-note"><strong>Hypothetical data, not a transport study.</strong> These eight time values are hand-assigned for a design exercise. No journeys were observed, and the results are not recommendations about University of Macau transport.</aside>
  <figure>
    <img src="assets/commute-times.png" alt="Connected-dot plot of assumed P50 and P90 journey times in minutes: bicycle 14 and 20, public bus 18 and 38, campus shuttle 20 and 30, walking 25 and 28." width="2160" height="1368">
    <figcaption><span>01 / Typical and slower journeys</span> P50 is the median. P90 is a time threshold within which at least 90% of journeys would finish under the assumed distribution; it is not a guarantee.</figcaption>
  </figure>
  <div class="finding"><p class="label">The finding</p><p>The bus is <strong>7 minutes faster</strong> than walking at the median, but <strong>10 minutes longer</strong> at P90. Looking only at the typical trip changes the comparison.</p></div>
  <aside class="data-note" aria-labelledby="ranking-title">
    <strong id="ranking-title">What changes in the ranking?</strong>
    <p><b>At P50, fastest to slowest:</b> Bicycle (14) → Public bus (18) → Campus shuttle (20) → Walking (25).</p>
    <p><b>At P90, fastest to slowest:</b> Bicycle (20) → Walking (28) → Campus shuttle (30) → Public bus (38).</p>
    <div class="table-wrap" tabindex="0" role="region" aria-label="Comparison of P50 and P90 rankings">
      <table>
        <caption>Rank changes at a glance — rank 1 is fastest at that benchmark</caption>
        <thead><tr><th scope="col">Mode</th><th scope="col">P50 rank</th><th scope="col">P90 rank</th><th scope="col">Change</th></tr></thead>
        <tbody>
          <tr><th scope="row">Bicycle</th><td>1st</td><td>1st</td><td>No change</td></tr>
          <tr><th scope="row">Public bus</th><td>2nd</td><td>4th</td><td>Down 2 places</td></tr>
          <tr><th scope="row">Campus shuttle</th><td>3rd</td><td>3rd</td><td>No change</td></tr>
          <tr><th scope="row">Walking</th><td>4th</td><td>2nd</td><td>Up 2 places</td></tr>
        </tbody>
      </table>
    </div>
    <p>All values are assumed minutes. Walking moves from fourth to second, while the bus moves from second to fourth. This compares the supplied reference points, not the chance of one mode beating another on an actual journey.</p>
  </aside>
  <figure class="secondary">
    <img src="assets/extra-allowance.png" alt="Bar chart of the assumed P90 minus P50 time allowance: public bus 20 minutes, campus shuttle 10, bicycle 6, walking 3. These gaps do not describe the complete distributions." width="2160" height="1368" loading="lazy">
    <figcaption><span>02 / Extra allowance beyond typical time</span> Sorting the gaps makes the additional allowance easy to compare. A short gap does not establish low variance or eliminate extreme delays.</figcaption>
  </figure>
  <a class="button" href="https://github.com/zzc1565545/data-science-project">Explore code, data and README <span aria-hidden="true">↗</span></a>
  <details class="data-table"><summary>Read the values as a table</summary><div class="table-wrap"><table><caption>Assumed door-to-door journey times (minutes)</caption><thead><tr><th scope="col">Mode</th><th scope="col">P50</th><th scope="col">P90</th><th scope="col">P90 − P50</th></tr></thead><tbody><tr><th scope="row">Bicycle</th><td>14</td><td>20</td><td>6</td></tr><tr><th scope="row">Public bus</th><td>18</td><td>38</td><td>20</td></tr><tr><th scope="row">Campus shuttle</th><td>20</td><td>30</td><td>10</td></tr><tr><th scope="row">Walking</th><td>25</td><td>28</td><td>3</td></tr></tbody></table></div></details>
</section>

<section id="methods" class="methods-section">
  <p class="eyebrow">How the result can be checked</p>
  <div class="method-grid"><div><h2>Small inputs.<br>Visible decisions.</h2><p>The project extends a static visualization exercise into a documented Python analysis. It reads a small JSON dataset, validates each pair of quantiles, calculates P90 minus P50, and creates both charts and a machine-readable summary.</p><p>The first chart preserves the actual time values; the second isolates their differences. Neither chart uses a truncated scale or estimates an unknown distribution.</p></div>
  <div class="reproduce"><p class="label">Reproduce locally</p><pre><code>python -m pip install -r requirements.txt
python analysis.py
python -m unittest -v</code></pre><p>Run these commands inside the project repository with Python 3.11 or later. The analysis uses only the bundled hypothetical data; no login, API key or data download is needed.</p><a href="https://github.com/zzc1565545/data-science-project#reproduce">Full reproduction instructions →</a></div></div>
  <div class="limitation"><p class="label">One important limitation</p><p>Two assumed quantiles cannot establish the full spread of journey times or the probability of being late. The comparison also leaves out cost, weather, safety, accessibility and service schedules. Real travel advice would need comparable observations and a different study design.</p></div>
</section>

<section id="next" class="next-section">
  <p class="eyebrow">Review and next steps</p><h2>Make the changing ranks visible.</h2>
  <p>A classmate identified the question, the bus-versus-walking finding and the hypothetical-data limitation. Their suggestion was to show the complete P50 and P90 rankings so readers can see which positions change. The page already contained written rankings; in this follow-up, I added a side-by-side table with each mode's two ranks and its movement. The <a href="https://github.com/zzc1565545/data-science-portfolio/blob/main/PEER_REVIEW.md">classmate feedback record</a> documents the suggestion and this new improvement.</p>
  <p>Longer term, I would replace the assumed values with consented, comparable observations and examine full distributions before drawing practical conclusions.</p>
  <p class="ai-note"><strong>AI assistance:</strong> OpenAI Codex assisted with code, visualization design, drafting and checks. The work is presented as AI-assisted coursework, not as an independently conducted transport survey.</p>
</section>
