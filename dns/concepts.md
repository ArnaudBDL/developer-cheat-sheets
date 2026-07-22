# DNS : Concepts

## Purpose

DNS is a distributed, hierarchical query-response system that maps domain names to data such as IP addresses, mail servers and service metadata.

## Core Components

```text
Stub resolver          Client-side resolver used by applications
Recursive resolver     Resolves queries on behalf of clients
Root name server       Refers resolvers to top-level-domain servers
TLD name server        Refers resolvers to authoritative servers
Authoritative server   Serves data for a DNS zone
Zone                   Administrative portion of the DNS namespace
Resource record        Typed DNS data associated with a name
```

## Hierarchy

```text
.                       Root
└── com.                 Top-level domain
    └── example.com.     Registered domain
        ├── www          Host or service label
        └── api          Host or service label
```

## Query Flow

```text
Application
    ↓
Stub resolver
    ↓
Recursive resolver
    ↓
Root → TLD → Authoritative server
    ↓
Cached answer returned to the application
```

## Transport

```text
UDP port 53   Common DNS queries and responses
TCP port 53   Large responses, fallback and zone transfers
DoT port 853  DNS over TLS
DoH           DNS over HTTPS
DoQ           DNS over QUIC
```

## Basic Query

```bash
dig example.com A
dig example.com AAAA
dig example.com MX
```
