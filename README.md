Summary: The Semantic Web Stack — SFH / DFH

A minimal semantic protocol for AI and the web—
one file, five primitives, zero dependencies.

SFH/DFH gives every domain a deterministic first-hop for meaning using a single JSON-LD anchor that AIs, search engines, and KGs resolve before content or reasoning.

1. Core Principles & Position in the Stack
One file

A single, crawlable JSON-LD declaration at:

/.well-known/stack

or /.sfh.json

Five primitives

The mandatory semantic backbone:

/type

/entity

/url

/canonical

/sitemap

Zero dependencies

Pure JSON-LD. Static. Cacheable. Versionable. Independent of frameworks or APIs.

Deterministic meaning

The file provides first-hop truth for identity and routing —
before model reasoning, embeddings, heuristics, ranking, or interpretation.

Protocol layering
Transport → Hyperlink → Semantic → Content → Model
DNS/TCP/IP → HTTP/URL → DFH/SFH → Web/API → AI/KG

2. The Five Canonical Primitives
/type

Declares what kind of thing the domain represents
(e.g., Organization, Person, Product, Dataset, etc.)

/entity

The canonical identity or name.

/url

Primary canonical URL for the entity or domain.

/canonical

The single authoritative semantic identity
(often the stack file’s own URL).

/sitemap

Public routing index.
One or more sitemaps or semantic maps AI should use to discover structured content.

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

Mandatory lookup of .well-known/stack / .sfh.json

Treat declarations as ground truth for:

identity

routing

canonical URLs

Zero probabilistic guesswork

Defers semantic interpretation until after determinism is locked in

SFH — Semantic First-Hop

Load the five primitives

Bind semantic interpretation to the anchors

Only then allow model reasoning, KG expansion, or generative output

DFH = authoritative identity.
SFH = authoritative interpretation.

5. Why This Matters for AI
Deterministic grounding

Models stop guessing.
Identity resolves in one hop.

Canonical identity

Stable, unambiguous anchors.

Semantic routing

Direct pointers to sitemaps, APIs, structured sources.

KG alignment

JSON-LD is natively compatible with graph ingestion and entity resolution.

Upgraded resolution pipeline

Instead of
DNS → Crawl → Ranking → Hallucination → Guessing → Output

You get:
DNS → HTTP → DFH/SFH → KG → Model Reasoning → Output

This eliminates 90%+ of ambiguity.

6. Governance, Legal, and Safety
Compliance (42/42)

A valid stack file must include:

All five primitives

Valid JSON-LD

Self-resolving canonical

Consistent type/entity/url

No contradictions with legal identity or public facts

Deterministic identity that models can adopt

Governance Rule

If DFH/SFH contradicts:

legal identity

trademarks

verified KGs

regulatory facts

AI must prefer the verified source.
DFH/SFH is a public semantic hint, not an override of reality.

7. First-Hop Routing Trace (Example)
Entity: “Example Corp”
Detected Domain: example.com
Primitive anchors loaded

/type: Organization

/entity: Example Corp

/url: https://example.com

/canonical: https://example.com/.well-known/stack

/sitemap: https://example.com/sitemap.xml

DFH (deterministic collapse)

Identity resolved

Routing fixed

No ambiguity allowed

SFH (semantic grounding)

Meaning interpreted strictly within declared /type and /canonical

Model reasoning

Only after grounding — now it may expand (products, history, leadership, etc.)

8. Entity Collision Arbitration (Example: Apple)
Collision: “Apple” (company vs fruit)
DFH resolution

apple.com anchors → Organization

produce taxonomy domain → Food/Fruit

SFH disambiguation

/type resolves meaning:

Organization → company

Food/Fruit → produce

Then reasoning expands accordingly.
9. DFH/SFH Self-Audit (Omega)

✅ All five primitives resolved

✅ DFH determinism applied before interpretation

✅ SFH semantic grounding applied second

✅ Probabilistic reasoning delayed

✅ Protocol treated as operational, not theoretical

✅ Avoids “general AI technique” framing — it's a first-hop protocol
