# Weather Update Publisher

A simple tool for publishing time-limited weather alerts to your website.

## Features

- Set weather alerts with automatic expiration
- Select which campuses are affected
- Secure GitHub Actions workflow (no repo token in browser)
- Auto-clearing alerts after duration expires
- Easy Squarespace embed code

## Setup Instructions

### 1. Create GitHub Token

1. Go to [GitHub Settings > Tokens](https://github.com/settings/tokens/new?scopes=actions:write&description=Weather%20Update%20Publisher)
2. Select scope: **`actions:write`** (NOT `repo` - more secure!)
3. Click "Generate token"
4. Copy the token (starts with `ghp_`)

### 2. Enter Token in Webpage

1. Visit your published site: https://yacnetadmin.github.io/yafoc-websiteweatherupdates/
2. Paste the token in the "GitHub Token" field
3. It will be saved in your browser's localStorage

### 3. Publish Weather Alerts

1. Enter your alert message
2. Select affected campuses
3. Choose duration (1-36 hours)
4. Click "Generate Update"
5. Alert publishes in 10-20 seconds via GitHub Actions

### 4. Add to Squarespace

Copy the embed code from the webpage and paste it into a Squarespace Code Block where you want the alert to appear.

## How It Works

- **Security**: Token only has `actions:write` permission (can't read/modify code)
- **Workflow**: Webpage triggers GitHub Actions workflow
- **Automation**: GitHub Actions updates the JSON file
- **Display**: Embed code fetches JSON and shows/hides based on expiration

## Files

- `index.html` - Main application interface
- `weather-update.json` - Current alert data (updated by workflow)
- `.github/workflows/update-weather.yml` - GitHub Actions workflow

## Clear an Alert

Click the "Clear Alert" button to remove the alert before it expires naturally.

