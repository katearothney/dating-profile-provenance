# Potential solutions

Ways to close the gap, each with what it is, what it can do, where it breaks, and how strong the evidence is. I try not to fall in love with any of them. The honest pattern is that no single one works, and the good ones are the ones that fail gracefully. This is a living list.

I grade the solution by how well-supported it is that the approach helps, not by how much I like it.

## Surface content provenance (make apps read C2PA)
- **What.** Dating apps read C2PA content credentials on uploaded photos and show the viewer where an image came from, the way TikTok already does.
- **Upside.** The standard exists, other platforms use it, and a UN Women policy expert explicitly recommends mandating C2PA-style credentials so platforms can "detect origin and manipulation" ([UN Women, 2025](https://www.unwomen.org/en/articles/faqs/ai-powered-online-abuse-how-ai-is-amplifying-violence-against-women-and-what-can-stop-it)).
- **Where it breaks.** Credentials are opt-in on the generator side and strippable by a screenshot or re-upload ([C2PA FAQ](https://c2pa.org/faqs/)). It labels good-faith AI, not a determined scammer's.
- Evidence the approach helps: **Moderate.** Real and deployed elsewhere, but partial by design.

## Label AI content the way Pinterest does
- **What.** Metadata first, a classifier as fallback, and a human appeals path, producing an "AI modified" style label.
- **Upside.** Proven at scale at Pinterest, Meta, and TikTok. Feasible today.
- **Where it breaks.** Classifiers wrongly flag real photos, which on a dating app is a reputational harm ([NewsGuard, 2026](https://www.newsguardtech.com/special-reports/leading-ai-image-detection-tools-mislead-online-users-often-declaring-authentic-content-fake/)), and partial labeling can raise trust in the fakes that slip through ([Pennycook et al., 2020](https://doi.org/10.1287/mnsc.2019.3478)).
- Evidence: **Moderate.** Feasibility is Strong, net benefit in a dating context is untested.

## Voluntary disclosure badges
- **What.** An optional "AI-assisted" tag a user can add, which Bumble reportedly launched in March 2026 ([Pose AI, 2026](https://pose.ai/blog/are-ai-photos-allowed-dating-apps-2026)).
- **Upside.** Low friction, no false accusations, gives honest users a clean way to be upfront.
- **Where it breaks.** Voluntary means the people most worth flagging will not use it, and a sea of "honest" badges can make the unbadged fakes look more trustworthy. This is the implied-truth problem wearing a friendly face.
- Evidence: **Emerging.** New, and the badge itself is only vendor-reported so far.

## Behavioral and network detection
- **What.** Score message timing, phrasing, link-sharing, and account graphs to catch coordinated scams, rather than judging pixels. Bumble's "Deception Detector" reportedly blocked 95 percent of accounts it identified as spam or scams ([GeekWire, 2026](https://www.geekwire.com/2026/ai-enters-the-chat-new-seattle-dating-app-relies-on-tech-to-facilitate-meaningful-human-connections/)), and vendors sell layered forensic-plus-liveness-plus-behavioral stacks ([Vaarhaft, 2025](https://www.vaarhaft.com/blog/image-id-or-behavior-what-stops-romance-scams-on-dating-apps)).
- **Upside.** Catches scam operations that photo forensics miss, and does not depend on detecting the image at all.
- **Where it breaks.** The 95 percent is self-reported and quietly conditional on what got "identified." It targets scams, not the honest-but-misleading AI profile.
- Evidence: **Moderate** on the concept, **Contested** on the specific numbers.

## Proof of humanity
- **What.** A cryptographic "this is a unique human" badge. Tinder is integrating World ID, from Sam Altman's World (formerly Worldcoin), which confirms humanness by iris scan, claims to store no name or address, and has verified 18 million people who have used it 450 million times. It is offered as an opt-in layer on top of Tinder's now-mandatory video selfie ([BBC, 2026](https://www.bbc.com/news/articles/cp9vppem4evo)).
- **Upside.** Raises the cost of bulk bot and fake-account creation, which is a real chunk of the problem (one user estimated 30 percent of profiles she saw were AI-enhanced scam accounts, and Deloitte projects deepfake-enabled fraud could reach 40 billion dollars in the US by 2027). Match Group's own trust-and-safety lead frames it as helping users "know the person on the other end is real."
- **Where it breaks.** It proves a unique human exists, not that their photos or words are real, so it is the same identity-versus-authenticity gap one layer up, just cryptographically stronger. It is also the platform-to-user model in its purest form (see the mutual-transparency section in [theories.md](theories.md)): a verdict handed down and attached to your name, which concentrates biometric data in a crypto-linked startup and carries real privacy and exclusion costs. Whether "anonymous" holds under a company that has rebranded three times is its own open question.
- Evidence: **Emerging.** New, and it solves bot-ness, not authenticity.

## Design the deception out
- **What.** Change the product so the vulnerable moment does not happen. Seattle's Lamu withholds photos until after an AI-mediated conversation, and Tinder's "Are You Sure?" blurs harassing messages before they are seen ([GeekWire, 2026](https://www.geekwire.com/2026/ai-enters-the-chat-new-seattle-dating-app-relies-on-tech-to-facilitate-meaningful-human-connections/)).
- **Upside.** Withholding photos moves the first impression off the image, which is a genuinely different answer to visual deception. Slowing the pace also counters the attachment-to-text problem psychologists describe in "chatfishing" ([Indian Express, 2026](https://indianexpress.com/article/lifestyle/feelings/ai-flirt-dating-apps-psychologist-warns-hidden-emotional-cost-chatfishing-10442867/)).
- **Where it breaks.** It hands more judgment to the algorithm, and it does not touch the text channel, where a fabricated personality still forms.
- Evidence: **Emerging.** Promising, unproven.

## User education and visual literacy
- **What.** Teach people the tells and the limits of the tells.
- **Upside.** Cheap, and better than nothing.
- **Where it breaks.** The learning loop means the tells go stale as fast as you teach them, and heightened suspicion made women in one study misclassify real people as fake ([Ivan, 2025](https://doi.org/10.1016/j.chbah.2025.100208)). Over-teaching skepticism has its own cost.
- Evidence: **Mixed.** Small and fragile effects.

## Regulate the generator, not just the app
- **What.** Require the tools that make AI content to mark it at the source, so a compliant image arrives already labeled. This is the direction of the EU AI Act and California's SB 942.
- **Upside.** Puts the duty where the marking is technically easiest, at generation, and UN Women argues this "makes it harder for perpetrators to plausibly deny origin" ([UN Women, 2025](https://www.unwomen.org/en/articles/faqs/ai-powered-online-abuse-how-ai-is-amplifying-violence-against-women-and-what-can-stop-it)).
- **Where it breaks.** Open-source and self-hosted generators ignore the rule, and the mark still gets stripped downstream. See [policy.md](policy.md) for the detail.
- Evidence: **Moderate.** The law is real, the coverage is partial.

## The honest synthesis
No single control holds. The practitioner consensus and my own read line up on the same shape: layer them. Microsoft's research points the same way, finding after testing 60 combinations of metadata, invisible watermarks, and cryptographic signatures against real-world stripping and tampering that layering the three survives better than any one alone, while warning that a sloppy detector invites a sociotechnical attack where altering a sliver of a real image gets the whole thing flagged as fake ([Fox and CyberGuy on Microsoft, 2026](https://www.foxnews.com/tech/inside-microsofts-ai-content-verification-plan)). Provenance and labeling handle good-faith AI at scale, behavioral detection catches coordinated scams, proof-of-humanity thins the bots, and design changes remove some of the vulnerable moments. Even stacked, none of this defeats a motivated adversary using a self-hosted generator, so the goal is harm reduction, not a solved problem. And every layer has to be weighed against its own cost, because a labeling and verification regime built carelessly lands hardest on exactly the marginalized users it was supposed to protect (see [open-questions.md](open-questions.md)).
