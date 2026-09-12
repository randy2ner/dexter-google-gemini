# Compass Customer Work Lifecycle Fixture v1

## Purpose

Exercise the disconnected Installation/Scan/Governor/Curator journey with fictional data and provide concrete examples of the canonical schema in [the Knowledge Graph Specification](../../specifications/knowledge-graph.md).

## Fixed review context

- Review instant: `2026-09-12T17:00:00Z`
- Graph timezone: `America/Los_Angeles`
- Default stale threshold: 14 days
- Inclusive stale cutoff: `2026-08-29T17:00:00Z`

## Baseline inventory

- One CSP
- Three active Efforts: stale, current, and recency-uncertain
- Two People
- Three Activities
- One Daily Log
- One synthetic evidence file containing customer and excluded non-customer items

## Expected classifications

- `effort:20000000-0000-4000-8000-000000000001` is stale from reliable Activity time.
- `effort:20000000-0000-4000-8000-000000000002` is current.
- `effort:20000000-0000-4000-8000-000000000003` remains uncertain because Teams continuation is incomplete.

## Prohibited uses

This fixture contains no real identities or work content. Do not replace fictional values with production data, use expected outcomes as runtime evidence, or treat disconnected success as Cowork capability proof.