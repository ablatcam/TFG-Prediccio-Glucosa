# TFG: Predicció dels nivells de glucosa en sang en pacients amb diabetis mitjançant models de sèries temporals

**Autor:** Adrián Blat Campos

**Tutors:** Ricardo Sanz Díaz y Alejandro Laguna Sanz

**Universitat:** Universitat de València — Curs 2025-26

## Descripció

El control de la glucosa en sang és essencial per al tractament de la diabetis i la prevenció de complicacions com la hiperglucèmia o la hipoglucèmia. En els últims anys s’ha produït un avanç científic i tecnològic que ha permés que els pacients amb diabetis puguen controlar els seus nivells de glucosa en temps real mitjançant sensors de Monitoratge Continu de Glucosa (MCG). Actualment, gràcies a la intel·ligència artificial és possible predir la glucosa en sang, ajudant d’aquesta manera els pacients a fer un seguiment més fluid i precís.
Aquest treball planteja el desenvolupament i l’avaluació de models predictius de sèries temporals en diferents horitzons de predicció. La investigació estableix inicialment un model de referència bàsic (Baseline), el qual prediu l’últim valor conegut. A partir d’aquest, s’avaluen models autoregressius univariants (ARIMA), analitzant el seu comportament i les seues limitacions davant de canvis bruscos de glucosa. Posteriorment, s’evoluciona cap a models multivariants (ARIMAX) mitjançant l’addició de variables exògenes com la insulina i les ingestes, comparant finalment el rendiment i la viabilitat clínica de cada enfocament lineal i assentant les bases per a la futura implementació d’arquitectures d’aprenentatge profund.

## Estructura del repositori

| Notebook | Contingut |
|---|---|
| `00_analisi_exploratoria.ipynb` | EDA: pèrdua de senyal, continuïtat, llindars, ACF/PACF |
| `01_preprocessat_dades.ipynb` | Extracció XML, neteja, segmentació (llindar 12h) i exportació |
| `02_avaluacio_test_naive.ipynb` | Model Naive (línia base) |
| `03_avaluacio_test_arima.ipynb` | Model ARIMA(1,1,0) amb sliding window |
| `04_avaluacio_test_arimax.ipynb` | Model ARIMAX amb IOB i lags de bolus/carbs |
| `05_avaluacio_i_resultats_finals.ipynb` | Comparativa global, Clarke Error Grid i resultats finals |

Els notebooks inclouen les eixides ja executades (taules i gràfiques), de manera que es poden revisar directament des de GitHub sense necessitat d'executar-los. Els fitxers visuals i mètriques consolidats estan emmagatzemats a `resultats_grafics/` i `resultats_metrics/`.

## Dades

Les dades crues no s'inclouen en aquest repositori. El conjunt de dades utilitzat és l'**OhioT1DM Dataset** (Marling & Bunescu, 2020).

## Requisits

```bash
pip install -r requirements.txt
