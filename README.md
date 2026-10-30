# k6-lab

Performance testing exercises for QuickPizza using Grafana k6.

## Run

Run the Part 0 scripts directly with k6. Part A scripts use the shared
`journey.js` module and keep the public-site limits from the lab: no more than
5 VUs, with the soak test limited to 2 VUs.

HTML reports for Part A are written under `reports/` with the web dashboard
output option, for example:

```powershell
k6 run --out web-dashboard=export=reports/a2-average.html a2-average.js
```
