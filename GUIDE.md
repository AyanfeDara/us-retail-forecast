# Build guide: US retail sales forecast (R)

**Business question:** which US store types will grow over the next 12 months, and how far can a forecast be trusted?

**Result:** a Quarto report (`retail_forecast.html`) with the analysis, four charts, and a README with findings. Time: 2 to 3 sessions.

---

## 1. Put the folder in place (2 minutes)

Unzip `us-retail-forecast` into your `Project Portfolio` folder, next to the other three projects.

## 2. Get the data (2 minutes)

1. Open this link in Chrome. It downloads one CSV with all five store types:
   <https://fred.stlouisfed.org/graph/fredgraph.csv?id=MRTSSM722USN,MRTSSM4451USN,MRTSSM448USN,MRTSSM452USN,MRTSSM4541USN>
2. The file arrives in Downloads as `fredgraph.csv`. Move it into the project's `data` folder and rename it to exactly `fred_retail.csv` (turn on **View > Show > File name extensions** first).

Do not open or save it in Excel; Excel can change the date format.

| Series ID | Store type |
| --- | --- |
| MRTSSM722USN | Restaurants and bars (food services and drinking places) |
| MRTSSM4451USN | Grocery stores |
| MRTSSM448USN | Clothing stores |
| MRTSSM452USN | General merchandise stores |
| MRTSSM4541USN | Online and mail-order (electronic shopping and mail-order houses) |

## 3. Open the project in RStudio (2 minutes)

1. In the project folder, double-click `us-retail-forecast.Rproj`. RStudio opens with this folder as its working folder.
2. In the **Files** panel (bottom right), click `retail_forecast.qmd` to open it.

## 4. Run the analysis, one chunk at a time

The report is split into grey **chunks** of code, like Jupyter cells. Run each one with the small green ▶ at its top right, in order from the top. The output appears under the chunk.

Send me a screenshot after these chunks, so we can check the numbers before going on:

| Chunk | What to check |
| --- | --- |
| `load` | Five store types, all starting 2010 Jan; the common last month; no gaps |
| `growth` | The growth table |
| `seasonality` | The two small tables |
| `test-models` | The accuracy table and the average by method (ARIMA takes a minute) |
| `forecast` | The `best` table and the `outlook` table |

If a chunk shows an error, stop and send me a screenshot.

## 5. Write your readings

Three places in the report say **Your reading**. Replace each with two or three sentences in your own words. These become your README findings and your interview answers.

Points to think about:

- **Growth:** growth is in current dollars. Prices rose a lot after 2021, so how much of the growth is real?
- **Methods:** why test on months the model has not seen, rather than on the data it was trained on?
- **Methods:** did the fancy methods beat the simple seasonal naive benchmark everywhere? If not, why might that be?
- **Forecast:** what would a store chain do differently with a forecast that is off by 2% versus 10%?

## 6. Render the report (2 minutes)

Click **Render** at the top of the editor. RStudio runs everything and creates `retail_forecast.html` in the project folder, and it opens in a viewer. This one file holds the full report with code, tables and charts.

## 7. Publish on GitHub

1. Create a new public repository `us-retail-forecast` (README off). Description: *Forecasting US retail sales by store type with R (fable): testing three methods on unseen data and forecasting the next 12 months.*
2. Upload `retail_forecast.qmd`, `retail_forecast.html`, `README.md`, `GUIDE.md`, `us-retail-forecast.Rproj`, and the `data` and `charts` folders.
3. Add `.gitignore` by hand (**Add file > Create new file**), copying this folder's `.gitignore`.
4. Topics: `r`, `forecasting`, `time-series`, `fable`, `tidyverse`, `quarto`, `data-analysis`.

The data is public US Census data, so it can go in the repository.
