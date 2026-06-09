[Chicago Food Inspections](https://apify.com/clawdeus/chicago-food-inspections?fpr=data)

# Chicago Food Inspections Scraper

Get comprehensive Chicago restaurant inspection data including violations, ratings, and business details. Perfect for compliance monitoring, market research, and consumer protection. Updated daily from the official Chicago Open Data Portal.

## Features

- Extracts data from Chicago's official Socrata API (data.cityofchicago.org)
- Supports flexible filtering by date range, facility type, business name, risk level, and inspection results
- Includes detailed violation information and geolocation data
- Returns structured data with cleaned violation text and parsed coordinates
- Rate-limited to be respectful to the city's API

## Data Extracted

Each inspection record includes:

- **Business Information**: Name, alternative name, license number, facility type
- **Location Data**: Full address, city, state, zip code, latitude/longitude
- **Inspection Details**: Date, type, result, risk level
- **Violations**: Both raw text and parsed violation array
- **Metadata**: Unique inspection ID and scrape timestamp

## Input Parameters

- **Start Date**: Filter inspections from this date (YYYY-MM-DD)
- **End Date**: Filter inspections until this date (YYYY-MM-DD)
- **Facility Type**: Filter by business type (e.g., "Restaurant", "Grocery Store")
- **Business Name**: Search for specific business names (partial matching)
- **Risk Level**: Filter by risk category (High, Medium, Low)
- **Inspection Result**: Filter by outcome (Pass, Fail, Pass w/ Conditions, etc.)
- **Max Items**: Limit the number of records returned (default: 1000, max: 50000)

## Use Cases

- **Compliance Monitoring**: Track inspection history for specific businesses
- **Market Research**: Analyze food safety trends across different facility types
- **Consumer Protection**: Identify businesses with recent violations
- **Data Analytics**: Perform statistical analysis of food safety patterns
- **Due Diligence**: Research potential business partners or acquisitions

## Data Source

This actor uses Chicago's official Open Data API:

- **Source**: City of Chicago Data Portal
- **Dataset**: Food Inspections (ID: 4ijn-s7e5)
- **Update Frequency**: Daily
- **API**: Socrata SODA API

## Rate Limits

The actor includes built-in rate limiting (100ms between requests) to ensure respectful API usage.

## Output Format

Data is returned in JSON format with the following structure:

```
{
  "inspectionId": "123456",
  "businessName": "EXAMPLE RESTAURANT",
  "alternativeName": "Example Rest",
  "licenseNumber": "987654",
  "facilityType": "Restaurant",
  "riskLevel": "Risk 1 (High)",
  "address": "123 Main St",
  "city": "CHICAGO",
  "state": "IL",
  "zipCode": "60601",
  "inspectionDate": "2024-01-15T00:00:00.000",
  "inspectionType": "Canvass",
  "inspectionResult": "Pass",
  "violations": ["Temperature violation", "Hand washing violation"],
  "violationText": "Temperature violation | Hand washing violation",
  "latitude": 41.8781,
  "longitude": -87.6298,
  "scrapedAt": "2024-01-16T10:30:45.123Z"
}
```

## Legal and Ethical Use

This data is publicly available through Chicago's Open Data Portal. Users should:

- Verify data accuracy before making business decisions
- Respect the original data licensing terms
- Use responsibly and ethically
- Not overload the city's servers

## Support

For issues or questions about this actor, please contact the developer or check the Apify marketplace for updates.