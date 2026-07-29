---
exo__Asset_isDefinedBy: "[[ca97bb2f-99bd-4ceb-b51e-c386b9231ae3]]"
exo__Asset_uid: abdb56bc-c1a1-4b95-978a-e9e2ea1c57dc
exo__Asset_createdAt: 2026-05-25T01:15:00
exo__Asset_updatedAt: 2026-05-25T01:15:00
exo__Asset_createdBy: "[[de20a3f1-7483-4714-ab28-b45f5cf02c76]]"
exo__Instance_class:
  - "[[ae56ca4c-b610-42a4-a25d-058c23673296]]"
exo__Property_domain: "[[493c2ae2-de56-47ec-954d-2eb8cb49bff7]]"
exo__Property_description: "Obsidian-native aliases list. Multi-valued literal strings. Cardinality 0..N. Formally declared as exo__DatatypeProperty so PropertyDefault references can target it via SHACL-valid wikilink (range exo__Property)."
exo__Asset_label: aliases
exo__Slugable_slug: "aliases"
aliases:
  - aliases
exo__Property_displayName: aliases
---

# aliases

`exo__DatatypeProperty` on `exo__Asset`. Multi-valued list of literal strings. Cardinality 0..N.

This property is Obsidian-native (used by the Obsidian app for note linking by alternate names). RFC 727572d2 declares it formally so RDF-driven creation can reference it from `exocmd__PropertyDefault_property` wikilinks without SHACL violations.

YAML serialization:
```yaml
aliases:
  - "Some alias"
  - "Another alias"
```
