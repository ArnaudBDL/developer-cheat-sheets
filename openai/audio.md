# OpenAI : Audio

## Audio Tasks

```text
Speech to text
Text to speech
Speech to speech
Speech translation
Realtime transcription and voice interaction
```

## Architecture Choice

```text
Request-based API
  Bounded file or text input, simpler processing.

Realtime session
  Live audio with low-latency partial events and session state.
```

## Rules

- Select a model and endpoint supporting the required audio modality.
- Validate media type, duration, size and sample format.
- Stream partial results only when the application can handle revisions.
- Obtain required consent for recording and synthetic speech.
- Protect voice recordings and transcripts as sensitive data.
- Define interruption, timeout and reconnect behavior for realtime sessions.
- Clearly disclose AI-generated voices where required.
