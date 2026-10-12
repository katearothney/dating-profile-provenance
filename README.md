# Dating Profile Provenance

*Verified, not authentic.*

> **Key finding:** a dating app's "verified" check confirms a live person, not that their photos are real. In one study, people spotted AI-generated profile photos only 42.8% of the time, below chance (Ivan, 2025).
>
> **What you'll get:** a graded grid of what exists to mark, detect and label AI images, video and voice on profiles, a proposal for what apps should do, and the counter-evidence on labels backfiring. No law currently requires dating apps to label AI photos.

I keep coming back to one question: should dating apps show where a profile's photos and words actually came from, the way Pinterest labels AI images, even when no law makes them?

This started with a real profile (the full story is in [why.md](why.md)). A man liked me on Hinge. His profile had the purple "verified" check. His photos were a jumble of AI-generated lifestyle shots (a man in a black overcoat in falling snow, a man fishing by a lake with the background quietly warping the way AI images do) and hockey photos of a Montreal Canadiens player, where the face barely held steady from one image to the next. The check told me a real person was behind the account. It told me nothing about whether the photos were real. Those turn out to be two completely different questions, and almost nobody using these apps knows that.

This is me working that out in public. I read the research, I try to be straight about what it does and doesn't show, and mostly I care about the practical side: what would actually make these spaces safer, and what would just look like it.

The stakes are not abstract. Unlabeled synthetic content lands hardest on the people already most exposed on these platforms, which is women, older adults, and marginalized users. That is the reason I care about the boring infrastructure question of provenance.

## What this repo is scoped to

This repo is specifically about content provenance for **images, video, and voice or audio**, the content you judge someone on before you ever meet them. Those are the highest-stakes first-impression signals and the ones current provenance and detection tools can actually mark. Text is the harder case, so I treat bios and messages as context and a future direction rather than the present demand. The broad risks of AI in dating (AI matchmaking, AI companions, engagement-driven design, privacy) are mapped in [landscape.md](landscape.md) for context, but the ask this repo makes is narrow and buildable: make it visible when a photo, a video, or a voice on a profile was made or altered by AI. The proposal and the full list of demands are in [PROPOSAL.md](PROPOSAL.md).

## The frame

I did not invent a taxonomy for this. I crossed two existing ones.

