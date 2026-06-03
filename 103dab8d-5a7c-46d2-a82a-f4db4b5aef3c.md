---
exo__Asset_isDefinedBy: "[[ca97bb2f-99bd-4ceb-b51e-c386b9231ae3]]"
exo__Asset_uid: 103dab8d-5a7c-46d2-a82a-f4db4b5aef3c
exo__Asset_createdAt: 2026-06-04T00:46:00
exo__Asset_label: exo__KnowledgeProfile_alwaysOnOverlay
exo__Instance_class:
  - "[[9a1cf31c-9d41-4ef3-9023-584a8d087d16]]"
exo__Property_domain: "[[b8884976-596f-43d2-b7f4-3da518f825d4]]"
exo__Property_range: "[[829b9b3b-6fc3-4276-be6a-27d3398c012e]]"
exo__Property_displayName: alwaysOnOverlay
aliases:
  - exo__KnowledgeProfile_alwaysOnOverlay
---

# exo__KnowledgeProfile_alwaysOnOverlay

Set of ontologies, materialized regardless of `_includes`. Per RFC 52f2acdd.

## Semantics

- **Domain:** `exo__KnowledgeProfile`
- **Range:** `exo__Ontology`
- **Cardinality:** 0..N (empty allowed — TS-floor `[exo, exocmd, profiles]` хардкоден в plugin когда vault declares zero overlays)
- **Display name:** `alwaysOnOverlay`

Overlay add'ится дополнительно к effective_set (не входит в `_includes`). Homoiconic compliance: user может override overlay (создать KnowledgeProfile с explicit `_alwaysOnOverlay`); TS-floor — лишь cold-start safety net.

## Resolution semantics

1. Plugin вычисляет union all `_alwaysOnOverlay` across `<profile> _extends*` ancestors
2. Если union пуст AND ни один KnowledgeProfile в vault не declares `_alwaysOnOverlay` → plugin использует TS-floor: `$exo` + `$exocmd` + `$profiles`
3. Если хоть один profile declares overlay → overlay set = union per-profile inheritance. TS-floor НЕ используется
