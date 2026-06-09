[Chicago Food Inspections](https://apify.com/fortuitous_pirate/chicago-food-inspections?fpr=data)

# Chicago Food Inspections

## Overview

Fetch food inspection data from Chicago's Socrata Open Data API. Supports filters (Facility Type, Start Date, End Date).

## Features

- Search by keywords to find specific results
- Filter results by category or type
- Export data in JSON, CSV, or Excel formats
- Control output volume with configurable result limits

## Use Cases

- **Track** - Track state and local government data and permits
- **Monitor** - Monitor regulatory filings and public records
- **Build** - Build databases for civic tech and transparency projects
- **Aggregate** - Aggregate local government data for community research

## Input Parameters

| Parameter | Type | Description | Default |
| --- | --- | --- | --- |
| `facilityType` | string | Filter by facility type (e.g., 'Restaurant', 'Grocery Store', 'Bakery') |  |
| `riskLevel` | string | Filter by risk level | `` |
| `results` | string | Filter by inspection result | `` |
| `startDate` | string | Filter inspections on or after this date (YYYY-MM-DD format) |  |
| `endDate` | string | Filter inspections on or before this date (YYYY-MM-DD format) |  |
| `maxItems` | integer | Maximum number of inspection records to fetch | `1000` |

## Output Example

Each result contains structured data like this:

```
{
  "inspection_id": "ABC-12345",
  "dba_name": "Chicago Food Inspections Sample Item",
  "aka_name": "Chicago Food Inspections Sample Item",
  "license_": "Sample license_",
  "facility_type": "Sample facility_type",
  "risk": "Sample risk",
  "address": "123 Main St",
  "city": "San Francisco",
  "state": "CA",
  "zip": "94105",
  "inspection_date": "2025-01-15",
  "inspection_type": "Sample inspection_type"
}
```

## Pricing

This actor uses pay-per-result pricing:

- **$0.001** per result
- **$1.00** per 1,000 results

No monthly fees. You only pay for what you scrape. [Apify Free plan](https://apify.com/pricing) includes $5/month in platform credits.

## How to Run

### Apify Console

1. Go to the [Chicago Food Inspections](https://apify.com/fortuitous_pirate/chicago-food-inspections) actor page
2. Configure your input parameters
3. Click **Start** and wait for the results
4. Download data in JSON, CSV, or Excel format

### API

```
curl -X POST "https://api.apify.com/v2/acts/fortuitous_pirate~chicago-food-inspections/runs?token=YOUR_API_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"maxItems": 10}'
```

### Python SDK

```
from apify_client import ApifyClient

client = ApifyClient("YOUR_API_TOKEN")
run = client.actor("fortuitous_pirate/chicago-food-inspections").call(
    run_input={"maxItems": 10}
)

for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

## Integration

Connect Chicago Food Inspections with your existing tools and workflows:

- **API access** - Programmatic access via [Apify API](https://docs.apify.com/api/v2)
- **Webhooks** - Get notified when scraping completes
- **Scheduling** - Set up recurring runs on any schedule
- **Zapier / Make** - Connect with 5,000+ apps via [Apify integrations](https://apify.com/integrations)
- **Python / Node.js SDKs** - Native client libraries for easy integration