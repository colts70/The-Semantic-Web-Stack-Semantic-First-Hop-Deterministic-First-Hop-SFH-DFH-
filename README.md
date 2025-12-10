The Semantic Web Stack — Semantic First-Hop / Deterministic First-Hop (SFH / DFH)

A minimal semantic protocol for AI and the web — one file, five primitives, zero dependencies.
DFH/SFH provides a deterministic first-hop for meaning using JSON-LD to create a public semantic layer that AIs and search engines resolve before content.

This is the smallest possible solution to one of the hardest problems in AI:
semantic grounding.

This project is not affiliated with Google, Amazon, OpenAI, DeepMind, Microsoft, or any third-party organization.
This is a modern implementation of Tim Berners-Lee’s Semantic Web map — rebuilt for AI.

🌐 What is DFH / SFH?
DFH — Deterministic First-Hop
SFH — Semantic First-Hop

Together, they define a deterministic, machine-perfect public semantic layer that sits between DNS/HTTP and content:

Transport Layer → DNS, TCP/IP  
Hyperlink Layer → HTTP, URL  
Semantic Layer → DFH / SFH  
Content Layer  → Web pages, APIs, datasets  
Model Layer    → AI systems, KG pipelines


Instead of guessing what a domain “means,” AI resolves one file:

https://yourdomain.com/.well-known/stack


or

https://yourdomain.com/.sfh.json


That single declaration exposes five canonical primitives.

🧱 The Five Canonical Primitives
Primitive	Description
type	What kind of thing the domain represents (Organization, Person, Product, System…)
entity	The canonical identity / name of the domain
url	The primary canonical URL
sitemap	One or more sitemaps or semantic maps
canonical	The single authoritative semantic identity of the declaration
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

DFH/SFH gives AI systems:

Deterministic grounding — one authoritative place to resolve meaning

Canonical identity — removes ambiguity and hallucination paths

Semantic routing — directs models and KGs where structured data lives

Stability — static, cacheable, versionable

JSON-LD compatibility — integrates directly into KG workflows

Resolution becomes:

DNS → HTTP → DFH/SFH → KG → Model Reasoning


instead of:

DNS → HTTP → Crawl everything → Infer → Hallucinate semantics


This flips the entire industry from semantic guesswork to semantic determinism.

✅ DFH/SFH Compliance (42/42)

A domain is considered fully compliant if:

A file exists at /.well-known/stack or /.sfh.json

JSON is valid and well-formed

JSON-LD is valid (recommended)

All five primitives are present

canonical resolves to itself

type, entity, and url are consistent

No conflict with legal or verified KG identity

Declarations are deterministic and unambiguous

Perfect compliance score: 42 / 42

A CLI harness computes this automatically (see SPEC.md).

🛡️ Safety & Governance

All DFH/SFH declarations operate under:

Verified legal identity

Trademark ownership

Knowledge graph consistency

Regulatory constraints

Publicly verifiable facts

If a DFH/SFH file contradicts real-world verified identity, systems MUST:

Prefer the verified source

Treat DFH/SFH as untrusted for that domain

This prevents:

Fraud

Impersonation

Disinformation

Semantic hijacking

DFH/SFH is a public semantic hint, not a legal override.

📄 Specification

See SPEC.md — DFH/SFH Protocol Specification v1.1
Public Semantic Layer (PSL) — Draft Standard

Includes:

Formal definitions

Deterministic resolution rules

Safety override semantics

Optional extensions (aliases, mirrors, semantic routes)

Full 42-point compliance checklist

Reference implementation guidelines

🔧 Roadmap

Planned:

Node.js compliance harness (dfh-compliance)

Example DFH/SFH files for:

Major banks

Fortune 500

Open-source projects

Creators & personal domains

Integration guides for:

SEO

AI agents

Knowledge graphs

Search engines

📜 License

MIT License.
Free to use, fork, modify, and embed in any system.

🙏 Attribution

DFH/SFH is independent, experimental research into:

A deterministic semantic layer for the public internet

A minimal upgrade to the Semantic Web

A public grounding map for AI systems

Not affiliated with any organization.

Correct SPEC Header (paste into SPEC.md)
# DFH / SFH PROTOCOL — SPEC v1.1
_Public Semantic Layer (PSL) — Draft Standard_

> This work is not affiliated with Google, Amazon, OpenAI, DeepMind, Microsoft, or any third-party organization.
> DFH/SFH is an independent, decentralized semantic protocol.
> Safety and systemic coherence always override deterministic claims.
