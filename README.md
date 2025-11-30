# Meinestadt.de Property Scraper

![banner](https://i.imgur.com/BqJwrBB.png)

Welcome to the Meinestadt.de Property Scraper! This actor extracts property listings and details from Meinestadt.de, one of Germany's major portals for real estate. Get fresh postings including property titles, prices, company info, images, and comprehensive structured data such as features, certificates, and more.

<p align="center">
  <img src="https://apify-image-uploads-prod.s3.us-east-1.amazonaws.com/DevbkY3adMTBuoECt-actor-2FWKW0UporX3gSLSj-S5T7VXyXSS-DevbkY3adMTBuoECt-actor-GJmqMR1qfHesGiASa-M6tig2Zh1L-meinestadtd" alt="Meinestandt.de Immobilien Scraper" style="height: 60px; margin-right: 15px;" /><a href="https://apify.com/lexis-solutions/property-meinestandt-de-scraper" target="_blank">
    <img src="https://img.shields.io/badge/Try%20it%20on-Apify-0066FF?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDA4IiBoZWlnaHQ9IjQwOCIgdmlld0JveD0iMCAwIDQwOCA0MDgiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGNsaXAtcGF0aD0idXJsKCNjbGlwMF8zNDFfNDE1NykiPgo8cGF0aCBkPSJNMjE4LjY5NSAxMDRIMzAwLjk3QzMwMi42NDMgMTA0IDMwNCAxMDUuMzU3IDMwNCAxMDcuMDNWMjMyLjc2NkMzMDQgMjM1Ljc3OCAzMDAuMDgzIDIzNi45NDUgMjk4LjQzNCAyMzQuNDI1TDIxNi4xNTkgMTA4LjY5QzIxNC44NDEgMTA2LjY3NCAyMTYuMjg3IDEwNCAyMTguNjk1IDEwNFoiIGZpbGw9IndoaXRlIi8+CjxwYXRoIGQ9Ik0xODkuMzA1IDEwNEgxMDcuMDNDMTA1LjM1NyAxMDQgMTA0IDEwNS4zNTcgMTA0IDEwNy4wM1YyMzIuNzY2QzEwNCAyMzUuNzc4IDEwNy45MTcgMjM2Ljk0NSAxMDkuNTY2IDIzNC40MjVMMTkxLjg0IDEwOC42OUMxOTMuMTU5IDEwNi42NzQgMTkxLjcxMyAxMDQgMTg5LjMwNSAxMDRaIiBmaWxsPSJ3aGl0ZSIvPgo8cGF0aCBkPSJNMjAyLjU5MSAyMDQuNjY4TDEwOS4xMjcgMjk4LjgzNUMxMDcuMjI5IDMwMC43NDcgMTA4LjU4MyAzMDQgMTExLjI3OCAzMDRIMjk2LjhDMjk5LjQ4MyAzMDQgMzAwLjg0MiAzMDAuNzcgMjk4Ljk2NyAyOTguODUyTDIwNi45MDggMjA0LjY4NUMyMDUuNzI2IDIwMy40NzUgMjAzLjc4MiAyMDMuNDY4IDIwMi41OTEgMjA0LjY2OFoiIGZpbGw9IndoaXRlIi8+CjwvZz4KPGRlZnM+CjxjbGlwUGF0aCBpZD0iY2xpcDBfMzQxXzQxNTciPgo8cmVjdCB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgZmlsbD0id2hpdGUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEwNCAxMDQpIi8+CjwvY2xpcFBhdGg+CjwvZGVmcz4KPC9zdmc+Cg==&logoColor=white" alt="Try it on Apify" style="border-radius: 12px; height: 60px;" />
  </a>
</p>


---

## Introduction

## 📊 Actor Stats

| Stat | Value |
|------|-------|
| **Version** | `0.0.1` |
| **Last Update** | Nov 30, 2025 |

---



The Meinestadt.de Property Scraper crawls real estate listings from Germany's meinestadt.de. Use this to collect properties for sale or rent, enriched with address, floor, furnishing, company/agent, and certification details. Results are highly structured and suitable for property dashboards, data analysis, or market research.

## Use Cases

- **Property Market Research**: Analyze German property listings by region, property type, features, or company.
- **Real Estate Integrations**: Feed property data to dashboards, CRMs, or valuation tools.
- **Competitive & Trend Monitoring**: Track property releases and prices across cities & types.
- **Enrichment/Aggregation**: Combine with job or car actors for competitor intelligence platforms.

---

## Input 📥

### Notes

- You can use either **`startUrls`** (list or detail) or **`locationQuery`** for the initial entry.
- Filtering on the original website does **not** change the URL. To apply filters (price, type, features, etc.), use the corresponding **input parameters** in this actor.
- **Proxy Requirement:** Use a **German or Polish proxy** to access the data successfully.
- **Location Suggestion:** `locationQuery` will use the **first suggestion** from the website’s location dropdown, similar to the website’s behavior.
- Use **`radius`** together with **`locationQuery`** for location-based searches.
- **Supported parameters:** `propertyType`, `usageType`, `radius`, `sort`, `features`, `roomMin`, `roomMax`, `surfaceMin`, `surfaceMax`, `priceMin`, `priceMax`, `furnishingType`, `category`, and more.
- Some **property types** are only available for specific **usage types**. If an invalid combination is provided, the **default property type** for that usage will be used instead (as described in the input form).

### Input Example 1: Start URLs (list or detail)

```json
{
  "startUrls": [
    { "url": "https://www.meinestadt.de/berlin/immobilien" }, // list url
    { "url": "https://www.meinestadt.de/expose/123456789" } // detail url
  ],
  "maxItems": 20,
  "proxyConfiguration": { "useApifyProxy": true, "apifyProxyCountry": "DE" }
}
```

### Input Example 2: Location Query & Filtering

```json
{
  "locationQuery": "Hamburg",
  "propertyType": "1", // Apartment
  "usageType": "2", // Rent
  "radius": "10",
  "maxItems": 15,
  "proxyConfiguration": { "useApifyProxy": true }
}
```

---

## Output 📤

Each property data output contains fields like:

```json
{
  "title": "Zimmer in Donauwörth möbiliert nett und günstig",
  "url": "https://www.meinestadt.de/expose/29413304",
  "address": "86609 Donauwörth",
  "date": "20.10.2025",
  "companyName": "Private:r Anbieter:in",
  "contactName": "Herr Walter Tobias",
  "companyLogo": null,
  "images": [
    "https://image-resize.meinestadt.de/image-resize/v2/resize?w=400&h=400&url=https%3A%2F%2Fimage-service-upload.meinestadt.de%2Fimage-service-upload%2Fv1%2F2a4d656f6a.jpg",
    "https://image-resize.meinestadt.de/image-resize/v2/resize?w=400&h=400&url=https%3A%2F%2Fimage-service-upload.meinestadt.de%2Fimage-service-upload%2Fv1%2Fc4f57cbf8b.png"
  ],
  "baseRent": "390 €",
  "numberOfRooms": "1.0",
  "livingAreaSqm": "15 m²",
  "features": ["Einbauküche", "Gäste WC", "Bad mit Fenster"],
  "heatingIncluded": "Ja",
  "heatingCost": null,
  "serviceCharges": "120 €",
  "commissionFree": null,
  "securityDeposit": "500 €",
  "parkingCost": null,
  "usableAreaSqm": "15 m²",
  "apartmentType": "Apartment",
  "floor": "1",
  "totalFloors": null,
  "furnishing": "Vollmöbliert",
  "fitoutLevel": "Normal",
  "balconies": null,
  "terraces": null,
  "bathrooms": "1",
  "bedrooms": null,
  "petsAllowed": "Nein",
  "yearBuilt": "20092009",
  "lastRenovationYear": null,
  "condition": "Vollständig renoviert",
  "availableFrom": "sofort, nach Vereinbarung",
  "parkingType": "Außenstellplatz",
  "parkingSpaces": "1",
  "primaryEnergySource": "Pellets",
  "heatingType": "Zentralheizung",
  "energyCertificateAvailable": "Ja, liegt vor",
  "energyCertificateType": "Bedarfsausweis",
  "energyCertificateValidUntil": "2028",
  "energyConsumptionKwhPerSqmA": null,
  "energyEfficiencyClass": "A",
  "hotWaterIncludedInEnergyConsumption": "Nein",
  "energyType": null,
  "description": "Wir vermieten Zimmer möbiliert in Donauwörth nett und günstig Wenn sie auf der Suche sind, freuen wir uns auf ihre Anfrage. Bitte per Mail bei uns anfragen, da auch wir berufstätig sind . Ihre Nebenkosten kalkulieren wir gerne, wenn wir etwas mehr von ihnen wissen. mögliche Küchennutzung mögliche WLAN Nutzung mögliche Stellplatznutzung Warmmiete ab 490 Euro nötig Schöne Grüße",
  "amenities": "EinbaukücheGäste WCBad mit Fenster",
  "location": "zentral mit vielen Einkaufsmöglichkeiten",
  "misc": null,
  "floorPlan": []
}
```

---

## Why Use the Meinestadt.de Property Scraper?

- ⚡️ **Fast**: Smart crawling & pagination for fast data collection.
- 🏠 **Precise**: Filters by location, property/usage type, features, and more.
- 🤙 **Easy to use**: Start from any property list/detail or filter by parameters.
- ☑️ **Reliable**: Built with Apify Actors and Crawlee (Cheerio).
- 🇩🇪 **German-focused**: Optimized for German property market with location awareness.

---

## Related Actors

- [seloger-scraper (France)](https://apify.com/lexis-solutions/seloger-scraper): French property listings
- [immovlan (Belgium)](https://apify.com/lexis-solutions/immovlan): Belgium property portal
- [pararius (Netherlands)](https://apify.com/lexis-solutions/pararius): Dutch property listings
- [openrent-co-uk (UK)](https://apify.com/lexis-solutions/openrent-co-uk-scraper): UK rental marketplace
- [onthemarket-com (UK)](https://apify.com/lexis-solutions/onthemarket-com-scraper): Major UK property site
- [flatfox-ch (Switzerland)](https://apify.com/lexis-solutions/flatfox-ch-properties-scraper): Swiss property portal
- [boligsiden-dk (Denmark)](https://apify.com/lexis-solutions/boligsiden-dk-scraper): Denmark property search
- [hemnet-se (Sweden)](https://apify.com/lexis-solutions/hemnet-se-scraper): Sweden property search

- [jobs-meinestadt-de-scraper](https://apify.com/lexis-solutions/jobs-meinestadt-de-scraper): Scrape German jobs
- [bundesagentur-fur-arbeit-arbeitsagentur-scraper](https://apify.com/lexis-solutions/bundesagentur-fur-arbeit-arbeitsagentur-scraper): Scrape the German employment agency

---

## Need help or want a custom solution?

Lexis Solutions is a certified Apify Partner.
Contact us via [Email](mailto:scraping@lexis.solutions) or [LinkedIn](https://www.linkedin.com/company/lexis-solutions)

## Support Our Work 💝

If you like this scraper, please leave us a review at [Lexis Solutions on Apify](https://apify.com/partners/find/lexis-solutions/review). It helps us a lot!
