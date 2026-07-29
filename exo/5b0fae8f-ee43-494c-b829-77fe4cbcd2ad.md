---
exo__Asset_isDefinedBy: "[[ca97bb2f-99bd-4ceb-b51e-c386b9231ae3]]"
exo__Asset_uid: 5b0fae8f-ee43-494c-b829-77fe4cbcd2ad
exo__Asset_createdAt: 2026-07-12T00:29:37+05:00
exo__Asset_updatedAt: 2026-07-12T00:29:37+05:00
exo__Instance_class:
  - "[[ae56ca4c-b610-42a4-a25d-058c23673296]]"
exo__Property_domain: "[[07eab746-0874-4676-9d98-dbaad1bc6fb8]]"
exo__Asset_label: exo__DisplayNameSpec_matchHostFunction
exo__Slugable_slug: "DisplayNameSpec_matchHostFunction"
aliases:
  - exo__DisplayNameSpec_matchHostFunction
exo__Property_displayName: match host function
---

Computed / host-function условие для conditional-специализации exo__DisplayNameSpec. Domain exo__DisplayNameSpec (**DatatypeProperty**). Range **xsd:string** — имя зарегистрированной display-matcher host-функции (напр. `isEffortBlocked`), НЕ wikilink. Cardinality **0..1** (spec без matchHostFunction = unconditional либо value-equality). В отличие от matchPath/matchValue (равенство по СОБСТВЕННОМУ frontmatter инстанса), host-функция — предикат, вычисляемый движком **на каждый рендер** из `(app, метаданные инстанса)`, поэтому он может резолвить ДРУГИЕ ассеты (**cross-asset** предикат; напр. `isEffortBlocked` читает `ems__Effort_blocker`, резолвит тот ассет, проверяет ЕГО статус). Spec участвует в отборе (`PrintNameRuleService.selectRule`) только когда названная функция вернула true; отбор среди участвующих — по exo__DisplayNameSpec_priority. Незарегистрированное имя → spec никогда не участвует (fail-closed). v2 single-matcher срез: spec несёт ЛИБО value-equality (matchPath/matchValue), ЛИБО host-function; конъюнкции = будущий exo__DisplayNameMatcher. Первая зарегистрированная функция — `isEffortBlocked`. RFC 92b91345 §v2 computed-срез, req d6cd2371, issue #3865.
