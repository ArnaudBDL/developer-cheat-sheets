# OpenAI : Files

## Upload

```python
with open("document.pdf", "rb") as file_handle:
    uploaded = client.files.create(
        file=file_handle,
        purpose="YOUR_SUPPORTED_PURPOSE",
    )

print(uploaded.id)
```

## Lifecycle

```text
Validate local file
Upload for a documented purpose
Store returned file identifier
Reference it only from compatible APIs
Monitor processing state when applicable
Delete it when no longer required
```

- Check supported formats, purposes and size limits in current documentation.
- Do not upload secrets or unnecessary personal data.
- Apply file-level authorization in the application.
- Treat filenames and file contents as untrusted input.
- Track retention, ownership and deletion.
- Do not expose file identifiers as proof of authorization.
