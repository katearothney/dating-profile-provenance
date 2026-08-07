# The matrix

A working map of the provenance question on dating apps, scoped to images, video, and voice. It comes in two parts. The first is the problem: why the people using these apps cannot sort real from synthetic on their own, which is the reason a control has to be built into the platform at all. The second sorts the actual state of the tools by what kind of thing each one is, because a flat list of thirteen rows buried the distinction that matters most. Some items are problems the fix has to solve. One is a fix that already works elsewhere. Several are caveats that keep the fix honest. Evidence is graded, the counter-evidence stays in, and every empirical claim links to its source. This is a living document and it is not finished.

## At a glance

Each cell is the current state of play. The empty and weak cells are the point.

| | Provenance and watermarking | Automated detection | Disclosure and labeling | Identity verification |
|---|---|---|---|---|
| **The person** | not built for this | duplicate-face checks | | badge confirms a live human |
| **The images** | C2PA exists, apps do not read it | unreliable both ways | Bumble optional badge, no dating app labels at scale | badge binds a face to user-supplied photos, not their origin |
| **The words** | nearly empty | weak on short text | almost none | not applicable |

## The frame

Rows are the three channels of dating-app self-presentation from the communication and HCI literature: the person, the images, the words. Toma and Hancock treat visual and textual deception as separate problems in ["Looks and Lies"](https://doi.org/10.1177/0093650209356437), Ellison, Heino and Gibbs frame the profile as managed self-presentation ([2006](https://doi.org/10.1111/j.1083-6101.2006.00020.x)), and Ivan notes that research focused on textual deception and left synthetic images understudied ([2025](https://doi.org/10.1016/j.chbah.2025.100208)).

Columns are the intervention layers from [NIST AI 100-4](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-4.pdf): provenance tracking (metadata and watermarking), automated detection, and human-facing labeling and disclosure. I add identity verification as a fourth column because it is the control the apps already ship.

Crossing these two into a grid is a modeling choice. Placing an item under one channel when it touches two is a judgment call, and I have tried to say so where it happens.

## The map, sorted by kind

The same findings, grouped by what they actually are. Full evidence for each row is in the matching section below.

### The problems, the reasons a fix is needed

| Problem | Channel | Layer | Evidence |
|---|---|---|---|
| The verified badge checks the face, not the photos | Person | Identity | Strong |
| People cannot tell AI faces from real ones | Images | Detection (human) | Strong |

### What already works, just not on dating apps

| What exists | Channel | Layer | Evidence |
|---|---|---|---|
| Pinterest, Meta, and TikTok label AI images at scale | Images | Disclosure | Moderate to Strong |

### The caveats that keep the fix honest

| Caveat | Channel | Layer | Evidence |
|---|---|---|---|
| Content provenance travels but is strippable | Images | Provenance | Strong |
| Watermarks mark only cooperating models, and come off | Images | Provenance | Strong |
| Automated image detectors are unreliable both ways | Images | Detection | Moderate |
| Partial or "AI" labeling can backfire | Cross-cutting | Disclosure | Moderate |
| Detection and provenance lose to a motivated adversary | Cross-cutting | All | Moderate |
| Biometric verification has its own privacy and exclusion cost | Person | Identity | Strong to Moderate |

### What lives elsewhere

Two things that showed up in the old flat list belong in other files, and are covered there in full. How AI shows up in profile text (AI-written messages that lower trust, fabricated personalities that do not survive a first date) is part of the wider picture in [landscape.md](landscape.md), not the scoped provenance demand. The legal picture (no law currently requires a dating app to label AI photos, and the rules that exist aim at generators) is in [policy.md](policy.md). Text provenance itself, the weakest case of all, gets its own short section at the end.

---

# The problems

## The verified badge checks the face, not the photos
- **Layer.** Identity verification
- **Established construct.** Identity verification versus content authentication are different problems. A liveness check binds a live face to an account. It says nothing about the provenance of the account's media.
- **What AI touches.** Nothing in the check itself. The gap is that the check was never meant to test whether the uploaded photos are real, and users read the badge as if it were.
- **What the research shows.** Hinge's Selfie Verification runs a liveness check plus 3D face authentication comparing a video selfie to the profile photos, and the help page states plainly that the feature "doesn't guarantee the safety of a particular user" ([Hinge Help](https://help.hinge.co/hc/en-us/articles/10303221435539-What-is-Selfie-Verification)). Tinder's Photo Verification confirms "a real, live person" whose face matches the profile photos and adds that it "doesn't guarantee the identity or safety of a particular user" ([Tinder Help](https://www.help.tinder.com/hc/en-us/articles/4422771431309-How-Does-Photo-Verification-Work)). A fraud-prevention analysis put it directly: selfie verification "validates only a single moment of interaction" and does not confirm whether photos "are authentic, AI-generated, or stolen" ([ConsumerAffairs, 2026](https://www.consumeraffairs.com/news/tinders-verification-tool-isnt-foolproof-heres-why-scammers-are-still-slipping-through-042426.html)). A 2026 cybersecurity playbook makes the same point plainly, that a verified badge proves liveness and adult ID but "does not prove definitively that the person you're talking to isn't a fraudster," and that continuous identity verification is "not officially standardized as of yet" ([ESET, 2026](https://www.eset.com/blog/en/home-topics/privacy-and-identity-protection/staying-safe-on-dating-apps/)). An undercover reporter demonstrated the gap concretely, getting a scammer to produce in seconds an AI selfie holding a paper with her name and the date, defeating the "send a selfie to prove you are real" test ([WBAL, 2026](https://www.wbaltv.com/article/ai-romance-scams-deepfake/70315255)). The exploit is not only demonstrated, it is taught and monetized. A 2026 YouTube tutorial ("AI Dating Photos: 6 Mistakes That Get You Banned") coaches users to make AI photos that still resemble their real face precisely so they clear verification, telling viewers "if you actually look like your AI pictures, you can get verified on dating apps like I did" and that once verified, "what can the girl say" ([YouTube, accessed August 2026](https://www.youtube.com/watch?v=OtPM34oOaRU)). It is the identity-versus-content gap repackaged as a growth tactic, a genuine live face over fabricated photos and scenes, with women named as the target. A paid photo service runs on the same principle, building its whole method around making the AI images still look like the real client so they clear the face-match check ([YouTube, accessed August 2026](https://www.youtube.com/watch?v=4eme37OGihk)). Counter-evidence that this is not the whole picture: Match Group added Reality Defender to screen profile images for AI manipulation and reported that 99.4 percent of a sample showed no concerning manipulation, and that most flagged cases were ordinary face-tuning filters rather than deepfakes ([Match Group, 2025](https://mtch.com/single-news/1022/)). That number is a vendor self-report with no published method, and the screening is a separate system from the badge, so passing verification does not run it.
- **Threat mechanism.** The badge answers "is a real person here who looks like these pictures." A bad actor who controls both the selfie and the uploads (stolen or AI images of a face that is genuinely theirs, or theirs plus fabricated context) satisfies that and still misrepresents.
- **Who it hits hardest.** Anyone who reads the check as proof the photos are real, which is most people, since the badge is marketed as "they really look like their photos."
- Evidence: **Strong** for what the badge does and does not certify. **Contested** for the claim that on-platform AI photos are rare, since that rests on one unaudited vendor figure.

## People cannot tell AI faces from real ones
- **Layer.** Detection (human)
- **Established construct.** Truth-default theory. People treat photographs as records of reality and do not enter suspicion mode without a trigger, which leaves them open to synthetic images.
- **What AI touches.** Text-to-image and face-generation models produce fully synthetic faces with no real referent, not edits of a real photo.
- **What the research shows.** In an experiment with 831 US online daters, detection of AI-generated profile photos was 42.8 percent, statistically below chance, while real photos were identified 82.7 percent of the time ([Ivan, 2025](https://doi.org/10.1016/j.chbah.2025.100208)). Women detected AI images somewhat better than men (46.6 versus 39.8 percent) but also misclassified real photos as fake more often, a heightened but sometimes misplaced skepticism. In a PNAS study, participants classified synthetic faces at 48.2 percent, below chance, and after training only reached 59 percent, and separately rated synthetic faces as about 7.7 percent more trustworthy than real ones ([Nightingale and Farid, 2022](https://doi.org/10.1073/pnas.2120481119)). A representative multi-country study found human detection of generated media hovering near a coin toss ([Frank et al., 2024, IEEE S&P](https://doi.org/10.1109/SP54263.2024.00058)). Counter-evidence: the Ivan and PNAS stimuli were clean portraits on plain backgrounds, not full profiles, so ecological validity to real app browsing is untested, and the trust gap is small.
- **Threat mechanism.** Ivan's "learning loop." Users lean on cues like distorted hands, and as models fix those cues the heuristics go stale, so detection ability lags generation permanently. The loop now has a supply side: a 2026 YouTube tutorial walks viewers through scrubbing exactly these tells (AI skin, warped hands, mismatched lighting, gibberish background text, distorted background faces) so a synthetic photo stops tripping them, which is the learning loop sold as a service ([YouTube, accessed August 2026](https://www.youtube.com/watch?v=OtPM34oOaRU)). That supply side is now a small market rather than one video. A paid service advertises AI dating photos made for more than 150 clients and coaches them away from the obvious tells so the images are not flagged or banned ([YouTube, accessed August 2026](https://www.youtube.com/watch?v=4eme37OGihk)), and first-person "I tried it for a week" videos report the match count jumping and insist no one can tell ([YouTube, accessed August 2026](https://www.youtube.com/watch?v=uF1L2Gbkt9I)).
- **Why training does not rescue it.** Visual-literacy training helped only marginally and can tip women toward flagging real photos, so "just be more careful" makes things worse for some people.
- **Who it hits hardest.** Everyone, with a specific twist that heightened suspicion makes women more likely to reject real people as fake, which is its own cost.
- Evidence: **Strong**. Multiple experiments, one preregistered, consistent direction, with the honest caveat that stimuli were simplified.

Put those two together and you have the whole case for a built-in control. The one cue people lean on, the badge, does not certify the content, and the cue they think they have, their own eye, performs at or below a coin toss. When the only signal is misleading and the human eye cannot close the gap, the burden cannot sit with the individual.

---

# What already works, just not on dating apps

## Pinterest, Meta, and TikTok label AI images at scale
- **Layer.** Disclosure and labeling
- **Established construct.** Best-effort labeling at scale, metadata first with a classifier fallback and a human appeal, rather than perfect detection.
- **What AI touches.** The whole pipeline exists to surface AI-generated and AI-modified media to the viewer.
- **What the research shows.** Pinterest labels generative-AI content "AI modified," analyzing metadata and its own classifiers "even if the content doesn't have obvious markers," with an appeals process, rolled out globally in 2025 ([Pinterest, 2025](https://newsroom.pinterest.com/news/introducing-gen-ai-labels/)). Meta reads C2PA and IPTC metadata plus builds classifiers, while admitting "it's not yet possible to identify all AI-generated content" and that markers can be stripped ([Meta, 2024](https://about.fb.com/news/2024/02/labeling-ai-generated-images-on-facebook-instagram-and-threads/)). TikTok auto-labels AI content from other platforms by reading C2PA credentials ([TikTok, 2024](https://newsroom.tiktok.com/partnering-with-our-industry-to-advance-ai-transparency-and-literacy)). Dating apps are the gap: Bumble's own Partnership on AI case study positions the company as a "passive distributor" waiting on industry-wide C2PA adoption rather than building labeling itself ([PAI, 2024](https://partnershiponai.org/wp-content/uploads/2024/03/pai-synthetic-media-case-study-bumble.pdf)). The one recent move toward disclosure is Bumble's optional "AI-assisted" photo badge, reported as launching in March 2026 and described as voluntary ([Pose AI, 2026](https://pose.ai/blog/are-ai-photos-allowed-dating-apps-2026), primary confirmation from Bumble still pending). Counter-evidence: feasible is not the same as reliable, since these labels miss stripped-metadata content and Meta's early "Made with AI" tag wrongly flagged lightly edited real photos, forcing a rename ([TechCrunch, 2024](https://techcrunch.com/2024/07/01/meta-changes-its-label-from-made-with-ai-to-ai-info-to-indicate-use-of-ai-in-photos/)).
- **Why it belongs in the "works" column.** This is the existence proof. The exact pipeline the proposal asks for is deployed and running at three of the largest image platforms. The point is not that it is perfect. It is that dating apps have declined to adopt a tool the rest of the industry already ships.
- **Who the gap hits hardest.** Users of apps that decline to label, who get none of the signal other platforms now provide.
- Evidence: **Moderate to Strong**. Strong that labeling is feasible and deployed, Moderate on the dating-app gap since Bumble is starting to move and the badge is not yet confirmed from a primary source.

---

# The caveats that keep the fix honest

These are not reasons to skip the fix. They are the costs and limits a good version has to design around, kept here so the proposal is honest about what the controls cannot do.

## Content provenance travels but is strippable
- **Layer.** Provenance
- **Established construct.** C2PA content credentials attach a cryptographically signed, tamper-evident record of how a file was made and edited.
- **What AI touches.** Generators like the ones behind OpenAI's images can write a credential at creation, so provenance is possible in principle for cooperating tools.
- **What the research shows.** C2PA is explicit that credentials verify the integrity of provenance data, not the truth of the content, and that a manifest "can be separated" from the asset ([C2PA FAQ](https://c2pa.org/faqs/)). NIST notes metadata "often is removed when files are shared" and that many platforms strip it on upload ([NIST AI 100-4](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-4.pdf)). The World Privacy Forum adds that a forged image can still carry a valid signature, creating false confidence, and that embedded capture metadata can deanonymize a creator ([WPF, 2025](https://www.worldprivacyforum.org/2025/06/report-privacy-identity-and-trust-in-c2pa/)). Counter-evidence: durable credentials pair the manifest with a soft binding (a watermark or fingerprint) so provenance can be recovered from a cloud store, which is a real mitigation, though it inherits every watermark weakness below.
- **Threat mechanism.** A screenshot produces a fresh pixel array with no inherited metadata and no manifest, so the provenance simply does not travel. Short-lived dating chats are close to the worst case.
- **Who it hits hardest.** Anyone downstream of a re-upload or screenshot, which on a dating app is nearly everyone.
- Evidence: **Strong**. The standard body and an independent government body both document the stripping problem.

## Watermarks mark only cooperating models, and come off
- **Layer.** Provenance (watermarking)
- **Established construct.** An imperceptible watermark embedded at generation time can later flag content as synthetic.
- **What AI touches.** SynthID watermarks images, text, audio, and video from Google's own and participating models.
- **What the research shows.** SynthID survives routine edits like compression and color changes but DeepMind states it "isn't foolproof against extreme image manipulations" and only marks participating models' output ([DeepMind](https://deepmind.google/models/synthid/)). The text version is peer-reviewed and scales, with negligible quality loss over nearly 20 million Gemini responses, but the authors concede it is "weakened by edits to the text, such as through LLM paraphrasing" ([Dathathri et al., 2024, Nature](https://doi.org/10.1038/s41586-024-08025-4)). Two peer-reviewed results go further: invisible image watermarks are "provably removable" by a generative regeneration attack ([Zhao et al., 2024, NeurIPS](https://arxiv.org/abs/2306.01953)), and there is a fundamental evasion-versus-spoofing trade-off, where watermarks can both be removed and be forged onto real images to frame a human ([Saberi et al., 2024](https://arxiv.org/abs/2310.00076)). NIST notes that anyone with model access "can modify that source code to disable watermarking" ([NIST AI 100-4](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-4.pdf)). Counter-evidence: high-perturbation watermarks that alter content more deeply resist removal better, at the cost of being less invisible.
- **Threat mechanism.** A bad actor using a self-hosted open-source generator produces content with no watermark to strip. Both halves of the chain have to hold (the generator cooperates and the mark survives), and against a motivated adversary neither reliably does.
- **Who it hits hardest.** Targets of anyone who chooses an uncooperative generator, which is exactly the scam threat model.
- Evidence: **Strong** for removability and the cooperating-model limit, with formal proofs plus independent corroboration.

## Automated image detectors are unreliable both ways
- **Layer.** Detection (automated)
- **Established construct.** Post-hoc classifiers try to separate generated from camera images, and inherit a robustness-versus-reliability trade-off.
- **What AI touches.** The detectors are themselves models, and they degrade as generators improve and as images are compressed and filtered.
- **What the research shows.** Testing five leading AI-image detectors on 45 images, one flagged 13.3 percent of authentic images as AI-generated, with the worst tool wrongly flagging 40 percent of real images, and detection of heavily altered images ranging down to 33 percent ([NewsGuard, 2026](https://www.newsguardtech.com/special-reports/leading-ai-image-detection-tools-mislead-online-users-often-declaring-authentic-content-fake/)). OpenAI shut down its own AI-text classifier in 2023 because it caught only 26 percent of AI text while mislabeling human text 9 percent of the time ([OpenAI, 2023](https://openai.com/index/new-ai-classifier-for-indicating-ai-written-text/)). Even an industry vendor selling AI dating photos concedes that "real photos get flagged as fake and polished fakes slip through," which is why no app relies on a single classifier ([fotto.ai, 2026](https://fotto.ai/blog/can-tinder-detect-ai-photos)). A UK government-commissioned market study found detection accuracy typically drops 10 to 20 percent when tools move from lab datasets to real-world content, that inconsistent metrics let providers claim high accuracy without independent validation, and cited an iProov study reporting only 0.1 percent of people could reliably identify deepfakes ([DSIT and PUBLIC, 2026](https://www.gov.uk/government/publications/deepfake-detection-technology)). Counter-evidence: in the same NewsGuard test some tools had zero false positives, so quality varies widely, and metadata-based checks are more reliable than pixel classifiers when a credential is present.
- **Threat mechanism.** A false positive brands a real person's genuine photo as fake, which is uniquely damaging on a dating app. A false negative lets a polished fake through. The failure lands in both directions.
- **Why it stays a support, not the answer.** Every serious deployment pairs the classifier with a human appeal process, precisely because the classifier is wrong sometimes.
- **Who it hits hardest.** Real users wrongly flagged, especially anyone whose genuine photos happen to look "too perfect."
- Evidence: **Moderate**. Strong on the direction, but the sharpest numbers come from a single small test.

## Partial or "AI" labeling can backfire
- **Layer.** Disclosure and labeling
- **Established construct.** The implied-truth effect. Labeling some false content can raise trust in the false content that goes unlabeled, because the missing label reads as a stamp of approval.
- **What AI touches.** The label itself is the intervention, and its wording and coverage change how people read both flagged and unflagged content.
- **What the research shows.** In a study of over 5,000 people, warning only on the fakes that get caught made people trust the uncaught fakes more ([Pennycook et al., 2020](https://doi.org/10.1287/mnsc.2019.3478)). Blunt "AI-generated" labels also lower perceived accuracy for true and human-made content, not only fakes, by about a fifth of a point on a six-point scale ([Altay and Gilardi, 2024, PNAS Nexus](https://doi.org/10.1093/pnasnexus/pgae403)). Counter-evidence, and it is real: a meta-analysis finds that on balance labels do reduce belief in and sharing of false content, so the effect is modest and conditional rather than a reason not to label ([Martel and Rand, 2024, Nature Human Behaviour](https://doi.org/10.1038/s41562-024-01973-x)).
- **Threat mechanism.** A person who writes in a clean, listy style gets read as a bot and penalized, while a careful fabricator who edits for voice slips past. This is why the proposal favors specific, appealable labels ("AI-modified," with a path to contest) over a scarlet-letter "AI" stamp.
- **Who it hits hardest.** Honest AI-assisted users who eat the trust penalty, and anyone who trusts an unlabeled fake because everything else on the page was clean.
- Evidence: **Moderate**. Well-replicated effects in both directions, with the honest note that the net balance still favors labeling.

## Detection and provenance lose to a motivated adversary
- **Layer.** All
- **Established construct.** The pattern underneath every row above. Each control is strong against lazy deception and weak against careful deception.
- **What AI touches.** The whole toolchain. Verification, detection, watermarking, and provenance each have a documented failure mode that a determined actor can reach.
- **What the research shows.** Verification stops static stolen photos but not a matching live face over fabricated context. Detection catches sloppy renders but not clean ones. Watermarks mark cooperating generators but not self-hosted ones, and come off. Provenance is a two-link chain (the generator has to cooperate and the mark has to survive to the viewer) and on adversarial dating content neither link holds. The supply side says it plainly: "detection technology is strong against deception and weak against honesty" ([fotto.ai, 2026](https://fotto.ai/blog/can-tinder-detect-ai-photos)).
- **Threat mechanism.** The honest AI user (a shy person polishing a real bio) is the easiest to flag, and the motivated bad actor is the hardest, which is the exact inverse of what you want.
- **Why it does not sink the proposal.** Labeling is a way to disclose good-faith AI at scale and raise the cost of casual deception, not a defense against a funded scam operation. Selling it as the second thing is how it fails. Layered controls plus provenance-at-generation (see [policy.md](policy.md)) are the only thing that touches the determined adversary.
- **Who it hits hardest.** The targets of anyone willing to spend effort, which is the scam threat model.
- Evidence: **Moderate**. The direction is well documented across the rows above, drawn from the same sources.

## Biometric verification has its own privacy and exclusion cost
- **Layer.** Identity verification
- **Established construct.** Verification mandates trade one risk for another. Biometric data is sensitive and permanent, and ID requirements exclude people who lack documents.
- **What AI touches.** Face-scan verification and facial age estimation are themselves AI systems, trained and retained, and dating apps are folding those face maps into their models.
- **What the research shows.** Hinge's face data practices carry an internal tension worth naming: one page says facial geometry templates are "deleted within 24 hours" while the Face Check page says "FaceMaps and FaceVectors are retained for the lifetime of an account," an ambiguity flagged by [Digital Rights Watch (2026)](https://digitalrightswatch.org.au/2026/05/13/too-much-information-dating-apps-and-ai/). On exclusion, roughly 15 million US adults lack a driver's license and 2.6 million have no government photo ID, 43 percent of transgender Americans lack ID reflecting their name or gender, and age-and-identity estimation is less accurate for Black, Asian, and Indigenous faces ([EFF, 2025](https://www.eff.org/deeplinks/2025/12/10-not-so-hidden-dangers-age-verification)). Counter-evidence: privacy-preserving designs exist, including on-device estimation that does not transmit the ID, so the harm is a function of implementation, not of verification as such.
- **Threat mechanism.** A compromised faceprint cannot be reset like a password, and retained biometrics plus intimate profile data concentrate risk under one company. Match Group controls a large share of the market ([Digital Rights Watch, 2026](https://digitalrightswatch.org.au/2026/05/13/too-much-information-dating-apps-and-ai/)).
- **Who it hits hardest.** People without conventional ID, trans and nonbinary users, and users with darker skin who face higher misclassification.
- Evidence: **Strong** for the exclusion and demographic-bias figures. **Moderate** for the retention-ambiguity claim, which rests on comparing two of Hinge's own pages.

---

# Text provenance, the weakest case, and what exists today

Text is deliberately outside this repo's demand. The ask is scoped to images, video, and voice, the content you judge someone on before you meet them, and text is named as a future direction rather than the present request. It sits here because the reason is a finding in its own right: text provenance is genuinely behind the other media, and it helps to be precise about what does and does not exist today rather than listing it as a flat gap.

What exists today is thin but not nothing. Long generated text, a full bio for instance, can carry a statistical watermark like SynthID-Text that survives if the passage is long and largely unedited, and the method is peer-reviewed and deployed at scale ([Dathathri et al., 2024, Nature](https://doi.org/10.1038/s41586-024-08025-4)). What does not exist is anything that works on the part of dating that matters most. Text watermarks degrade under paraphrase, "substantially" for short texts and only slightly for long ones ([NIST AI 100-4](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-4.pdf)), and Barkallah and Zytko note that C2PA-style credentials are "a poor fit for the short-lived, cross-app text chats that shape impressions in online dating" ([CHI, 2026](https://doi.org/10.1145/3772318.3791593)). A dating opener is short, is pasted across apps, and carries no durable metadata, so there is nothing to mark and nothing to read. The bio is a slightly easier case than the message thread, and neither is solved. That is why the demand starts with images, video, and voice, where the tooling actually reaches.

The deception side of AI in profile text, chatfishing and fabricated personalities, is mapped in [landscape.md](landscape.md). The evidence there is strong that it is happening. The provenance tooling to label it is what is missing.

---

# Cross-cutting honest limits

Beyond the per-control caveats, three limits run through the whole repo and are worth stating on their own.

The largest is causal. The romance-scam loss figures are real and large (the US FTC reported 1.14 billion dollars in 2023, and UK bank data put the average romance-scam loss at 7,000 pounds in 2025), but almost none of these numbers separate AI-driven harm from ordinary catfishing that predates AI ([FTC, 2024](https://www.ftc.gov/business-guidance/blog/2024/02/love-stinks-when-scammer-involved), [Barclays, 2026](https://home.barclays/news/press-releases/20260/02/ai-deepfake-concerns-see-gen-z--swiping-left--on-dating-apps/)). The FBI confirms criminals use generative AI in romance and confidence fraud but gives no prevalence or dollar attribution ([FBI IC3, 2024](https://www.ic3.gov/PSA/2024/PSA241203)). So "AI is making this worse" is directionally supported and not quantified, and I will not pretend otherwise. Two things the dollar figures still miss. The harm is not only financial, since survivors of romance fraud report PTSD, depression, and suicidal ideation, and the shame around it suppresses reporting so official totals understate the true scale ([UNSW, 2026](https://www.unsw.edu.au/newsroom/news/2026/02/valentines-day-is-coming--how-vulnerable-are-you-to-ai-enabled-rom)). And the mechanism has genuinely shifted, because agentic AI lets one operator run many personalized, long-term deceptions at once rather than grooming victims by hand, with concrete cases like a Hong Kong deepfake romance ring that took victims for 46 million dollars ([UNSW, 2026](https://www.unsw.edu.au/newsroom/news/2026/02/valentines-day-is-coming--how-vulnerable-are-you-to-ai-enabled-rom), [NCOA, 2026](https://www.ncoa.org/article/understanding-deepfakes-what-older-adults-need-to-know/)). That sharpens the worry without closing the quantification gap.

The second limit is that a threat-only version of this repo would have to drop the real upside. AI genuinely helps neurodivergent, disabled, and non-native-speaker daters express themselves, and a heavy-handed labeling regime would penalize them first. The privacy cost of verification is real and lands on marginalized users. And the moral panic about technology ruining dating is very old, which is worth remembering before treating this moment as unique ([Harvard Gazette, 2025](https://news.harvard.edu/gazette/story/2025/02/tech-has-changed-dating-its-complicated/)).

The third is demand without supply. Users want this. In a UK survey, 30 percent wanted clear labels and warnings about AI-generated content, 84 percent wanted platforms to do more, and Gen Z is partly retreating to in-person dating over exactly these fears ([Barclays, 2026](https://home.barclays/news/press-releases/20260/02/ai-deepfake-concerns-see-gen-z--swiping-left--on-dating-apps/)). The tooling exists at other platforms. The dating apps have mostly not connected the two.

Full source list with grades is in [SOURCES.md](SOURCES.md). Open questions are in [open-questions.md](open-questions.md).
