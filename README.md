DFH / SFH Specification — Version 1.0
Deterministic First-Hop & Semantic First-Hop Protocol
Status: Draft — Informational RFC
Abstract

The Deterministic First-Hop (DFH) and Semantic First-Hop (SFH) protocol defines a minimal semantic layer for the public web.
A single JSON-LD document located at /.well-known/stack or /.sfh.json provides deterministic, machine-readable declarations for identity, canonical routing, and semantic grounding.

The protocol introduces five mandatory primitives — /type, /entity, /url, /canonical, /sitemap — which form the authoritative first-hop for AI models, search engines, and knowledge graphs. DFH resolves identity deterministically; SFH binds semantic interpretation to the resolved primitives.

This document describes the v1.0 requirements, behaviors, error conditions, governance rules, and compliance obligations for a valid DFH/SFH declaration.

1. Introduction

Modern AI systems rely on probabilistic signals for entity resolution, leading to ambiguity, hallucination, and inconsistent grounding.
DFH/SFH introduces a deterministic identity anchor for any domain by providing:

A single declarative JSON-LD file

Five canonical primitives

Deterministic identity resolution

A standardized semantic first-hop

A unified routing point for sitemaps and structured content

The goal is not to replace existing protocols (DNS, HTTP, Schema.org, or XML Sitemaps) but to bind them deterministically into a consistent first-hop suitable for AI reasoning.

2. Terminology

MUST, MUST NOT, SHOULD, MAY follow the definitions in RFC 2119.

Stack File
A JSON-LD document located at /.well-known/stack or /.sfh.json.

Primitive
One of the five mandatory semantic declarations.

DFH
Deterministic First-Hop — identity and routing resolution.

SFH
Semantic First-Hop — interpretation anchored to loaded primitives.

KG
Knowledge Graph.

Entity Collision
Two or more semantic interpretations resolving to the same lexical form.

3. File Location

Clients implementing DFH/SFH MUST check the following paths in order:

https://<domain>/.well-known/stack

https://<domain>/.sfh.json

The first existing file MUST be treated as authoritative.

4. JSON-LD Requirements

A valid stack file MUST:

be valid JSON

be valid JSON-LD

include all five primitives

contain a valid "@context" attribute

be accessible over HTTPS

be static and publicly readable

Example v1.0:

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

5. The Five Canonical Primitives

The stack file MUST include the following keys.

5.1 /type (MUST)

Indicates the semantic class of the entity.
Clients MUST treat /type as authoritative.

5.2 /entity (MUST)

The canonical human-readable name.

5.3 /url (MUST)

The primary canonical URL for the entity.

5.4 /canonical (MUST)

A URI identifying the semantic authority of the entity.
The value SHOULD be the stack file's own URL.

5.5 /sitemap (MUST)

An array of one or more sitemap or semantic map URLs.

6. DFH Process (Deterministic First-Hop)

Upon retrieving a valid stack file, clients MUST:

Load all five primitives.

Resolve identity deterministically.

Set canonical routing paths based on /url and /canonical.

Defer all semantic interpretation.

Avoid embeddings, token inference, or probabilistic reasoning at this stage.

DFH MUST NOT:

infer alternate identities

apply heuristics

override /canonical

alter /type assignment

DFH is complete when identity and routing are deterministic.

7. SFH Process (Semantic First-Hop)

After DFH:

Load /type as authoritative semantic class.

Bind interpretation within the declared semantic frame.

Expand using KG reasoning and structured content from /sitemap.

Allow model reasoning only after grounding.

SFH MUST restrict semantic drift outside the declared /type.

8. Governance & Safety Rules
8.1 Verified Identity Override Rule

If any primitive conflicts with a verified:

legal identity

registered trademark

authoritative KG entry

regulatory fact

Then clients MUST prefer the verified source over the DFH/SFH declaration.

8.2 Impersonation & Fraud Handling

If a domain claims an identity that it does not legally or publicly represent, clients:

MUST treat the stack file as unverified

MUST NOT adopt the identity deterministically

MUST mark the domain as a conflicting entity

9. Entity Collision Arbitration

When multiple entities share a lexical identity (e.g., “Apple”):

DFH uses domain ownership to bind canonical identity.

SFH uses /type to distinguish semantic class.

Reasoning proceeds independently within each canonical frame.

10. Compliance (42/42)

A stack file is fully compliant if:

All five primitives exist (5/5)

JSON is valid (1/1)

JSON-LD is valid (1/1)

/canonical resolves (1/1)

Consistency checks (type/url/entity) pass (3/3)

Legal/trademark contradictions do not exist (5/5)

Sitemap(s) resolve (5/5)

DFH constraints followed (10/10)

SFH constraints followed (10/10)

Total: 42/42 compliance.

11. Security Considerations

DFH/SFH does not override legal identity.

Domain-level declarations cannot impersonate trademarked entities.

SFH interpretations are restricted to declared semantic classes.

Protocol integrity depends on HTTPS accessibility and JSON-LD validity.

This protocol introduces zero new attack surface beyond ordinary website hosting.

12. Versioning

DFH/SFH v1.0 follows strict minimalism.
Future versions may introduce OPTIONAL fields but MUST NOT:

break the five primitive contract

alter DFH determinism

distort SFH semantic grounding

DFH / SFH Specification — Version 1.1
Changes from v1.0
1. Abstract (Updated)

Version 1.1 introduces optional extension primitives, improved sitemap expectations, and a clearer canonicalization rubric. Core deterministic behaviors remain unchanged.

2. Additions in v1.1
2.1 Optional Fields

The following MAY be included:

"altCanonical": array of mirrored canonical identities

"api": array of structured API endpoints

"mirror": alternate semantic map hosts

None of these alter DFH determinism.

3. Canonicalization Rubric (Clarified)

Canonical identity resolution now follows:

/canonical

Domain-level authority

Verified entity records

SFH semantic frame

4. Sitemap Expectations (Updated)

Clients SHOULD:

fetch all entries in /sitemap

treat XML sitemaps and semantic maps as equivalent routing indexes

consider priority and modification timestamps when provided

5. Backward Compatibility

Version 1.1 is fully backward compatible with v1.0.
Clients supporting v1.1 MUST support v1.0 without fallback.

6. Compliance Updates

Optional fields do not affect the 42/42 score.
New optional integrity checks may increase total score to 50/50 in v1.1-compliant validators.
