# A proposal to dating apps: say when something is AI-generated

This is the ask at the center of the whole repo. Dating apps should tell users when the content on a profile was generated or manipulated by AI, the same way Pinterest, Meta, and TikTok already label AI images. Right now the apps verify that a real person exists and market that badge as if it also vouched for the photos. It does not. This proposal closes that gap.

## Scope

This repo, and this proposal, is specifically about content provenance for the parts of a profile you judge someone on first: **images, video, and voice or audio**. Those are the highest-stakes first-impression signals, they are where a fabricated persona does its work before you can catch it in person, and they are the content that today's provenance and detection tools can actually mark. Text is the harder case, because a short chat message carries no durable metadata and defeats current text watermarks, so I treat text provenance as a future direction rather than a present demand. Down the line I hope the same asks extend to bios and messages. For now, the demand is scoped to what is buildable: visual and audio provenance.

The broad risks of AI in dating (AI matchmaking, AI companions, AI-written openers, engagement-driven design, privacy and data-selling) are real and are mapped in [landscape.md](landscape.md). This proposal does not try to solve all of them. It solves one thing well: making it visible when a photo, a video, or a voice on a dating profile was made or altered by AI.

## Why now

The timing is good, not bad. Two transparency regimes went live on 2 August 2026, the EU AI Act's Article 50 and California's SB 942, and both push the duty to mark AI content onto the tools that generate it. That means a compliant AI image should increasingly arrive already carrying a machine-readable credential. The dating app's job is then small: read the mark and show it. The apps are not being asked to invent detection from scratch. They are being asked to surface a signal that other platforms already surface and that regulation is increasingly forcing into the content itself.

## The full list of demands

1. **Label AI-generated and AI-modified visual and audio content, visibly.** Put an "AI-generated" or "AI-modified" tag on photos, video, and voice notes that are synthetic or substantially altered, shown to the viewer at the point they see the content. This is the Pinterest model, and it is the core demand. Everything else supports it.

2. **Read content credentials.** Ingest and display C2PA Content Credentials when a file carries them, the way TikTok and LinkedIn already do. When the provenance travels with the file, show it.

3. **Detect on a best-effort basis, metadata first.** Where no credential is present, run classifier-based detection as a fallback, exactly the metadata-first, classifier-fallback approach Meta and Pinterest use. Do not wait for perfect detection, because it does not exist. Label on a best-effort basis and correct mistakes.

4. **Build an appeals process.** Because detection produces false positives, and a false "AI" flag on a real person's genuine photo is a real harm, every label must be appealable to a human. Pinterest ships this. So should dating apps.

5. **Stop conflating identity and content in the interface.** The verified badge should clearly say what it certifies, which is that a live human matches the uploaded photos, and clearly not imply that the photos themselves are real. Two different claims, two different signals.

6. **Cover the video call.** Deepfake video calls are now used to defeat the "ask them to video chat" defense. In-app video should run liveness and manipulation checks, and the app should tell users that a live call is not proof of authenticity on its own.

7. **Cover voice and audio.** Voice notes and audio should carry the same provenance treatment as images, because voice cloning is cheap and voice is increasingly part of the profile.

8. **Offer voluntary self-disclosure too, and design it honestly.** Keep a user-facing option to disclose AI use (Bumble's "AI-assisted" badge is a start), but pair it with platform detection, and label real and human content too where feasible, so that the absence of a label does not falsely certify the fakes that slip through. Partial labeling can backfire, and honest design is how you avoid it.

9. **Publish real numbers.** Release transparency reporting on how much AI content is detected, labeled, and removed, with methodology. Right now the only figures are unaudited vendor claims. A credible labeling program shows its work.

10. **Keep verification privacy-preserving.** Favor on-device and data-minimizing checks over mandatory government ID and permanent biometric storage, so the safety feature does not exclude people without ID or concentrate unresettable face data. Verification should not trade one harm for another.

11. **Join the standards, do not fork them.** Support C2PA and the Content Authenticity Initiative industry-wide, so provenance is interoperable across the apps rather than a per-company silo that a screenshot defeats.

12. **Make disclosure consent infrastructure, not a ranking signal.** Surface provenance to help two people decide whether to meet on accurate information. Do not turn a user's disclosure into an input that quietly buries them in the algorithm, because the moment labeling becomes a mandatory, ranked verdict it stops being safety and becomes the permission system critics rightly warn about.

## The tools already exist

None of this requires an invention. The technologies that could address the provenance gap are already shipping, mostly on other platforms:

- **C2PA and Content Credentials.** An open, cryptographically signed provenance standard, already read by TikTok and LinkedIn and written by OpenAI's image tools and a growing list of camera makers.
- **Platform labeling pipelines.** Pinterest ("AI modified"), Meta ("AI Info"), and TikTok run live, at-scale, metadata-first-plus-classifier labeling with appeals. The template exists.
- **Watermarking.** Google's SynthID marks images, audio, video, and text from participating models, and Meta's Video Seal watermarks AI video. These mark good-faith AI at the source.
- **Deepfake detection vendors.** Match Group already partners with Reality Defender to screen profile images, and firms like Reality Defender, GetReal, and Hive sell image, video, and audio detection. The capability is in-house or one integration away.
- **Liveness and behavioral detection.** FaceTec-style liveness and Bumble's behavioral "Deception Detector" already exist inside these apps. They just do not surface a content-provenance signal to the user.

The gap is not technical capability. It is a product and policy choice, and this proposal asks the apps to make the other choice.

## The honest caveats I am keeping in

I am not claiming labeling fixes dating, and I am putting the strongest objections right here so the proposal is credible.

Labeling can backfire if it is partial or blunt. Warning only the fakes you catch can make people trust the fakes you miss, and a flat "AI" label can unfairly tar honest AI-assisted content. Demand 8 is my answer, but it is a mitigation, not a guarantee.

Detection is imperfect, and a false flag on a real person is a real harm. Demand 4 (appeals) exists because of this, not in spite of it.

Verification can curdle into surveillance. Demands 10 and 12 exist to keep this consent infrastructure rather than a gatekeeping layer, which is the risk I take most seriously.

And a motivated adversary using a self-hosted generator produces content with no mark to read. This proposal raises the cost and improves the signal for good-faith and lazy-bad-faith content at scale. It does not defeat a determined scammer, and I will not pretend it does. The point is that the current signal is actively misleading, and a best-effort honest one is better than that.

Full evidence and grading is in [SOURCES.md](SOURCES.md). The argument behind the proposal is in [ARGUMENT.md](ARGUMENT.md). What you can do while the apps catch up is in [protect-yourself.md](protect-yourself.md).
