# jim_N8N_8134_base_v1

A lightweight n8n workflow template for collecting RSS / API-style feed data, cleaning fields, removing duplicates, and writing structured records into Google Sheets.

## 1. What This Workflow Does

This workflow provides a simple data pipeline:

```text
Schedule Trigger
→ RSS Read
→ Merge
→ Set / Field Mapping
→ Filter
→ Deduplicate by Title
→ Google Sheets Append or Update
```

It is designed as a reusable base template for small business automation, lead monitoring, content aggregation, market tracking, and lightweight data collection workflows.

---

## 2. Core Use Case

This template is suitable for:

- RSS feed monitoring
- Public API data collection
- News or content aggregation
- Lightweight lead/source tracking
- Writing cleaned records into Google Sheets
- Preventing duplicate entries across repeated runs

---

## 3. Output Fields

The workflow writes the following standardized fields into Google Sheets:

```text
url
title
summary
published_at
source
first_seen_at
status
```

Google Sheets header row:

```text
url	title	summary	published_at	source	first_seen_at	status
```

---

## 4. Deduplication Logic

This version deduplicates records by:

```text
title
```

Reason:

Some RSS sources, especially Google News RSS, may generate different redirect URLs for the same underlying article. URL-based deduplication is therefore unreliable for this base version.

---

## 5. Google News URL Limitation

When using Google News RSS, the `url` field may contain a Google News redirect URL instead of the original canonical publisher URL.

This is an accepted limitation of the base version.

If canonical publisher URLs are required, that should be handled as a paid upgrade or custom enhancement.

---

## 6. Included Deliverables

```text
1. n8n workflow JSON
2. Google Sheets field template
3. README documentation
4. Workflow screenshot
```

Recommended file names:

```text
jim_N8N_8134_base_v1.json
jim_N8N_8134_base_v1_sheet_template
README.md
workflow_screenshot.png
```

---

## 7. Recommended Use

This workflow is intended as a base automation template.

It can be customized for:

- Different RSS sources
- API inputs
- Extra filters
- Additional fields
- Telegram / Email alerts
- Error handling workflow
- Canonical URL extraction
- AI summarization or classification

---

## 8. Maintenance Boundary

The base version intentionally avoids complex logic.

It does not include:

- Canonical URL extraction
- AI processing
- Multi-user configuration
- Advanced error workflow
- High-frequency database-grade deduplication
- Direct scraping of restricted websites

---

## 9. Commercial Positioning

This is a base workflow template for small automation projects.

Typical customization directions:

```text
RSS/API → Clean Data → Deduplicate → Google Sheets
RSS/API → Filter → Alert
API → Normalize → Excel/Sheets
Broken n8n workflow → Fix and stabilize
```

---

## 10. Version

```text
jim_N8N_8134_base_v1
```

Status:

```text
Base version completed.
Ready for demonstration, reuse, and client-specific customization.
```
