# Lesson 01 specification

## STUDIO-001 · Launch a tested calculator on an existing server

**Status:** Hosted verification passed; learner reports successful phone and laptop use. Learner review and publication approval received; GitHub CI/PR completion pending.
**Next step:** Verify all three latest CI jobs on [PR #2](https://github.com/dan38-cmyk/my-server-studio/pull/2) before an owner-approved merge, then confirm issue closure and final main checks.
**Instructor implementation:** [issue #9](https://github.com/kaw393939/373_hosting/issues/9).
Create your own issue from the [lesson template](.github/ISSUE_TEMPLATE/studio-calculator.md).

## Agreed result

Launch the supplied published calculator image through your existing Traefik
network and a nonconflicting HTTPS hostname. Preserve unrelated services and
host access. Do not add another proxy/updater or build a substitute image.
The [release selection](studio/calculator-release.json) supplies the expected
commit and multi-platform digest independently of the running website.
An explicitly agreed adoption of a matching existing deployment is recorded
as adoption, not a fresh launch. This bounded lesson does not certify the whole
server baseline or a vulnerability-free image.

- **Public hostname:** https://dan38-calc.duckdns.org — trusted HTTPS passed during hosted verification on November 5, 2026; learner reports laptop access on November 6.
- **New launch or adopted deployment, and reason:** New calculator container created on a separate hostname to preserve the existing Apache site. Initial launch failed its HTTPS check; a calculator-only TLS override repaired the route. Successful evidence is a subsequent `already-managed` verification, not a successful initial-launch report.
- **Own issue / feature branch:** [Issue #1](https://github.com/dan38-cmyk/my-server-studio/issues/1), independently verified open with the required `STUDIO-001` marker; branch `studio-001-calculator`; [PR #2](https://github.com/dan38-cmyk/my-server-studio/pull/2) is open and targets `main`.
- **Agreed scope or actual access/configuration gap:** Learner approved one image-only calculator launch using the existing Traefik network `hosting373-ip-web`, preserving the existing Apache site. Learner-provided CLI doctor output reports `ready`, `launch-new`, `mutates: false`, and two existing containers. Server-side HTTPS for the existing site returned HTTP 200; laptop access reset on school Wi-Fi, with filtering suspected but unconfirmed.

**Selected release:** [published image selection](studio/calculator-release.json), pinned to `docker.io/kaw393939/is373_ci_cd@sha256:aec414c990a5de6ed74c9e8dcb105b78f6358c03a8cea70a9d40dcda51c3a8fa`, expected [source commit](https://github.com/kaw393939/is373_ci_cd/tree/4600202bad42da0c5ffb11d83ce8364671293d3d). The selection links its [publication run](https://github.com/kaw393939/is373_ci_cd/actions/runs/36904255716); this chat has not independently checked that run's latest state.

**HTTPS diagnostic and scoped repair:** Learner shared a launch failure after the calculator started, followed by server-side curl reporting a self-signed certificate at the calculator hostname. The existing Apache router explicitly selects `letsencrypt`; the generated calculator router does not. The learner applied the [calculator-only Compose override](studio/calculator-tls-override.json), selecting that existing resolver and enabling TLS on only the calculator router. Subsequent hosted verification passed. Existing proxy and Apache configuration were not edited. To reproduce the repaired configuration, use both the generated `compose.json` and this override with the calculator Compose project; the unmodified CLI generator does not include these extra TLS labels.

Private SSH targets and configuration stay in ignored local state. Share only
reviewed, selected evidence; never commit credentials or raw server output.

## Evidence to keep

| Evidence | Actual result / link |
|---|---|
| Prepared Black/Pylint/pytest and real-image browser checks | Black and Pylint passed; fast pytest: 91 passed, 2 deselected on November 5. Local E2E unrun because Docker daemon was unavailable. Full browser E2E runs in the [PR studio job](https://github.com/dan38-cmyk/my-server-studio/pull/2/checks); local E2E remains unrun. |
| Hosted image/commit, trusted HTTPS, valid and rejected API cases | Passed November 5: [sanitized evidence](studio/evidence.json). Multiplication returned 42/HTTP 200; division by zero returned 400; numeric string returned 422. |
| Preservation of unrelated services | Two other containers had unchanged identity, state and published ports during verification. This does not establish uninterrupted preservation across the earlier failed launch and repair. |
| Own prediction, check interpretation, browser observation and keep/revise reason | [LEARNING.md](LEARNING.md): learner reports arithmetic testing on phone/laptop and matching browser/API results for 6 × 7 = 42. Learner prefers a realistic calculator layout and more advanced math as future improvements, outside this image-only lesson. Original prediction and a learner explanation of test limits remain missing; assistance disclosed. |
| Accuracy review before publishing learner excerpts | Learner reviewed the corrected test statement and revision preference and explicitly authorized commit/push. |
| Actual PR, latest CI, merge and issue closure | [PR #2](https://github.com/dan38-cmyk/my-server-studio/pull/2), [latest CI checks](https://github.com/dan38-cmyk/my-server-studio/pull/2/checks). Verify `studio`, `validate` and `integration-contract` success before owner-approved merge; verify issue #1 closure and final main checks afterward. |

The exported [studio/evidence.json](studio/evidence.json), [issue #1](https://github.com/dan38-cmyk/my-server-studio/issues/1) and [PR #2](https://github.com/dan38-cmyk/my-server-studio/pull/2) are linked above. [CI run](https://github.com/dan38-cmyk/my-server-studio/actions/runs/42328155052) is the initial PR run; use the PR’s latest checks for later evidence-only commits.
CI does not deploy this server. A fixture, green check, timestamp, closed issue
or AI assertion alone does not establish the full result. `status` reports
recorded evidence and readiness for instructor review; it does not grade,
certify authorship or establish understanding.

## Optional instructor history

The records below are background, not steps to repeat. Their original anchors
remain here so earlier links continue to work.

## HOST-001 · Keep the Traefik dashboard private

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-001--keep-the-traefik-dashboard-private).

## HOST-002 · Controlled host maintenance

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-002--controlled-host-maintenance).

## HOST-003 · Companion image security maintenance

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-003--companion-image-security-maintenance).
