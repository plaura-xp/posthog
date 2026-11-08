# Log Explorer integration conventions

Version 5. Applies to new capability, function, page, REST, MCP and event adapters in this fork.

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

## Shared contract and packaged context

Use the [reviewed shared contract](https://github.com/plaura-xp/astro-craft/blob/355cf9f/docs/architecture/capability-event-presentation.md) with this repository's source boundary.
Qualify each source and environment separately.

Package the guarded handler, route alias, page/workflow identity and source descriptors together.
Publish the path, version and digest of the manifest the host actually selects.
Keep REST and MCP descriptions tied to the same semantic operation.
Preserve other page bindings and existing access-profile declarations.
Test the packaged page and direct API/tool authorization paths.
Source declarations alone do not prove that the delivered adapter contains its metadata.

## Bounded collections and live views

The current explorer uses a seven-day window and a 1,000-event collection ceiling.
Return bounded results with visible truncation instead of implying that the whole source was inspected.
Report exact totals only from the same authorized snapshot when it is not clipped.
Use lower bounds elsewhere and leave unmeasured totals unknown.
Keep ceiling omissions separate from upstream loss, unparsed records, deletion and late arrival.
Only authorized rows may contribute to counts or a truncation sentinel.
Recheck authority before releasing counts and clear them with private records on revocation.

Keep view state and selection through layout and collection changes.
Ordinary selection preserves the wider context; explicit Follow narrows it.
Temporary canvas changes create no notebook records.
Fullscreen Escape must restore focus and preserve modal/menu precedence, including a focused notebook frame.

## Verified delegation and precise Follow

Keep the actual machine actor separate from the human who delegated its authority.
A registration parent or storage owner is insufficient evidence of a current delegator or run controller.
Only the owning API's successful current parent/delegation and final client-revision checks may attach `delegator_reference` with `delegation_basis: verified-parent-authority`.
Independently authorized machines can have no current delegator recorded.
Retain only a trusted same-environment pair; drop incomplete, malformed, untrusted or cross-environment claims before disclosure.
Never put parent subjects, credentials or names into observation payloads.
Delegation does not make the human the performer, broaden their My journey results or establish ownership, causality or Pluto context.
Show the pair as explained source context in the original notebook; do not invent graph edges.
The [owning reference contract](https://github.com/plaura-xp/mybyio/blob/2f191b85e37c381c970f43ac7141a068fd631a75/docs/specs/log-explorer-machine-delegation.md) separates source implementation from hosted producer activation.

A rolling poll captures one exact UTC timestamp window and reuses it for every cursor page.
Do not round source queries through minute-precision form displays.
Refresh completion is distinct from measured source lag; an up-to-date query cannot prove that all earlier source events have arrived.
Keep provider/browser sessions, token authentication and occurrence/receipt clocks distinct.

This guidance adds no collector, API route, notebook mutation, access grant or production activation in this repository.

## Replay requests and capture lifetimes

A selected event, Context router control or original canvas browser-session Source card may request playback through the [closed request interface](https://github.com/plaura-xp/astro-craft/blob/8e0ba88c2306cfb561907d55adb30947ef59acf5/Templates/astro-log-explorer/contracts/replay-request.v1.schema.json).
Notify shared event selection before the explicit playback request, then recheck current source and independent recording authority in the owning host.
Selection alone never opens playback or narrows the feed.
Temporary browser-reference notes link recorded association only and establish no identity, ownership or causality.
The actual player clock moves a presentation cursor; unrecorded gaps and time outside the current canvas page remain explicit.
Clock movement creates no event/note, selects no nearest event and writes no notebook storage.

Replay capture needs a separate explicit choice and a current owning-service permit for an approved non-sensitive surface.
The [capture lifetime guard](https://github.com/plaura-xp/astro-craft/blob/51633c78b734e529b31c61963d936c69d337ade0/docs/architecture/log-explorer-replay-capture.md) remains unmounted source with no product surfaces or recorder SDK adapter registered.
Do not enable it by inheriting ordinary analytics consent or log-read permission.
Stop synchronously before route, DOM or account transitions; an observer after rendering cannot prove exclusion.
Suspend before hidden/bfcache transitions and resume only after current session verification.
Each recorder receives a send lease that stays revoked after replacement; withdrawal must discard buffered/unload dispatches.
Respect DNT/GPC and clear the choice on account change.
A short-lived capture permit cannot prove historical recording scope or authorize a viewer to read recordings.
The actual pinned recorder, separate consent/policy owners, cross-window withdrawal, masking/exclusion canaries and consented provider playback require their own source and environment acceptance.


## Reviewed journey context

Bind each explanation to the recorded source and producer contract version.
Explain sign-in, verification, enrollment and return outcomes in field help and the original notebook Source cards.
A completed sign-in or redirect response does not prove the destination page rendered.
Provider verification does not prove this request sent or consumed an email code.
Unknown or unversioned events must show that a reviewed description is unavailable.

A trusted archive adapter may add a reviewed version after validating the complete producer event.
Keep the immutable queued payload, its hash and the provider request unchanged.
Reject caller-supplied version fields before dispatch.
Preserve first-write archive rows on retries and leave historical missing versions unresolved.
The [MyByIO implementation](https://github.com/plaura-xp/mybyio/blob/ce5858a6/docs/mvp/SHARED_ANALYTICS.md#private-archive-contract-annotation) adds this marker only to the private archive projection.

## Staging feed readiness

The MyByIO staging reader implements six registered product projections.
Cloud and Club collection remains unactivated and requires its owning authentication and consent storage acceptance.
Gateway journey preparation does not register a first-value operation or browser observation capability.
Qualify application, archive-writer and archive-reader rights separately, including cross-store, modification and destructive denials.
Record controlled provider responses separately from actual ingestion, native identity, certificate setup and hosted journeys.
Separate roles in one fixture database do not prove physical environment isolation.
This guide changes no runtime, collector, grant, migration or deployment in this repository.
