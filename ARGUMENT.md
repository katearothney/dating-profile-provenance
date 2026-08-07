# The argument

This is the through-line of the whole repo, written out as an argument rather than a matrix. It develops the claim, lays out the risks, walks the possible solutions, and then does the thing I think matters most: it separates what the evidence actually agrees on from what is still being argued and what nobody has measured. The full graded source list is in [SOURCES.md](SOURCES.md), and the cornerstones are gathered at the end here.

## The claim

A man liked me on Hinge. His profile carried the purple verified check, and his photos were a jumble of AI-generated lifestyle shots (a man in a black overcoat in falling snow, a man fishing by a lake with the background quietly warping the way AI images do) and hockey photos of a Montreal Canadiens player, a set where the face barely held steady from one image to the next.

The check told me a real person was behind the account. It told me nothing about whether the photos were real. Those are two different questions, and conflating them is the whole problem.

My argument is that dating apps should show where a profile's photos and words came from, the way Pinterest and Meta and TikTok already label AI images, even though no law currently requires it, because a verified badge that certifies a face but not the content it is attached to creates a false sense of safety, and that false sense lands hardest on the people already most exposed on these platforms.

## Why this is the right question

The sharpest version of the argument is not "AI is bad for dating." It is that identity verification and content authenticity are different problems, and the apps have solved the first while marketing it as if it solved the second.

A liveness check confirms that a live human took a selfie that matches the uploaded photos. Hinge and Tinder say this plainly in their own help pages, and both add that verification does not guarantee the identity or safety of a user. A cybersecurity playbook put it even more directly, that a verified badge proves liveness and adult ID but "does not prove definitively that the person you're talking to isn't a fraudster." So a person can pass verification with a face that is genuinely theirs and a set of photos that are entirely fabricated, which is close to exactly what I saw. An undercover reporter made the gap concrete by getting a scammer to produce, in seconds, an AI selfie holding a paper with her name and the date on it, defeating the "send a selfie to prove you're real" test.

That is the hinge of the argument. The badge answers "is a real person here who looks like these pictures." It does not answer "are these pictures real." Provenance is the missing layer.

## The risks

The risks stack up in a specific order, and each one is graded in the matrix.

