# Copilot Studio : Entities

## Purpose

```text
Entities identify and normalize meaningful information in a user's utterance,
such as dates, numbers, locations, categories or domain-specific values.
```

## Design

```text
Built-in entity where suitable
Closed list for controlled vocabulary
Synonyms for recognized variations
Validation for ambiguity
Fallback when no reliable value is found
```

Do not assume entity recognition is authorization or business validation. Confirm high-impact values, preserve the original user input where needed, and test spelling, abbreviations, multilingual input and ambiguous phrases.
