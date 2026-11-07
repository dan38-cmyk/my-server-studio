# Lesson 01 · Conversation evidence

AI-drafted task summary, not a transcript or grade. It may be public. Use actual
short quotes or labeled paraphrases, name any help supplied, and link actual
work. Leave missing contributions Pending. A learner can review, correct or
remove excerpts before publication; accuracy approval is not proof of learning.
Label role-play honestly rather than treating it as an actual learner response.

**Lesson:** STUDIO-001. **Available conversation context:** This coaching chat, November 4–6, 2026. Learner reviewed the corrected test statement and revision preference before publication.

## Prediction

Pending. Learner asked AI to handle routine work. AI supplied a hint: DNS finds the server, and Traefik uses the hostname to select a container. No learner prediction recorded.

## Check interpretation

Learner statement, edited for grammar: “I tested 6 × 7 and got 42 in both the browser and the API result. This showed that the tested multiplication worked correctly.” A learner explanation of what the check leaves untested has not been supplied. AI previously explained the difference between API and browser evidence.

## Browser observation

Learner reported testing multiplication, addition, subtraction and division in laptop and phone browsers. They later supplied this specific comparison: “I tested 6 × 7 and got 42 in both the browser and the API result.” Wording edited for grammar; the API-panel observation is learner-reported, separate from automated verification.

On November 6, after being asked to open the calculator on the laptop using work Wi-Fi, learner said: “yea the calculator loads and works”.

Earlier school-Wi-Fi HTTPS requests reset despite correct DNS. The precise cause remains unconfirmed; the successful work-Wi-Fi observation does not by itself establish the cause.

## Keep decision

Revision preference, edited for grammar: “I would prefer a layout that looks like a real calculator and supports more advanced math problems.” This records a requested future improvement, not a feature implemented in this lesson or an approval to change the supplied application image. The current assignment remains the tested deployment of that image.

## Review

Learner approved the corrected test statement and future-revision preference in this chat. Learner explicitly authorized commit/push of the four reviewed Server Studio files; merging remains a separate decision. AI helped correct grammar; implementation and diagnostic help are described below.

## AI work and next step

AI completed local setup and fast checks (91 tests passed; local E2E unrun), prepared the plan and calculator-only TLS override, and exported [sanitized verification evidence](studio/evidence.json). With AI-provided commands, the learner established server access, created the calculator hostname and [issue #1](https://github.com/dan38-cmyk/my-server-studio/issues/1), approved scope, ran the launch, applied the TLS repair and ran verification. AI explained DNS, Traefik routing, containers and the difference between API and browser evidence. Initial launch failed HTTPS; the later successful report describes verification of an already-managed container. No successful initial-launch report is claimed.

[PR #2](https://github.com/dan38-cmyk/my-server-studio/pull/2) contains the approved records; actual CI links are in [SPEC.md](SPEC.md). Next: verify latest full CI and owner-approved PR/issue completion. The original prediction and the learner's explanation of test limits remain missing after offered hints; no retrospective answer is invented. Publication is authorized; the remaining gaps stay explicit in the published record.
