# agentic_workflow
Agents to assist with workflow

## Facebook Marketplace Screenshot Tool

Automatically captures daily screenshots of Facebook Marketplace listings in Arlington, MA.

### Setup

```bash
cd marketplace_screenshots
pip install -r requirements.txt
playwright install chromium
```

### Usage

**Take screenshots now (one-time run):**
```bash
python marketplace_screenshots/screenshot_marketplace.py
```

**Force a re-run (even if already ran today):**
```bash
python marketplace_screenshots/screenshot_marketplace.py --force
```

**Run on a daily schedule (keeps running in background):**
```bash
python marketplace_screenshots/screenshot_marketplace.py --schedule
```

**Specify a custom time (24-hour format):**
```bash
python marketplace_screenshots/screenshot_marketplace.py --schedule --time 08:30
```

**Custom output directory:**
```bash
python marketplace_screenshots/screenshot_marketplace.py --output-dir /path/to/folder
```

### Alternative: Use cron (Linux/macOS)

Add to your crontab (`crontab -e`) for a daily run at 9 AM:
```
0 9 * * * cd /path/to/agentic_workflow && python marketplace_screenshots/screenshot_marketplace.py
```

### Output

Screenshots are saved to `marketplace_screenshots/screenshots/` by default, with filenames like:
```
marketplace_arlington_ma_2024-01-15_09-00-00_page1.png
marketplace_arlington_ma_2024-01-15_09-00-00_page2.png
marketplace_arlington_ma_2024-01-15_09-00-00_full.png
```

### Notes

- The script runs only once per day by default (tracks last run date in `.last_run` file)
- Uses headless Chromium browser via Playwright
- Facebook may require login for some content — the script captures whatever is publicly visible
- Screenshots include multiple scroll positions plus a full-page capture
