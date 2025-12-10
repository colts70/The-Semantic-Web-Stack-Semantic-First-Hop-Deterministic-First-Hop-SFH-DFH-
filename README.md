The-Semantic-Web-Stack — Semantic First-Hop / Deterministic First-Hop (SFH / DFH)
A minimal semantic protocol for AI and the web — one file, five primitives, zero dependencies.

DFH/SFH provides a deterministic first-hop for meaning using JSON-LD to create a public semantic layer that AIs and search engines resolve before content.

🌐 The Semantic Web Stack (SFH / DFH)
Core Principles

One file

Five primitives

Zero dependencies

Pure JSON-LD

Deterministic meaning

This is the smallest possible solution to one of the hardest problems in AI:

semantic grounding.

This project is not affiliated with Google, Amazon, OpenAI, DeepMind, Microsoft, or any third-party organization.
It is a modern, minimal implementation of Tim Berners-Lee’s Semantic Web vision — rebuilt for AI systems.

🧠 What is DFH / SFH?
DFH — Deterministic First-Hop
SFH — Semantic First-Hop

Together, they define a public semantic layer that sits between DNS/HTTP and web content, giving every domain a deterministic meaning root.

Transport Layer   → DNS, TCP/IP  
Hyperlink Layer   → HTTP, URL  
Semantic Layer    → DFH/SFH  
Content Layer     → Web pages, APIs, datasets  
Model Layer       → AI systems, KG pipelines  


Instead of guessing what a domain “means,” AIs resolve one file:

https://yourdomain.com/.well-known/stack


or the alternative:

https://yourdomain.com/.sfh.json


That single file exposes five canonical primitives.

🧱 The Five Canonical Primitives
Primitive	Description
type	What kind of thing the domain represents (Organization, Person, Product…)
entity	The canonical identity/name of the domain
url	The primary canonical URL
sitemap	One or more sitemaps or semantic maps
canonical	The authoritative semantic identity (usually the DFH/SFH file itself)
Minimal Example
{
  "@context": "https://schema.org",
  "type": "Organization",
  "entity": "Example Corp",
  "url": "https://example.com",
  "sitemap": [
    "https://example.com/sitemap.xml"
  ],
  "canonical": "https://example.com/.well-known/stack"
}

🚦 Why This Matters for AI

DFH/SFH provides:

Deterministic grounding — one place to resolve meaning

Canonical identity — eliminates semantic guessing

Semantic routing — where to look for structured content

Stability — static, cacheable, versionable

JSON-LD compatibility — maps into knowledge graphs with zero friction

The new AI resolution pipeline becomes:

DNS → HTTP → DFH/SFH → KG → Model Reasoning


Instead of:

DNS → HTTP → Crawl everything → Hallucinate semantics


This is why your protocol hits so hard — it solves the first-hop problem every model struggles with.

✅ Compliance (42/42)

A domain is DFH/SFH compliant if:

File exists at /.well-known/stack or /.sfh.json

JSON is valid

JSON-LD is valid (recommended)

All five primitives are present

canonical resolves to itself

type, entity, url are consistent

No conflict with legal or verified identity

Meaning is deterministic and unambiguous

Perfect score: 42/42

A CLI harness can compute this (see SPEC.md).

🛡️ Safety & Governance

All DFH/SFH declarations are bound by:

Legal identity

Trademark ownership

Verified knowledge graphs

Regulatory constraints

Publicly verified facts

If a DFH/SFH file contradicts these, consumers must:

Prefer the verified source

Treat the DFH/SFH file as untrusted

This prevents:

Fraud

Impersonation

Disinformation

DFH/SFH is a public semantic hint, not an override of legal reality.

📄 Spec

Full protocol defined in:

SPEC.md — DFH/SFH Protocol Specification v1.1

Public Semantic Layer (PSL) — Draft Standard

Contains:

Formal definitions

Deterministic resolution rules

Safety override semantics

Extension fields (mirrors, aliases, routes)

42-point compliance checklist

Suggested reference implementation

🔧 Roadmap
Planned:

Node.js compliance harness (dfh-compliance)

Example DFH/SFH files for:

Major banks

Fortune 500

Open-source projects

Creators / personal sites

Integration guides for:

SEO

AI agents

Knowledge graphs

Search engines

📜 License

MIT License — free to use, fork, modify, embed.

🙏 Attribution

DFH/SFH is independent, experimental research into:

A deterministic semantic layer for the public internet

A minimal upgrade to the Semantic Web

A public grounding map for AI systems

Not affiliated with any company or institution.

✅ SPEC.md Header (Copy/Paste)
# DFH / SFH PROTOCOL — SPEC v1.1
_Public Semantic Layer (PSL) — Draft Standard_

> **This work is not affiliated with Google, Amazon, OpenAI, DeepMind, Microsoft, or any third-party organization.**
> **DFH/SFH is an independent, decentralized semantic protocol.**
> **Safety and systemic coherence always override deterministic claims.**
