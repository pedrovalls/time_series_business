# Time Series Econometrics for Business Research

FGV EAESP — São Paulo School of Business Administration  
MSc / PhD in Business Administration  
**Prof. Pedro Valls Pereira** · pedro.valls@fgv.br

Seven lectures on time series econometrics with applications to finance and marketing.
Each lecture comes with Beamer slides, article-class lecture notes, and an applied tutorial
using publicly available data.

## Citation

To cite this repository, files, or associated materials, use the format shown below, adapting it as needed for the context of your work.

Valls, P. P. (2026). *Time Series Econometrics for Business Research*. https://github.com/pedrovalls/time_series_business.

> @misc{valls2026TimeSeriesEconometricsforBusinessResearch,  
author = {Valls, Pedro P.},  
title = {Time Series Econometrics for Business Research},  
year = {2026},  
howpublished = {\url{https://github.com/pedrovalls/time_series_business}}  
}


## Course website

The course page is served at:  
`https://<your-github-username>.github.io/<repo-name>/`

## Course materials

| Lecture | Topic | Slides | Notes | Tutorial |
|---|---|---|---|---|
| 1 | Stochastic Processes and ARMA Models | [PDF](Lectures/lecture1_beamer.pdf) | [PDF](Notes/lecture1_timeseries.pdf) | [PDF](Tutorials/tutorial1_timeseries.pdf) |
| 2 | Non-Stationarity: Unit Roots and Trends | [PDF](Lectures/lecture2_beamer.pdf) | [PDF](Notes/lecture2_timeseries.pdf) | [PDF](Tutorials/tutorial2_timeseries.pdf) |
| 3 | Dynamic Regression, ECM and Exogeneity | [PDF](Lectures/lecture3_beamer.pdf) | [PDF](Notes/lecture3_timeseries.pdf) | [PDF](Tutorials/tutorial3_timeseries.pdf) |
| 4 | Multivariate Dynamics: VAR, Cointegration and VEC | [PDF](Lectures/lecture4_beamer.pdf) | [PDF](Notes/lecture4_timeseries.pdf) | [PDF](Tutorials/tutorial4_timeseries.pdf) |
| 5 | Structural Breaks, State Space and the Kalman Filter | [PDF](Lectures/lecture5_beamer.pdf) | [PDF](Notes/lecture5_timeseries.pdf) | [PDF](Tutorials/tutorial5_timeseries.pdf) |
| 6 | Volatility Modelling: ARCH, GARCH and DCC | [PDF](Lectures/lecture6_beamer.pdf) | [PDF](Notes/lecture6_timeseries.pdf) | [PDF](Tutorials/tutorial6_timeseries.pdf) |
| 7 | Forecasting and Model Selection | [PDF](Lectures/lecture7_beamer.pdf) | [PDF](Notes/lecture7_timeseries.pdf) | [PDF](Tutorials/tutorial7_timeseries.pdf) |

## Tutorial case studies

| # | Case Study | Area | Data Source |
|---|---|---|---|
| 1 | Modelling daily USD/BRL exchange rate returns (ARMA) | Finance · FX | FRED: `DEXBZUS` |
| 2 | Are commodity prices and the BRL integrated? (Unit roots) | Macro · Commodities | FRED: `DCOILBRENTEU`, `GOLDAMGBD228NLBM`, `DEXBZUS` |
| 3 | Long-run price elasticity in Brazilian retail (ECM) | Marketing · Retail | IBGE PMC + IPCA |
| 4 | Macro-finance linkages: Brazilian business cycle VAR | Macro · Monetary Policy | FRED: `BRAGDPNADSMEI`, `BRACPIALLMINMEI`, `INTDSRBRZQ156N` |
| 5 | Structural breaks in Brazilian inflation (Bai–Perron + IIS) | Macro · Inflation | FRED: `BRACPIALLMINMEI` (1980–2024) |
| 6 | IBOVESPA GARCH, VaR backtesting and DCC | Finance · Equity Risk | Yahoo Finance: `^BVSP`, `^GSPC` |
| 7 | Consumer goods demand forecasting and combination | Marketing · Demand | R `Mcomp` (M3) or Kaggle M5 |

## Repository structure

```
<repo-name>/
├── index.html          ← course website (served by GitHub Pages)
├── README.md
├── .nojekyll           ← disables Jekyll so PDFs are served directly
├── Lectures/           ← Beamer slide PDFs (lecture1_beamer.pdf … lecture7_beamer.pdf)
├── Notes/              ← Article-class lecture notes PDFs (lecture1_timeseries.pdf … )
└── Tutorials/          ← Tutorial PDFs (tutorial1_timeseries.pdf … )
```

## Rebuilding from source

All materials were compiled from LaTeX. To rebuild:

```bash
# Slides (requires preamble.tex in same folder)
cd Lectures && pdflatex lecture1_beamer.tex  # lecture1 is standalone
for i in 2 3 4 5 6 7; do
  cp preamble.tex .
  pdflatex lecture${i}_beamer.tex
  pdflatex lecture${i}_beamer.tex
done

# Notes
cd Notes
for i in 1 2 3 4 5 6 7; do
  pdflatex lecture${i}_timeseries.tex
  pdflatex lecture${i}_timeseries.tex
done

# Tutorials
cd Tutorials
for i in 1 2 3 4 5 6 7; do
  pdflatex tutorial${i}_timeseries.tex
  pdflatex tutorial${i}_timeseries.tex
done
```

## License

© Pedro Valls Pereira · FGV EAESP  
Licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)  
Course material for educational purposes only.
