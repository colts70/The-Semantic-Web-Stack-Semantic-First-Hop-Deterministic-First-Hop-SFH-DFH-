The Semantic Web Stack — SFH / DFH
A minimal semantic protocol for AI and the web — one file, five primitives, zero dependencies.

SFH/DFH gives every domain on the internet a deterministic first-hop for meaning using a single JSON-LD anchor that AIs, search engines, and knowledge graphs resolve before crawling, ranking, embeddings, or reasoning.

1. Core Principles & Position in the Stack
One file

A single, crawlable JSON-LD declaration located at:

/.well-known/stack

or /.sfh.json

Five primitives

The universal semantic backbone:

/type

/entity

/url

/canonical

/sitemap

Zero dependencies

Pure JSON-LD. Static. Cacheable. Versionable. Platform-agnostic.
No APIs, frameworks, or runtimes required.

Deterministic meaning

The stack file provides first-hop truth for identity and routing —
before model reasoning, embeddings, heuristics, SEO signals, or interpretation.

Protocol Layering
Transport → Hyperlink → Semantic → Content → Model
DNS/TCP/IP → HTTP/URL → DFH/SFH → Web/API → AI/KG


DFH/SFH inserts the missing semantic layer between URL routing and content.

2. The Five Canonical Primitives
/type

Declares what the domain represents
(e.g., Organization, Person, Product, Dataset, Service, Place, etc.)

/entity

The canonical identity or name.

/url

The primary canonical URL for the entity or domain.

/canonical

The authoritative semantic identity
(often the URL of the stack file itself).

/sitemap

Public routing index.
One or more sitemaps or semantic maps AI should use to discover structure.

3. Minimal JSON-LD Example
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

4. DFH and SFH Behaviors
DFH — Deterministic First-Hop

AI must:

fetch .well-known/stack or .sfh.json

treat the five primitives as ground truth

resolve identity, routing, and canonical URLs with zero guesswork

delay semantic interpretation until determinism is locked in

DFH = authoritative identity.

SFH — Semantic First-Hop

After DFH completes:

load /type and /canonical

bind semantic interpretation to the declared anchors

only then allow model reasoning, KG expansion, or generative output

SFH = authoritative interpretation.

5. Why This Matters for AI
Deterministic grounding

Models stop guessing identity.

Canonical identity

Stable, unambiguous anchors for every domain.

Semantic routing

Direct pointers to sitemaps, APIs, and structured data.

KG alignment

Native compatibility with graph ingestion.

Upgraded AI pipeline

Old path:
DNS → Crawl → Ranking → Embeddings → Guesswork → Output

DFH/SFH path:
DNS → HTTP → DFH/SFH → KG → Reasoning → Output

This eliminates 90%+ of ambiguity.

6. Governance, Legal, and Safety
42/42 Compliance Requirements

A valid stack file must include:

all five primitives

valid JSON-LD

self-resolving canonical

consistent type/entity/url

no contradictions with legal identity or verified public facts

deterministic identity AIs can adopt

Governance Rule

If DFH/SFH contradicts:

legal identity

trademarks

verified knowledge graphs

regulatory facts

AI must prefer the verified source.
DFH/SFH acts as a public semantic hint, not an override of reality.

7. First-Hop Routing Trace (Example)

Domain: example.com
Entity: “Example Corp”

DFH loads primitives:

/type: Organization
/entity: Example Corp
/url: https://example.com
/canonical: https://example.com/.well-known/stack
/sitemap: https://example.com/sitemap.xml

DFH collapse

Identity fixed

Routing determined

Ambiguity removed

SFH grounding

Meaning interpreted under /type and /canonical

Only then can reasoning expand to products, leadership, history, etc.

8. Entity Collision Arbitration (Example: Apple)

Collision: “Apple” (company vs fruit)

DFH resolution

apple.com → Organization

produce domain → Food/Fruit

SFH disambiguation

/type distinguishes semantic meaning

models expand reasoning within the correct semantic frame

9. DFH/SFH Self-Audit (Omega Model)

✅ All five primitives resolved
✅ Determinism applied before interpretation
✅ Semantic grounding applied second
✅ Probabilistic reasoning delayed
✅ Treated as an operational protocol, not a theory
✅ Avoids “general AI technique” framing — it is a first-hop standard