The person. Verification checks the face, not the photos, and the biometric checks that do the verifying carry their own cost. Face scans concentrate permanent, unresettable biometric data (Hinge's own pages are internally inconsistent about whether face maps are deleted in 24 hours or kept for the life of the account), and mandatory ID excludes real people, including the roughly 15 million US adults without a driver's license and the 43 percent of trans Americans without ID that reflects their name or gender.

The images. People cannot tell AI faces from real ones. In a study of 831 online daters, detection of AI profile photos ran at 42.8 percent, below chance, while real photos were identified 82.7 percent of the time. A PNAS study found people classified synthetic faces at chance and rated them as slightly more trustworthy than real faces. The tools meant to help are not reliable either. A UK government-commissioned study found detection accuracy drops 10 to 20 percent moving from lab to real-world content and cited a finding that only 0.1 percent of people can reliably spot deepfakes, and reverse image search, the one habit that used to work, fails against fully synthetic faces because there is no original to find.

The words. This is the channel we understand least and the one where provenance is weakest, because a short chat message carries no durable metadata and defeats text watermarks. AI-written profile text reduces trust in the author when it is noticed, and it is used to fabricate whole personalities. The phenomenon has a name now, "chatfishing," and a real face: one woman described three weeks of thoughtful Hinge messages collapsing on the date into "knock, knock, is anyone home," the AI having secured a meeting the man could not sustain himself.

The harm. This is where the argument earns its stakes, and it is also where I am most careful. Romance-scam losses are large and real, but almost none of the headline dollar figures separate AI-driven harm from ordinary catfishing that predates AI, so "AI is making this worse" is directionally supported and not cleanly quantified. What has changed is the mechanism. A February 2025 raid on a Makati City scam hub found a real-time face-swap operation running thousands of synthetic dating profiles and ended in 169 arrests, and agentic AI now lets one operator run many personalized, long-term deceptions at once rather than grooming victims by hand, with concrete cases like a Hong Kong deepfake romance ring that took victims for 46 million dollars. The harm is also not only financial. Survivors report PTSD, depression, and suicidal ideation, and shame suppresses reporting so the official totals understate it.

Who it hits hardest. The harm is gendered and it concentrates on the vulnerable. UN Women documents AI-facilitated abuse as one of the fastest-growing forms of technology-facilitated gender-based violence, with the overwhelming majority of deepfake abuse targeting women. Monash researchers who interviewed perpetrators of sexualized deepfake abuse found it shared for status and peer approval, distributed on platforms including dating apps, with the harm minimized by the people causing it. Older adults lose the most per victim, and LGBTQ+ users face specific sextortion and outing risks. Women are also more skeptical going in, with one survey finding only 10 percent of women versus 20 percent of men believe AI dating apps lead to better relationships.

## The potential solutions

No single control holds, and the honest position is harm reduction, not a solved problem. Each of these is developed with its tradeoff in [solutions.md](solutions.md).

Surface content provenance. Have apps read C2PA content credentials and show viewers where a photo came from, the way TikTok already does. A UN Women policy expert explicitly recommends mandating this. The limit is that credentials are opt-in on the generator side and stripped by a screenshot.

Label AI content the way Pinterest does. Metadata first, a classifier as fallback, a human appeal. Proven at scale at Pinterest, Meta, and TikTok, which is the direct answer to "why can Pinterest do this but a dating app can't." The limit is false positives that brand a real person's genuine photo as fake, and the implied-truth risk that labeling only the AI you catch quietly certifies the AI you miss.

Behavioral and network detection. Score message timing, link-sharing, and account graphs to catch coordinated scams rather than judging pixels. Bumble's Deception Detector reportedly blocked a large share of spam and scam accounts. The limit is that it targets scams, not the honest-but-misleading AI profile, and the numbers are self-reported.

Proof of humanity. Tinder is integrating World ID iris scans. It raises the cost of bulk bots, but it proves a unique human exists, not that their photos or words are real, so it is the same identity-versus-authenticity gap one layer up, with added biometric-concentration risk.

Design the deception out. Withhold photos until after a conversation (as Lamu does), or slow the pace so people attach to a person rather than to polished text. Promising and unproven, and it does not touch the text channel.

Regulate the generator, not just the app. The EU AI Act and California's SB 942 push the marking duty onto the tools that make AI content, so a compliant image should arrive already marked. Open-source and self-hosted generators route around it.

The synthesis, which Microsoft's own research supports after testing 60 combinations of metadata, watermarks, and cryptographic signatures, is that layering these survives real-world stripping better than any one alone, and that precision matters, because a sloppy detector invites an attack where altering a sliver of a real image gets the whole thing flagged as fake.

## Where the field agrees, argues, and does not know

This is the part I think is most useful for building a credible argument, because it shows I know the difference between a settled point and a live one.

Where there is broad support (I can lean on these):
- Humans cannot reliably detect AI faces, and the tools are unreliable too. This is consistent across the Ivan dating study, the Nightingale and Farid PNAS study, the NewsGuard tool test, and the UK government market study. Strong.
- Provenance and watermarks are fragile and strippable, and detection alone cannot be ground truth. C2PA says so itself, NIST says so, and the peer-reviewed watermark-removal results say so. Strong.
- Labeling AI content at scale is feasible today, because Pinterest, Meta, and TikTok do it, imperfectly, right now. Strong on feasibility.
- No current law requires a dating app to label AI profile photos, and the transparency duties that exist fall on the generators, not the hosting platform. Strong on the legal facts.
- The harm is real and gendered, and it lands hardest on women, older adults, and marginalized users. Strong on direction, from UN Women, Monash, FTC and FBI data, and Pew.

Where the field is actively arguing (I have to hold these as debates, not settle them):
- Does labeling help or backfire? The implied-truth effect and the "AI label lowers trust in true content" studies say partial labeling can hurt, while a strong meta-analysis says labels net-work even for skeptics. The honest read is that labeling is modest, conditional, and easy to get wrong, not that it fails or that it saves us.
- Is verification safety or surveillance? The same tools read as consent infrastructure when people opt into them and offer them to each other, and as a gatekeeping "permission system" when a platform makes them mandatory and ranks on them. This is the mutual-transparency argument in [theories.md](theories.md), and it is genuinely unsettled.
- Mandatory versus voluntary disclosure. Bumble's optional AI badge is the low-friction path, but voluntary means the people most worth flagging will not use it.

Where nobody has the answer yet (I name these on purpose):
- What share of dating profiles actually use AI photos or AI text. The one vendor figure is unaudited.
- Whether AI increases harm or just changes its texture, because no dataset attributes losses specifically to AI.
- Whether provenance labeling on a dating app would reduce harm or just move it, since every labeling study is from news and social media, not dating.

These are in [open-questions.md](open-questions.md), and naming them is part of the argument, not a weakness in it.

## The honest bottom line

My argument is not that provenance labeling fixes dating. It is that the current signal is actively misleading, because a badge that verifies a face while saying nothing about the content trains people to trust exactly what they should question, and that the tooling to do better exists and is deployed elsewhere. I hold two counter-arguments in view the whole way through. Labeling can backfire if it is partial or blunt, and verification can curdle into surveillance if it is mandatory and ranked. The version I actually believe in is narrow: voluntary, mutual, honestly-designed transparency that people offer each other, aimed at informing consent rather than policing it.

## Sources

The robust, graded source list is in [SOURCES.md](SOURCES.md), with every claim cited, graded, and linked, grouped by topic, and flagged where a link is vendor-sourced or still needs a primary confirmation. The cornerstones, one per load-bearing claim:

- Verification certifies a face, not the photos: [Hinge Help](https://help.hinge.co/hc/en-us/articles/10303221435539-What-is-Selfie-Verification), [Tinder Help](https://www.help.tinder.com/hc/en-us/articles/4422771431309-How-Does-Photo-Verification-Work), [ESET, 2026](https://www.eset.com/blog/en/home-topics/privacy-and-identity-protection/staying-safe-on-dating-apps/), [WBAL, 2026](https://www.wbaltv.com/article/ai-romance-scams-deepfake/70315255).
- Humans cannot detect AI faces: [Ivan, 2025](https://doi.org/10.1016/j.chbah.2025.100208), [Nightingale and Farid, 2022](https://doi.org/10.1073/pnas.2120481119).
- Detection and provenance are unreliable or strippable: [NewsGuard, 2026](https://www.newsguardtech.com/special-reports/leading-ai-image-detection-tools-mislead-online-users-often-declaring-authentic-content-fake/), [DSIT and PUBLIC, 2026](https://www.gov.uk/government/publications/deepfake-detection-technology), [C2PA FAQ](https://c2pa.org/faqs/), [NIST AI 100-4](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-4.pdf), [Zhao et al., 2024](https://arxiv.org/abs/2306.01953).
- Labeling is feasible at scale: [Pinterest, 2025](https://newsroom.pinterest.com/news/introducing-gen-ai-labels/), [Meta, 2024](https://about.fb.com/news/2024/02/labeling-ai-generated-images-on-facebook-instagram-and-threads/), [TikTok, 2024](https://newsroom.tiktok.com/partnering-with-our-industry-to-advance-ai-transparency-and-literacy).
- Dating apps have not adopted it: [Partnership on AI, 2024](https://partnershiponai.org/wp-content/uploads/2024/03/pai-synthetic-media-case-study-bumble.pdf).
- Consent framing: [Barkallah and Zytko, 2026](https://doi.org/10.1145/3772318.3791593).
- Labeling can backfire: [Pennycook et al., 2020](https://doi.org/10.1287/mnsc.2019.3478), [Altay and Gilardi, 2024](https://doi.org/10.1093/pnasnexus/pgae403), countered by [Martel and Rand, 2024](https://doi.org/10.1038/s41562-024-01973-x).
- The law: [EU AI Act Art 50](https://eur-lex.europa.eu/eli/reg/2024/1689/oj), [California SB 942](https://www.morganlewis.com/pubs/2026/08/new-california-ai-disclosure-rules-become-operative), [TAKE IT DOWN Act](https://www.ftc.gov/business-guidance/blog/2026/05/take-it-down-act-enforcement-starts-now-what-know-about-ftc-tida).
- Gendered harm: [UN Women, 2025](https://www.unwomen.org/en/articles/faqs/ai-powered-online-abuse-how-ai-is-amplifying-violence-against-women-and-what-can-stop-it), [Monash, 2025](https://lens.monash.edu/inside-the-minds-of-deepfake-abusers-what-drives-ai-fuelled-sexual-abuse/).
- Provenance as gatekeeping (the counter I take seriously): [Popular AI, 2026](https://www.popularai.org/p/ai-provenance-creator-permission-system).
