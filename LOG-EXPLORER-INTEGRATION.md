# Log Explorer integration conventions

Version 1. Applies to new capability, function, page, REST, MCP and event adapters in this fork.

## Capability descriptions

Declare stable page, control and operation identifiers, owning product/service, contract version, actual environment and implementation readiness.
REST OpenAPI and typed MCP schemas must describe the same domain operations.
Use readable labels, field meanings, expected outcomes, missing-data states and current permission requirements.
Capability discovery, UI visibility and selecting a graph node confer no execution authority.

## Events and identity

Separate attempted invocation, transport completion, tool result and committed business outcome.
Emit mutation success after commit once; transaction retries do not create another success.
Mark an operation receipt replay as a repeated invocation rather than another mutation.
Preserve provider event identity separately from application event identity, and occurrence time separately from receipt time.

Use references derived from verified owning-service context for human/machine actors, acting Pluto context, provider sessions and machine authentication.
A browser SDK session is a distinct reference.
Keep actual actor, controller/delegator and storage owner separate.
Names, email, IP, tags and time proximity cannot establish identity, ownership or causality.
Chronological order can group events without creating a causal edge.
Historical context that was not recorded remains unavailable.

## Disclosure and presentation

Apply current source, environment, tenant/Pluto and field authority before data, counts, facets, graph edges, descriptions or recording metadata reach the client.
Bind pagination to the exact authorized query and collection.
Report loaded/partial counts, source lag and unavailable states.
Explain card types and attributes through reviewed source/version metadata; unknown meanings remain unavailable.

Use the existing shared notebook renderer for notebook views.
Temporary event projections create no saved notebook records.
Explicit workflow drafts retain reusable action definitions and protected evidence references.
Viewing, saving or editing a draft never invokes the represented operation.
Recheck source rights when resolving evidence, including history and sharing paths.

## Collection and qualification

Keep credentials, tokens, private content, input values, raw queries, arbitrary URLs and request/response bodies out of product telemetry.
Security audit, provider diagnostics and optional browser analytics have separate collection and retention policies.
Replay requires separate opt-in capture on approved surfaces and independent playback authorization.
Respect withdrawal and account changes; exclude sensitive authentication and private-content screens.

For each new adapter, record its source/schema/build pin, supported filters, permitted fields, capture policy and actual readiness.
Test semantic outcomes, duplicate prevention, retry and tool-error paths, current revocation, cross-scope denial, unavailable sources and content/secret canaries.
Qualify stored event delivery and any replay playback independently from successful HTTP responses.
Source checks, isolated fixtures, CI, hosted staging and production are separate evidence.
This document installs no collector, grants access to no source and changes no runtime setting.

## Owning-source boundary

Keep provider instance, project, producer environment and application distinct. SDK distinct IDs and browser sessions are observations rather than authorization principals. Recording access and capture consent are independent.
