# Copilot : Connectors

## Purpose

Copilot connectors can make approved external organizational content available to Microsoft 365 Copilot and Microsoft 365 search experiences while respecting underlying access controls.

## Source Examples

```text
Knowledge bases
Ticketing systems
Wikis
File stores
CRM systems
Business applications
```

## Implementation Checklist

- Confirm ownership and approval for the source.
- Map source permissions accurately.
- Define indexed fields and searchable content.
- Exclude secrets and unnecessary sensitive data.
- Establish sync, deletion and failure behavior.
- Test citations and source links.
- Monitor indexing health and access changes.

## Prompt Pattern

```text
From the approved ticketing connector, summarize open incidents for Project Atlas from this week.
Include citations and do not use other sources.
```
