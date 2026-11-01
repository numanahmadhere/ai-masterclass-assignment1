# Crypto data workflow

**Question:** Which coin was the most volatile over the last 30 days, and is each coin above or below its 30-day average?

This project is for education only and is not financial advice.

## What this repo has

- `crypto_workflow.py`: gets daily candles from the Kraken public API, calculates metrics, applies two rules, and writes a report to `reports/`. It does not call any AI model.
- `.github/workflows/crypto.yml`: runs `crypto_workflow.py` every day on GitHub and saves the report in `reports/`.

## What I learned about the data

(Fill in from your own look at https://api.kraken.com/0/public/OHLC?pair=XBTUSD&interval=1440)

## How to run

1. Install Python 3 and open this folder in VS Code.
2. Install the package: `pip install -r requirements.txt`
3. Run it: `python3 crypto_workflow.py` (Windows: `python crypto_workflow.py`). A report appears in `reports/`.

## How it works

The workflow fetches 720 daily candles per coin and drops the last one, because it is not finished. It takes the last 30 finished days and calculates the average close, the % distance from that average, daily volatility (standard deviation of daily % returns), and maximum drawdown. Two rules turn the numbers into labels. Then it writes a Markdown report.

## Rules and thresholds

- **High volatility:** daily volatility above 3.5%. (Explain why you picked this number.)
- **Well above or below average:** more than 5% away from the 30-day average. (Explain why.)

## Hand check

(Pick one number, recalculate it in Google Sheets, and write what you found.)

## Sample output

(Paste a sample report here after you run the workflow.)

## AI analysis

(You will add this in Session 6.)
