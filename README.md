# OceanOPS Linked Data

This repository hosts JSON-LD contexts and related resources for representing [OceanOPS](https://www.ocean-ops.org/) ocean observing metadata as Linked Data.

The objective is to make OceanOPS metadata more interoperable, discoverable and machine-readable by connecting GOOS Passports to established ontologies and authoritative reference vocabularies.

## GOOS Passport JSON-LD

The GOOS Passport describes ocean observing platforms, their deployments, sensors, observations, affiliations and operational status.

OceanOPS is developing a JSON-LD representation of the Passport that preserves the existing JSON structure while progressively adding semantic relationships and persistent identifiers.

The initial implementation uses:

- **[Schema.org](https://schema.org/)** — General descriptive metadata and identifiers.
- **[Observatories of the Seas Ontology (OSO)](https://earthportal.eu/ontologies/OSO)** — Concepts for ocean observing platforms and deployments.
- **[WMO Codes Registry](https://codes.wmo.int/)** — Authoritative references for observed variables, facility types, programme affiliations and other controlled vocabularies.

## Published contexts

### GOOS Passport — v1

[https://oceanops.github.io/oceanops-linked-data/contexts/passport/v1.jsonld](https://oceanops.github.io/oceanops-linked-data/contexts/passport/v1.jsonld)

JSON-LD documents can reference this context using:

```json
{
  "@context": "https://oceanops.github.io/oceanops-linked-data/contexts/passport/v1.jsonld"
}
```

Contexts are versioned to preserve compatibility with previously published records.

## Architecture

JSON-LD records are derived automatically from the canonical OceanOPS Passport JSON cache.

The generation pipeline uses a dedicated PostgreSQL cache, refresh queue and worker, allowing the JSON-LD representation to evolve independently of the underlying Passport metadata.

## Status

**Proof of concept — under development.**

The initial implementation focuses on a small number of semantic mappings. Additional relationships between platforms, deployments, instruments, programmes and observations will be introduced progressively.

Future work may include RDF validation using SHACL and publication of dereferenceable identifiers for individual OceanOPS entities.

## Maintained by

[OceanOPS](https://www.ocean-ops.org/) — Joint WMO-IOC Centre for Oceanography and Marine Meteorology in situ Observations Programme Support.