The rows are the three things a dating profile puts in front of you, a split that comes straight from two decades of online-dating self-presentation research. That work separates the person (identity and appearance), the images (visual self-presentation), and the words (bios and messages, or verbal self-presentation). Toma and Hancock's "Looks and Lies" treats visual and textual deception as distinct problems ([Communication Research, 2010](https://doi.org/10.1177/0093650209356437)), Ellison, Heino and Gibbs set up profiles as managed self-presentation ([JCMC, 2006](https://doi.org/10.1111/j.1083-6101.2006.00020.x)), and Ivan's 2025 study notes that prior work focused on textual deception while synthetic images are the newer gap ([Computers in Human Behavior: Artificial Humans, 2025](https://doi.org/10.1016/j.chbah.2025.100208)).

The columns are the intervention layers from NIST's report on reducing the risks of synthetic content, which organizes the field into provenance tracking (metadata and watermarking), automated detection, and human-facing measures like labeling and disclosure ([NIST AI 100-4, 2024](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-4.pdf)). I add identity verification as the fourth column because it is the control the apps already ship, and it is the one my Hinge match had passed.

Crossing self-presentation channels with intervention layers is my modeling choice, not a law of nature. Some items sit in more than one cell, and where I put them is a judgment call. The point of the grid is not tidiness. It is to show where the coverage is and, more usefully, where it is missing.

### At a glance

Each cell is the current state of play. Empty and weak cells are the finding, not a gap I am hiding.

| | Provenance and watermarking | Automated detection | Disclosure and labeling | Identity verification |
|---|---|---|---|---|
| **The person** | not designed for this | duplicate-face checks exist | "verified" badge | this is where the apps invest |
| **The images (photos)** | C2PA exists, apps do not use it | unreliable, both directions | Pinterest and Meta do this, dating apps do not | badge only confirms a live face, not the photo |
| **The words (bios, messages)** | nearly empty, text is the worst case | weak on short chat text | almost nonexistent | not applicable |

The full graded version is in [matrix.md](matrix.md). The things nobody has actually measured yet are in [open-questions.md](open-questions.md).

## What the evidence actually says

The short version, with everything graded and linked in the matrix:

The purple check verifies a live human whose face matches the uploaded photos. It does not verify that the photos are real, recent, un-stolen, or not AI-generated. Hinge and Tinder say this themselves in their own help pages. So a person can pass verification with a face that is genuinely theirs and a set of photos that are entirely fabricated, which is close to what I saw.

People cannot tell AI faces from real ones. In a study of 831 online daters, detection of AI-generated profile photos ran at 42.8 percent, below chance, while real photos were called correctly 82.7 percent of the time ([Ivan, 2025](https://doi.org/10.1016/j.chbah.2025.100208)). A separate PNAS study found people classified synthetic faces at 48.2 percent, below chance, and rated them as slightly more trustworthy than real faces ([Nightingale and Farid, 2022](https://doi.org/10.1073/pnas.2120481119)).

Provenance labeling is not science fiction, because Pinterest, Meta, and TikTok already do it at scale. They use a metadata-first, classifier-fallback, human-appeal approach that they openly admit is imperfect. Dating apps have not adopted it. Bumble's own case study with the Partnership on AI positions the company as a "passive distributor" that is waiting on industry-wide provenance standards rather than building the labeling itself ([PAI, 2024](https://partnershiponai.org/wp-content/uploads/2024/03/pai-synthetic-media-case-study-bumble.pdf)).

No law currently requires a dating app to label AI profile photos. The EU AI Act's Article 50 (applying from 2 August 2026) and California's SB 942 (operative 2 August 2026) both push the marking duty onto the makers of the AI, not the platforms that host it. So "are they technically required" has a real answer, and the answer today is no.

And labeling can backfire. Warning only the fakes you catch can make people trust the fakes you miss more, an effect measured in a study of over 5,000 people ([Pennycook et al., 2020](https://doi.org/10.1287/mnsc.2019.3478)). Labels reading "AI-generated" also lower trust in true and human-made content, not just fakes ([Altay and Gilardi, 2024](https://doi.org/10.1093/pnasnexus/pgae403)). I keep this counter-evidence in on purpose, because it is the strongest argument against the thing I am inclined to want.

## What's in here

- [why.md](why.md) is the entry point: why I started this, why it's a problem, the gaps, and what needs to happen. Start here.
- [ARGUMENT.md](ARGUMENT.md) is the through-line written out: the claim, the risks, the solutions, and where the field agrees, argues, and does not know.
- [PROPOSAL.md](PROPOSAL.md) is the ask: a full list of demands to dating apps, led by "label AI content, like Pinterest."
- [protect-yourself.md](protect-yourself.md) is how to use the tech you have today while the apps catch up.
- [matrix.md](matrix.md) is the spine: every risk graded, by channel and intervention layer.
- [landscape.md](landscape.md) maps all the ways AI shows up in dating, the good and the risky (context for the scoped ask).
- [theories.md](theories.md) is the set of established ideas I reason with, each cited.
- [solutions.md](solutions.md) walks the possible fixes and existing technologies, with the tradeoff attached to each.
- [policy.md](policy.md) covers what the law does and does not require, and the options.
- [open-questions.md](open-questions.md) is the gaps, the things nobody has measured yet.
- [SOURCES.md](SOURCES.md) is the graded source registry.

## Being honest about the evidence

The science here is real but young, and a lot of it is messy. So I grade the evidence behind every claim, I keep in the studies that argue against my own worry, and I name the things nobody has studied yet.

- **Strong.** More than one study, at least one a proper randomized experiment, and it held up when others tried it.
- **Moderate.** Consistent across a few studies, but mostly surveys or single experiments. No direct contradiction yet.
- **Mixed.** Real studies pointing different ways, or an effect that shows up in some settings and not others.
- **Emerging.** One study, a preprint, or a claim that's reasoned rather than measured. Interesting, not settled.
- **Contested.** Widely repeated, but the evidence is weak or failed to replicate. I'll say so.
- **Open question.** Something I keep wondering about that nobody seems to have studied yet. Named on purpose rather than dressed up with a weak citation.

The biggest honest limit runs through the whole repo: the money-loss numbers are real, but almost none of them separate AI-driven harm from ordinary catfishing that predates AI. I flag that everywhere it matters, and it is the first open question.

## Contributing

Want to add a study I missed, poke holes in a grade, or bring evidence that cuts against me? That is the most useful thing you can do here. See [CONTRIBUTING.md](CONTRIBUTING.md).

Shared under CC BY 4.0. All of this is my own opinion and does not represent my employer.

## Scope and caveats

I'm not a trust and safety engineer or a lawyer. I read the research and try to be straight about what it does and doesn't show.
