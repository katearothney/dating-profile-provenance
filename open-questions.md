# Open questions and gaps

The empty cells in the matrix are a finding, not something to hide. These are the things I keep wondering about that nobody seems to have measured yet, or where the evidence runs out. Each one is a place this repo can grow. If you can fill one, see [CONTRIBUTING.md](CONTRIBUTING.md).

I grade these the same way as everything else. Most are **Open question** by definition. A few are **Emerging** because there is a first stab at an answer.

## The base rate nobody has
- **What share of dating-app profiles actually use AI-generated photos?** Match Group's vendor put it near 0.6 percent of a sample, but that is unaudited and self-reported, and it counts "concerning manipulation" rather than all AI. No independent number exists. Everything downstream (how big is this problem, really) depends on a figure nobody has published. **Open question.**
- **What share of opening messages and bios are AI-written?** One paid press release claims one in four singles use AI in dating communication, and a survey found roughly 60 percent suspect they have received AI messages, but the first is a marketing figure and the second is perception, not measurement. **Emerging, weak.**

## The causal gap
- **Does AI actually increase harm, or just change its texture?** Romance-scam losses are large and real, but no FTC or FBI dataset attributes dollars or victims specifically to AI. Romance fraud predates AI by decades. The honest state is that AI plausibly lowers the cost and raises the polish of deception, and that this is not yet quantified. **Open question.** This is the single most important gap in the whole repo. The clearest concrete evidence that AI personas run at scale is a February 2025 raid on a scam hub in Makati City that found a real-time face-swap operation running thousands of synthetic dating profiles and ended in 169 arrests ([GMA via Vaarhaft, 2025](https://www.vaarhaft.com/blog/how-dating-apps-detect-ai-generated-profile-pictures-and-crush-romance-scams)). That shows the mechanism is real and industrialized, but it still does not measure the incremental harm over pre-AI catfishing. On the demand side, a UK survey found 19 percent of singles say they have already been duped by a deepfake and 81 percent think dating apps are not doing enough to filter manipulated images ([Sumsub, 2025](https://sumsub.com/newsroom/one-in-five-single-brits-have-already-been-duped-by-deepfakes-on-dating-apps/)).
- **Is an AI-generated profile more harmful than old-fashioned catfishing with stolen photos?** Stolen real photos can be reverse-image searched. AI photos cannot, because the person does not exist (the Katie Jones espionage case is the clean early example). So AI may specifically defeat the one detection habit that worked. Plausible, unmeasured. **Emerging.**

## Whether the fix would even work
- **Would provenance labeling on a dating app reduce harm, or just move it?** Every labeling study I have is from news and social media, not dating. The implied-truth and AI-label-distrust effects might be worse in a high-stakes, one-on-one, romantic context, or might not apply at all. Untested in this setting. **Open question.**
- **Does a "verified" badge create false confidence that makes people less careful?** The badge verifies a live face, but if users read it as "these photos are real," the badge could lower vigilance exactly where it should not. I have not found a study measuring how the badge changes user trust behavior. **Open question.**
- **Who does a false "AI-generated" flag hurt, and how badly?** Detectors wrongly flag real photos, and on a dating app a false flag on a real person's genuine photo is a reputational harm with no news-media equivalent. Nobody has studied the cost of that specific error here. **Open question.**

## The channel we understand least
- **Text is the hard case and the understudied one.** Provenance and watermarking were built for persistent images. The highest-stakes early signal on a dating app is a short chat message, which carries no durable metadata and defeats text watermarks. What does provenance even mean for a one-line opener pasted across three apps? **Open question.**
- **Where is the line between honest AI help and deception?** A shy or non-native-speaker dater polishing a real bio is different from someone fabricating a personality, but both may read the same to a detector and to a partner. The consent research raises this and does not resolve it. Users are already arguing it in exactly these terms: a widely-shared TikTok asked whether AI photos are "the same as women using filters, which also isn't right," then the harder collective question, "should we all be using AI to generate our dating profile?" ([doctor.nicolej, 2025](https://www.tiktok.com/@doctor.nicolej/video/7584881526970551574)). That second question is the arms-race version. If everyone has to use AI to compete, the honest non-user is the one penalized, and "authentic" quietly stops being an option. **Open question.**

## The tradeoffs I do not know how to weigh
- **Does mandatory verification make marginalized users safer or more exposed?** It can keep banned abusers out, and it can lock out people without ID, out trans users, and concentrate biometric data. I do not have a way to net these against each other, and I am not sure one exists. **Open question.**
- **Could provenance become a gatekeeping system rather than a safety one?** The strongest critique of my own position is that provenance plus identity plus ranking can quietly become a permission layer that decides who is visible, which would hit anonymous and marginalized creators first. This is argued, not measured, but it is the risk I take most seriously. **Emerging.**

## Things I have not researched yet (honest to-do)
- Non-US and non-Western dating contexts, where the CHI survey had large African and Global South representation but most other evidence is US or UK.
- AI romantic companions and chatbots (Grindr's AI wingman, Replika-style partners) as a distinct problem from AI-assisted human profiles.
- Whether any dating app has published real numbers on AI-content removal, rather than a vendor summary.
- The economics: does the business model (engagement, return visits) actively work against labeling that would reduce matches?
