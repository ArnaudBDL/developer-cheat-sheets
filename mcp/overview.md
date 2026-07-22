# Model Context Protocol : Overview

## Purpose

```text
Model Context Protocol (MCP) standardizes how AI applications connect to external context and capabilities.
```

## Core Participants

```text
Host    AI application coordinating one or more MCP clients
Client  Connector maintaining a dedicated connection to one MCP server
Server  Program exposing context and capabilities to MCP clients
```

## Server Features

```text
Resources  Context and data exposed for reading
Prompts    Reusable message and workflow templates
Tools      Functions exposed for model-controlled invocation
```

## Client Feature

```text
Sampling  A server requests model generation through the connected client
```

MCP defines context exchange and capability invocation. It does not prescribe how a host manages its language model or uses returned context.
