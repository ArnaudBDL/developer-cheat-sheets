# OpenAI : Images

## Image Workflow

```text
Choose an image-capable endpoint and model
Describe subject, composition, style and constraints
Request generation or editing
Validate the returned asset
Store the asset and provenance metadata
```

## Prompt Pattern

```text
Create [subject] in [visual style].
Composition: [camera, framing and layout].
Lighting and palette: [details].
Constraints: [aspect ratio, background and exclusions].
```

## Rules

- Use the image API or a supported multimodal workflow documented for the selected model.
- Verify accepted input types, output formats and size options.
- Treat uploaded images as untrusted files.
- Review generated images before publication.
- Preserve rights, consent and organizational branding requirements.
- Record prompt, model and asset lineage when reproducibility matters.
