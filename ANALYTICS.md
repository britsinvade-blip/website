# Google Analytics Tracking Documentation

## App Store Button Tracking

All "Download on the App Store" buttons across the website now fire Google Analytics events when clicked.

### Event Details

**Event Name:** `app_store_click`

**Event Parameters:**
- `app_name`: The name of the app (e.g., "Gelato Wizard", "Fastest Train")
- `location`: Where the button was clicked (`hero_button` or `footer_button`)

### Tracked Buttons

Each app page has 2 tracked buttons:
- ✅ **Fastest Train** (2 buttons)
- ✅ **Cholesterol Heart Tracker** (2 buttons)
- ✅ **Gelato Wizard** (2 buttons)
- ✅ **Spettle** (2 buttons)
- ✅ **Tic Tac More** (2 buttons)
- ✅ **Fires & Ladders** (2 buttons)

**Total:** 12 tracked App Store buttons

## Viewing Data in Google Analytics

### 1. Real-Time Events
1. Go to Google Analytics (GA4)
2. Navigate to: **Reports** → **Realtime**
3. Scroll to "Event count by Event name"
4. Look for `app_store_click` events

### 2. Event Reports
1. Go to: **Reports** → **Engagement** → **Events**
2. Find `app_store_click` in the events list
3. Click on it to see detailed breakdown

### 3. Custom Report by App
1. Go to: **Explore** → **Create new exploration**
2. Add dimensions: `Event name`, `app_name`, `location`
3. Add metrics: `Event count`
4. Filter: Event name = `app_store_click`

### 4. Useful Queries

**Which app gets the most clicks?**
- Dimension: `app_name`
- Metric: `Event count`

**Hero vs Footer button performance?**
- Dimension: `location`
- Metric: `Event count`

**App-specific funnel:**
- Filter by `app_name` = "Gelato Wizard"
- See clicks by location

## Example Data Structure

```json
{
  "event": "app_store_click",
  "app_name": "Gelato Wizard",
  "location": "hero_button"
}
```

## Conversion Tracking

To track actual App Store visits (not just clicks):
1. Set up **Google Analytics 4 Outbound Link tracking** (already enabled by default)
2. Look for `click` events with `link_url` containing "apps.apple.com"

## Tips

- Events may take 24-48 hours to appear in standard reports
- Use **Real-time** view for immediate verification
- Compare click-through rates: `app_store_clicks / page_views`
- A/B test button placement using `location` parameter

## Event Testing

To test if tracking works:
1. Open website in browser
2. Open browser DevTools Console
3. Click an App Store button
4. Check for network request to Google Analytics
5. Verify in Real-time reports (appears within seconds)
