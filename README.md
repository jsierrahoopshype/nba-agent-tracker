# NBA Agent Tracker

Interactive dashboard for tracking NBA player-agent relationships and career earnings since 1990.

## Files

- `index.html` - Main application (React loaded via CDN)
- `data.json` - Agent relationships and salary data

## Deploy to GitHub Pages

### Option A: Using GitHub Web Interface

1. Create a new repository on GitHub (e.g., `nba-agent-tracker`)
2. Upload both `index.html` and `data.json` to the repository
3. Go to **Settings** → **Pages**
4. Under "Source", select **Deploy from a branch**
5. Choose **main** branch and **/ (root)** folder
6. Click **Save**
7. Your site will be live at: `https://[username].github.io/nba-agent-tracker/`

### Option B: Using Git Command Line

```bash
# Initialize and push
cd agent-tracker-gh-pages
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/[username]/nba-agent-tracker.git
git push -u origin main

# Then enable Pages in repository Settings
```

## Embed in HoopsHype (Presto)

Once deployed, embed with iframe:

```html
<iframe 
  src="https://[username].github.io/nba-agent-tracker/" 
  width="100%" 
  height="800" 
  frameborder="0"
  style="border: none; max-width: 1200px;"
></iframe>
```

### Responsive Embed

For responsive height, add this script after the iframe:

```html
<script>
  window.addEventListener('message', function(e) {
    if (e.data.type === 'resize') {
      document.querySelector('iframe').style.height = e.data.height + 'px';
    }
  });
</script>
```

## Updating Data

To update the agent/salary data:

1. Replace `data.json` with new data
2. Commit and push to GitHub
3. Changes go live automatically (may take 1-2 minutes)

## Data Structure

`data.json` contains:

```json
{
  "playerSalaries": {
    "Player Name": {
      "2024-25": 35000000,
      "2023-24": 32000000
    }
  },
  "agentData": [
    {
      "agent": "Agent Name",
      "player": "Player Name",
      "team": "Team Name",
      "start": "2020-07-01",
      "end": null,
      "current": "Yes"
    }
  ]
}
```

## Features

- Search agents or players
- Agent leaderboard by total client earnings
- Player leaderboard by career earnings
- Season-by-season earnings breakdown
- Click any season to see that year's top earners
- Related suggestions (shared clients, similar rankings)
- Mobile responsive

## Credits

Data compiled by HoopsHype
