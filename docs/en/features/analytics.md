---
title: Analytics
description: Track and analyze your email campaign performance with LiteStartup's analytics dashboard.
---

# Analytics

> Track and analyze your email campaign performance.

Analytics provides insights into your email performance, helping you understand what works and optimize your campaigns for better results.

## Getting Started

1. Go to **Emails > Analytics** from the sidebar
2. View your email performance metrics
3. Analyze trends over time
4. Export reports as needed

## Dashboard Overview

The Analytics dashboard shows key metrics at a glance:

- **Emails Sent** - Total emails sent in the period
- **Delivery Rate** - Percentage successfully delivered
- **Open Rate** - Percentage of emails opened
- **Click Rate** - Percentage of emails with link clicks
- **Unsubscribe Rate** - Percentage of unsubscribes

## Key Metrics

### Email Metrics

| Metric | Description |
|--------|-------------|
| Sent | Total emails sent |
| Delivered | Successfully delivered to inbox |
| Bounced | Failed to deliver (hard/soft bounce) |
| Opened | Unique email opens |
| Clicked | Unique link clicks |
| Unsubscribed | Unsubscribe requests |

### Engagement Rates

| Rate | Formula | Good Benchmark |
|------|---------|----------------|
| Delivery Rate | Delivered / Sent | > 95% |
| Open Rate | Opens / Delivered | > 20% |
| Click Rate | Clicks / Delivered | > 2% |
| Unsubscribe Rate | Unsubscribes / Delivered | < 0.5% |

## Time Range

View analytics for different periods:

- **Last 7 days**
- **Last 30 days**
- **Last 90 days**
- **Custom range**

## Campaign Analytics

View performance for individual campaigns:

1. Go to **Emails > Campaigns** → Select a campaign
2. Click **View Report**
3. See detailed metrics for that campaign

### Campaign Report Includes

- Total recipients
- Delivery status breakdown
- Open and click tracking
- Top clicked links
- Geographic distribution
- Device breakdown

## Engagement Trends

Track how engagement changes over time:

- **Daily trends** - See patterns by day of week
- **Hourly trends** - Find the best time to send
- **Monthly trends** - Track long-term performance

## Contact Engagement

View engagement at the contact level:

- **Most engaged** - Contacts who open and click frequently
- **Inactive** - Contacts who haven't engaged recently
- **At risk** - Contacts showing declining engagement

## API Access

Access analytics data programmatically via the [Analytics API](api/analytics-get.md):

```bash
curl -X GET "https://api.litestartup.com/client/v2/analytics?days=30" \
     -H 'Authorization: Bearer YOUR_API_KEY'
```

## Best Practices

- **Monitor regularly** - Check analytics weekly at minimum
- **A/B test** - Compare different subject lines and content
- **Segment by engagement** - Target active vs inactive contacts differently
- **Clean your list** - Remove consistently inactive contacts
- **Optimize send times** - Use data to find the best times to send