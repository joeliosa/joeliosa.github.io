---
layout: post
title: "Scales of Alignment"
date: 2026-07-06
image: /assets/cohesionthumbnail.jpeg
---

---
layout: post
title: "Scales of Alignment"
subtitle: "To build trustworthy AI, we must first figure out how to trust ourselves."
date: 2026-07-05
---

From having orbited them during the past few years, I feel that AI ethics, safety, and alignment — this whole collection of related fields — proceed, in great part, from the particular assumption that human values exist in some sufficiently coherent and recoverable form, and that the central problem is one of representing those values precisely enough to train AI systems to pursue them reliably. That is, whether via reinforcement learning from human feedback (RLHF)<sup id="fnref:1"><a href="#fn:1">1</a></sup>, debate, amplification, or formal verification, work on these topics aims broadly at addressing the question of how to get AI systems to do what we want.

This is a reasonable starting point, and has led to a wealth of valuable work since we began to collectively think about these topics more seriously sometime in the early 2010s. But I believe this question actually defers a more fundamental one that turns out to be far more difficult, which is: what *is* it that we want?

Current methods for this kind of value alignment do their best. Some approaches attempt to recover implicit preferences from behavioral data, on the assumption that, given enough signal, we can approximate what people actually desire beneath the surface of their choices. Others skip over the question entirely, treating value specification as a solved or solvable problem downstream of sufficient compute and feedback. But I don't think either approach is adequate. The behavioral data from which preferences are inferred is not adequately reflectively endorsed by the people producing it, as we act under constraint, habit, and social pressure as much as genuine preference (more on this in a bit). And the question of whose values, combined how, and updated by whom, cannot be dissolved by just collecting more data. Furthermore, these methods are notoriously brittle when it comes to capturing the structure of values (the relationships between them, the tradeoffs, the context-dependence) even if they perform adequately on surface-level behavioral proxies.

Now to be fair, I don't think many working in these fields would disagree with me about any of this, and if they did, I've potentially done myself a disservice in positioning myself against them by only brusquely listing my main concerns above. In what follows, I wish to merely demonstrate the importance of this more foundational question, which I hope establishes that it is at least neglected in its current treatment.

Phrasing this question differently, then, we might ask: what are the deeper structural values that should constrain powerful systems? Whose values count, and how are conflicts between them resolved? How do values change over time, and what mechanisms ensure that the representation stays current?

In my view, these remain, for the most part, unanswered, or answered only implicitly<sup id="fnref:2"><a href="#fn:2">2</a></sup>. What this suggests is that alignment is not only a technical problem. It is also a problem of values infrastructure. Even a perfectly capable system needs some mechanism external to itself that makes our values explicit, adjudicates between them and keeps them current. Building that mechanism is not obviously an AI problem at all. That is what makes it worth pausing on.

What's more, even if we accept that thinking about concrete values for AI systems is neglected, the question of how to actually build systems that make values legible and load-bearing in real human institutions seems to me more or less *completely* open, yet is central for any kind of meaningful effort to build technology whose autonomous behavior we would endorse. This is not a new problem. Human societies have long depended on their own values infrastructure such as religious traditions, legal systems, democratic deliberation and markets to perform exactly this function, with uneven and often fragile success. That so much of this infrastructure now seems to be straining or failing outright is one way of naming what is increasingly called the metacrisis.

## I. An analogy: the metacrisis

To motivate the importance of understanding and representing our collective values, and to foreshadow why this matters beyond just AI, we might look at how similar lack of knowledge about values manifests in existing human systems. The concept of the "metacrisis", associated with thinkers like Daniel Schmachtenberger and the broader Game B discourse, offers a useful diagnostic frame<sup id="fnref:3"><a href="#fn:3">3</a></sup>.

The metacrisis, broadly speaking, refers to a convergence of crises whose common generator is a particular kind of *systemic* misalignment of values. Consider three examples. Climate change is not primarily an energy problem, as the technologies needed to decarbonize do indeed exist and are increasingly cost-competitive<sup id="fnref:4"><a href="#fn:4">4</a></sup>. The obstacle is merely a misalignment between the incentive structures of fossil fuel markets and financial institutions, which reward short-term extraction, and the long-term survival interests of the people those institutions nominally serve. Additionally, democratic erosion is not primarily a political problem. It is downstream of a misalignment between the logic of attention-driven media ecosystems, which reward outrage and polarization, and the requirements of genuine collective deliberation, a dynamic documented by Eli Pariser's work on filter bubbles<sup id="fnref:5"><a href="#fn:5">5</a></sup> and by further empirical work on the spread of misinformation, which travels significantly faster and further than accurate information on social media<sup id="fnref:6"><a href="#fn:6">6</a></sup>. Furthermore, epistemic fragmentation, the breakdown of shared factual ground, is not primarily a media problem. It reflects a misalignment between the incentives facing information producers and distributors and the epistemic needs of the communities consuming that information, a dynamic that has been analyzed in terms of how algorithmically curated information environments fragment shared reality<sup id="fnref:7"><a href="#fn:7">7</a></sup>. In each case, the crisis on display is downstream of a more fundamental failure, which is human systems having lost the capacity to coordinate around shared values at the scale and speed that current challenges demand.

Analogous to these cases, I think that we cannot meaningfully align AI systems with human values if we do not first have functioning mechanisms for identifying, aggregating, and institutionalizing those values in human systems. **The alignment problem with human values for AI inherits the dysfunction and misalignment of the institutions it is embedded in. Yet this fundamental alignment problem, properly understood, is not primarily a problem about AI systems. It is, in fact, a problem about human systems, about whether we have the institutional capacity to know what we collectively value, represent it coherently, and hold powerful actors accountable to it.**

## II. A diagnosis: the missing values layer

Assuming we can make some headway on understanding and working around shared values, let us consider a bit more how values currently fail to function in real human systems, away from the metacrisis lens. In most organizations, values exist as mission statements, rendering them aspirational, vague, and almost entirely disconnected from actual decision-making. For instance, Enron's stated core values of "integrity, communication, respect, and excellence" appeared in its 2000 Annual Report (p. 29) and were, according to multiple accounts, chiseled in marble in the main lobby of its Houston headquarters<sup id="fnref:8"><a href="#fn:8">8</a></sup>. Yet when faced with real decisions requiring tradeoffs between short-term gain and long-term integrity, those values provided no guidance and imposed no constraint. Decisions leading to its eventual downfall were made through informal power dynamics, inertia, or whoever argued most confidently, and these public-facing, stated values were merely decorative.

This is also not unique to corrupt organizations, as even well-intentioned nonprofits, cooperatives, and public institutions face the same structural problem. Research on organizational culture has found consistently that stated values diverge from enacted values (ie. the values actually visible in decisions, resource allocation, and behavior) across organizations of all kinds<sup id="fnref:9"><a href="#fn:9">9</a></sup>. A community organization that says it values both environmental sustainability and affordability has not actually resolved anything *until it specifies what happens when those values conflict*, as they routinely do. Without that specificity, the values document sits in a drawer, and has absolutely no practical impact.

In markets, values are represented through price signals, which I think is a *radical* compression of human preference that treats willingness-to-pay as a proxy for what people actually care about. This representation undoubtedly has advantages, as it aggregates dispersed information efficiently, enables coordination among strangers, and provides a feedback mechanism that disciplines producers. In narrow domains where preferences are stable, individual, and well-informed, the price mechanism works reasonably well. However, it also systematically excludes values that are not easily monetized, aggregates preferences in ways that distort minority positions, and creates no mechanism for distinguishing genuine values from preferences shaped by advertising, social pressure, or limited options. For instance, a person who buys fast fashion is not expressing a value for environmental destruction so much as expressing a constrained preference under conditions of limited income and limited alternatives. Thus, markets on their own are insufficient for eliciting values in the way we would want, and the question of what "the way we would want" means is precisely what remains underspecified.

In democratic governance, values are aggregated through voting systems that are well-understood to produce suboptimal outcomes even under idealized conditions (a result formalized by Arrow's impossibility theorem<sup id="fnref:10"><a href="#fn:10">10</a></sup>). In practice, these representations of values are subject to manipulation, gerrymandering, and the distortions of media ecosystems that reward outrage over nuance, clickbait over measured analysis. And what's the result? A system that produces the appearance of value aggregation while generating outputs that large majorities actively oppose. On gun control, 56% of Americans favor stricter laws covering the sale of firearms, and 86% support universal background checks for all firearm sales<sup id="fnref:11"><a href="#fn:11">11</a></sup>, yet federal legislation reflecting these preferences has not materialized. On drug policy, 70% of Americans support legalizing marijuana<sup id="fnref:12"><a href="#fn:12">12</a></sup>, yet it remains federally prohibited. Again, the gap between expressed public values and legislative outcomes is not an anomaly but a structural feature of the system.

In AI systems, values are approximated through behavioral proxies, such as RLHF<sup id="fnref:13"><a href="#fn:13">13</a></sup>, constitutional AI<sup id="fnref:14"><a href="#fn:14">14</a></sup> and direct preference optimization<sup id="fnref:15"><a href="#fn:15">15</a></sup>, among others. These do indeed capture something of substance, but put to the test, these representations still diverge meaningfully from actual human values in ways that are difficult to detect and potentially catastrophic at scale. For example, a language model trained to maximize human approval ratings will learn to tell people what they want to hear rather than what may be accurate, a failure mode documented in the alignment literature as sycophancy<sup id="fnref:16"><a href="#fn:16">16</a></sup>. Similarly, a medical AI assistant that has learned to be agreeable rather than accurate might validate a patient's self-diagnosis rather than contradict it, even when the self-diagnosis is dangerously wrong. A recommendation system trained to maximize engagement, rather than to reflect what users would endorse on reflection, will learn to exploit psychological vulnerabilities, surfacing content that triggers anxiety, outrage, or compulsion regardless of whether users would choose it under calmer conditions<sup id="fnref:17"><a href="#fn:17">17</a></sup>. This proxy then compounds across time, as each layer of approximation between a behavioral signal and the underlying value it is meant to represent introduces error, and those errors interact in ways that are difficult to predict or audit.

**Now, what to make of all this? I believe that what is fundamentally missing, across all of these systems, is a formal, structured, live representation — a "values layer," if you will — of what a community, organization, or institution actually cares about, connected to real decisions, updateable as values evolve, and resistant to capture by narrow interests.**

This problem is not merely institutional but, I believe, also technological. Making values legible at scale requires not just better governance structures but better elicitation tools. Consider the crudeness of our current instruments, such as annual engagement surveys, town halls, periodic strategic reviews. As well-intentioned as these might be, they are low-bandwidth and low-frequency, and they are highly susceptible to social desirability bias, where people say what sounds good rather than what they actually believe or prioritize. The mechanisms are also deeply passive, as they collect responses to questions rather than observing revealed commitments over time.

The contrast with even simple feedback mechanisms may be of use. A button in a restaurant that asks "how was your service today?" is certainly a weak signal by any rigorous standard, but it has several properties that these organizational values surveys lack entirely. For one, it is administered immediately after the relevant experience, when memory is fresh and the emotional salience of the encounter is still present. It is also low-friction enough that the threshold for responding is low, generating high participation rates. Furthermore, the response is binary, which eliminates the ambiguity introduced by rating scales. And crucially, the data is aggregated across many interactions and tracked over time, so that individual noise resolves into meaningful signals at the level of the institution. The restaurant uses this data to actually correct behavior, closing the feedback loop, while organizational values instruments almost never close the loop in any comparable way.

What would a higher-bandwidth equivalent look like for values? As just one idea, we structured digital elicitation that surfaces genuine preference orderings over real tradeoffs rather than abstract endorsements. For instance, asking "do you value fairness?" produces near-universal assent and almost no information, but asking "given a fixed budget, would you prioritize option A that benefits 80% of members equally, or option B that disproportionately benefits the 20% who are most disadvantaged?" forces a genuine choice between values that are both sincerely held but cannot both be fully satisfied. Presenting concrete tradeoffs in this way produces meaningfully different and more honest responses. Aggregating these responses across members, tracking how they shift over time, and connecting them to actual decision records creates something closer to a live values layer than anything most institutions currently maintain.

But a critical clarification is warranted here: **what I am describing is categorically different from the kind of behavioral data collection that has become standard in the technology industry, where user actions are tracked at scale and mined for patterns that can be used to predict and influence behavior**. This more sinister way of doing things extracts revealed preferences from behavior without consent, often without awareness, and uses the resulting profiles to serve commercial interests that may be orthogonal or actively opposed to the interests of the people being profiled. The values data I am describing is different in kind, consisting of reflectively endorsed judgments, expressed by people who understand better what they are expressing and why, in response to questions that are designed to surface what they genuinely care about rather than what they can be induced to do. The distinction matters both morally and practically. Behavioral data only tells you what people do under the constraints they face. Reflectively endorsed judgments, on the other hand, tell you what they would endorse upon reflection, which I would claim is — even in the midst of them *still* not being perfect — a much better approximation of what we mean by values.

## III. A solution in the form of systems design?

Now, in spite of having continually pointed out shortcomings of many human systems with regards to value adherence, I don't actually think the reason that the values layer is missing is because people simply don't care about values. Rather, I think we simply lack the machinery to make values legible, stable, and load-bearing in real systems.

Elinor Ostrom's fascinating work on common-pool resource governance I think serves as some of the most rigorous empirical evidence we have about what this machinery can look like at small scale<sup id="fnref:18"><a href="#fn:18">18</a></sup>. Her case studies, spanning Swiss alpine communities, Japanese fishing villages, and Spanish irrigation systems, document communities that successfully maintained shared resources across generations, not through markets or states, but through carefully designed structures that made values explicit, created accountability for violations, and maintained short feedback loops between actions and consequences.

To dig deeper into one example, the Törbel community in the Swiss canton of Valais has managed shared alpine meadows through documented institutional arrangements since at least 1483. Its structure includes clearly defined membership rules, seasonal usage rights calibrated to each household's actual holdings, collective monitoring by community members with direct stakes in the outcome, and graduated sanctions for violations. The community's values of sustainable use, proportional contribution, long-term stewardship were not expressed in a mission statement, but were rather encoded in the rules themselves, so when someone violates them, the consequences are real and visible. And when the rules stop working, there are legitimate mechanisms for changing them.

What Ostrom documented in pre-digital communities, I think we now need to build for organizations, markets, and eventually AI systems possibly operating at far greater scale and speed. The core tasks of making values explicit enough to be actionable so as to create accountability structures that make defection from shared values costly, and building feedback loops short enough to enable genuine learning and adaptation are the same. This is, of course, a nontrivial design problem, but it is one that requires understanding how human systems actually function rather than how we might wish them to function.

## IV. What's preventing us from implementation?

Now, there is no shortage of theoretical work on values, alignment, and coordination. Philosophy has sophisticated accounts of value theory<sup id="fnref:19"><a href="#fn:19">19</a></sup>, economics has mechanism design<sup id="fnref:20"><a href="#fn:20">20</a></sup> and social choice theory<sup id="fnref:21"><a href="#fn:21">21</a></sup>, political theory has deliberative democracy<sup id="fnref:22"><a href="#fn:22">22</a></sup>, AI safety has coherent extrapolated volition<sup id="fnref:23"><a href="#fn:23">23</a></sup>, moral parliament<sup id="fnref:24"><a href="#fn:24">24</a></sup>, and increasingly elaborate RLHF variants<sup id="fnref:25"><a href="#fn:25">25</a></sup>, among other grounding concepts. Nonetheless, there is a lack of empirically grounded methodology for actually building values infrastructure in real human systems that are messy, politically charged, subject to power asymmetries, and populated by people whose values are inarticulate, inconsistent, or evolving.

I'm inclined to believe that some weighted combination of both intentional design and tried-and-tested, practical heuristics are needed, and that a gap between these exists because of structural reasons, a general siloing of theory and practice. Academic disciplines tend to work at one level of abstraction and rarely cross into implementation. AI safety research is technically sophisticated but I believe often does not take into account the reality of how human institutions function. Social entrepreneurs and civic technologists build tools without sufficient theoretical grounding to generalize from their cases. And the communities most in need of better coordination mechanisms, such as small organizations, activist groups, local governments, are the least resourced to develop them. As a result, we have a landscape in which the theoretical tools for building values infrastructure exist but are not connected to real institutional contexts, and the real institutional contexts that need values infrastructure do not have access to the theoretical tools.

## V. Toward an implementation

Nassim Taleb's concept of skin in the game may offer a useful entry point for thinking about what closing this gap requires<sup id="fnref:26"><a href="#fn:26">26</a></sup>. Taleb's simple, yet key observation is that systems degrade when decision-makers are insulated from the consequences of their decisions. His recurring example is the "Bob Rubin trade," named after the former U.S. Treasury Secretary and Citigroup advisor who collected over $120 million in compensation in the decade preceding the 2008 financial crisis, then bore no personal cost when Citigroup required a taxpayer bailout<sup id="fnref:27"><a href="#fn:27">27</a></sup>. The pattern generalizes widely. Economists who recommended austerity programs in the aftermath of the 2008 crisis, including figures like the IMF's Olivier Blanchard, whose team later acknowledged systematic underestimation of austerity's contractionary effects<sup id="fnref:28"><a href="#fn:28">28</a></sup>, similarly faced absolutely no personal consequences when those programs deepened recessions and increased unemployment in the countries that implemented them. The feedback loops that would otherwise discipline bad judgment were severed, and the people best positioned to improve the system had the least incentive to do so. To give a nod to Taleb, in a functioning system, those crooks should be out of a job and publicly shamed, and macroeconomics (especially of the more mathematical nature) should have ceased to be a serious discipline.

All in all, what Taleb diagnoses as a moral failure is, at a structural level, a value infrastructure failure, where a system in which the stated purpose is not actually connected to the incentives facing the people responsible for it. Now, I believe this points directly at what a value implementation program needs to accomplish. That is, it is not enough to articulate good values. **The structures (both institutional and technological) must make it individually costly to violate them and individually beneficial to uphold them.** The game must be designed so that honest, values-consistent behavior is also the strategically rational behavior.

Complex systems science adds a complementary perspective. Healthy complex systems — of which we might term economies as an example — maintain tight feedback loops between actions and their consequences, for this is how they self-correct and adapt<sup id="fnref:29"><a href="#fn:29">29</a></sup>. Systematically severed feedback loops are a signature of the same metacrisis dynamics, such as carbon emissions whose costs are borne by future generations, financial instruments whose risks are distributed away from the people who create them, and political decisions whose consequences fall on constituencies without voice. Building a values layer is, in part, the work of restoring these severed loops.

The right place to start is with systems that are small and bounded enough that feedback loops are fast and failure is survivable, such as small activist organizations, research groups, local governance bodies, worker cooperatives. These are systems where the value elicitation problem is manageable, where the people involved have genuine stakes in getting it right, and where the consequences of a failed experiment are limited enough to allow honest learning.

Now, we might attempt to sketch out a core methodology of sorts, which involves at least three components. First, there is something like a *structured elicitation of values*, or carefully designed processes for bringing out what people actually value, as distinct from what they say they value in socially charged settings. The gap between these is not a matter of dishonesty but of context, as people respond differently when they are asked to endorse abstract values versus when they are forced to choose between them under realistic constraints. Incentive-compatible elicitation, drawing on mechanism design, can reduce this gap by structuring the process so that honest expression is individually rational. I don't take this to be a novel idea in theory, as mechanism design has developed sophisticated tools for eliciting private information honestly (including the Vickrey auction and various scoring rules for probabilistic forecasts) but applying these tools to the elicitation of structured value preferences in real communities is largely unexplored territory.

Second, there is the need to *rigorously map out our values*, to represent elicited values in a structured form that makes their relationships explicit, surfaces genuine tensions, and is precise enough to provide guidance on real decisions. The goal is not a list of values, but rather something closer to a map of how they relate and where they conflict. The moral graph formalism developed by the Meaning Alignment Institute is one approach to this, and related work on preference aggregation in social choice theory and on value learning in AI alignment provides additional conceptual resources. Whatever a refined version ends up looking like, it ought to satisfy the key requirement that the representation be precise enough to actually distinguish between situations where values point in the same direction and situations where they genuinely conflict, rather than collapsing all tension into vague reassurances that everything can be balanced.

Third, there is something like *decision integration*, meant to connect the values representation to actual decision processes, so that the map does real work rather than sitting in a drawer. This is ultimately a governance design problem, of embedding the values layer in the rules, procedures, and accountability structures of an organization or community such that it actually constrains decisions. Ostrom's design principles suggest some answers, for instance, in that the values representation needs to be collectively owned and modifiable, violations of it need to be visible and consequential, and there need to be legitimate mechanisms for updating it when circumstances change. The interesting part is seeing how what Ostrom achieved through careful institutional design in pre-digital communities can be extended to digital tools, potentially at a greater scale and lower cost.

And this is where the technological dimension of the program becomes important. Digital interfaces can present concrete tradeoff scenarios at scale, reducing the social pressure dynamics that distort in-person deliberation and enabling asynchronous participation that is not simply dominated by whoever speaks most confidently. Computational methods, including the moral graph formalism and related work on value learning, can represent the structure of values in ways that are way too complex for purely manual methods. Software that maintains a live record of stated values and flags when proposed decisions appear to conflict with them creates an accountability mechanism that does not depend on any individual's memory or goodwill.

None of these tools currently exist in sufficiently developed form for this purpose. Participatory budgeting platforms like Decidim<sup id="fnref:30"><a href="#fn:30">30</a></sup> and opinion-mapping tools like Pol.is<sup id="fnref:31"><a href="#fn:31">31</a></sup> do gesture in the right direction, but they are not designed around structured values representation. The gap between what these tools do and what a genuine values layer would require is substantial, but tractable, and it is the gap that the work described aims at closing. I believe the output of this effort, over time, is not just a set of case studies but a whole library of reusable design patterns and tested mechanisms for values elicitation, aggregation, and decision integration that can be adapted across contexts. We might see this as a new version of the Ostrom project, just extended and formalized for the current moment.

As the methodology matures, it could scale, first from communities to organizations, then from organizations to markets, where richer preference expression mechanisms can supplement or replace the blunt instrument of price signals (explored in the RadicalxChange literature on quadratic voting and plural money<sup id="fnref:32"><a href="#fn:32">32</a></sup>). Eventually, we could even bring in AI systems, where a values layer built and validated in human communities provides the empirical foundation for alignment targets that are actually grounded in how human values work in practice, rather than how a small group of researchers imagines they work.

The ambition is not to solve the alignment problem theoretically. It is to build the institutional and technological infrastructure that makes alignment tractable, starting at human scale, where the feedback loops are fast enough to learn from, and to then work upward from there. As we saw, plenty of theoretical formalisms already exist. What I think remains is merely the harder and less glamorous work of seeing how they hold up.

---

<div class="footnotes">
<ol>
<li id="fn:1">
<p>Christiano et al., "Deep Reinforcement Learning from Human Preferences," NeurIPS 2017. <a href="#fnref:1" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:2">
<p>The Meaning Alignment Institute is among the few groups working explicitly on this prior problem, through constructs like the moral graph. See Joe Edelman and Oliver Klingefjord, "The First Moral Graph," Meaning Alignment Institute, 2024. <a href="#fnref:2" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:3">
<p>Rosie Bell & Rufus Pollock, "From Polycrisis to Metacrisis: A Short Introduction," Life Itself Sensemaking Studio, *metacrisis.info*. Available at: [https://metacrisis.info/paper](https://metacrisis.info/paper) <a href="#fnref:3" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:4">
<p>The International Renewable Energy Agency's annual Renewable Power Generation Costs reports document this trend in detail. See: IRENA, "Renewable Power Generation Costs in 2023," IRENA, 2024. <a href="#fnref:4" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:5">
<p>Pariser, "The Filter Bubble," Penguin Press, 2011. <a href="#fnref:5" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:6">
<p>Vosoughi, Roy, and Aral, "The spread of true and false news online," *Science*, Vol. 359, Issue 6380, 2018. <a href="#fnref:6" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:7">
<p>Sunstein, "#Republic: Divided Democracy in the Age of Social Media," Princeton University Press, 2017. <a href="#fnref:7" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:8">
<p>Burkus, "A Tale of Two Cultures," *Values-Based Leadership Journal*, Vol. 4, Issue 1. <a href="#fnref:8" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:9">
<p>Argyris and Schon, "Organizational Learning: A Theory of Action Perspective," Addison-Wesley, 1978, introduced the distinction between espoused theories and theories-in-use that captures this gap precisely. <a href="#fnref:9" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:10">
<p>Arrow, "Social Choice and Individual Values," Yale University Press, 1951. <a href="#fnref:10" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:11">
<p>Gallup, "Majority in U.S. Continues to Favor Stricter Gun Laws," October 2023; McCourtney Institute for Democracy, Mood of the Nation Poll, May 2023. <a href="#fnref:11" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:12">
<p>Gallup, "Grassroots Support for Legalizing Marijuana Hits Record 70%," November 2023. <a href="#fnref:12" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:13">
<p>Christiano et al., 2017, op. cit. <a href="#fnref:13" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:14">
<p>Bai et al., "Constitutional AI: Harmlessness from AI Feedback," arXiv:2212.08073, 2022. <a href="#fnref:14" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:15">
<p>Rafailov et al., "Direct Preference Optimization: Your Language Model is Secretly a Reward Model," NeurIPS 2023. <a href="#fnref:15" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:16">
<p>Perez et al., "Sycophancy to Subterfuge: Investigating Reward Tampering in Language Models," arXiv:2406.10162, 2024. <a href="#fnref:16" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:17">
<p>Stray et al., "What are You Optimizing For? Aligning Recommender Systems with Human Values," ICML 2020 Workshop on Participatory Approaches to Machine Learning. <a href="#fnref:17" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:18">
<p>Ostrom, "Governing the Commons: The Evolution of Institutions for Collective Action," Cambridge University Press, 1990; the Törbel case study appears in Chapter 3, pp. 61–65, drawing on the ethnographic work of Robert Netting, "Balancing on an Alp," Cambridge University Press, 1981. <a href="#fnref:18" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:19">
<p>Chang, "Incommensurability, Incomparability, and Practical Reason," Harvard University Press, 1997. <a href="#fnref:19" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:20">
<p>Hurwicz and Reiter, "Designing Economic Mechanisms," Cambridge University Press, 2006. <a href="#fnref:20" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:21">
<p>Arrow, "Collective Choice and Social Welfare," Harvard University Press, 1970. <a href="#fnref:21" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:22">
<p>Fishkin, "When the People Speak," Oxford University Press, 2009. <a href="#fnref:22" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:23">
<p>Yudkowsky, "Coherent Extrapolated Volition," MIRI technical report, 2004. <a href="#fnref:23" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:24">
<p>MacAskill, Ord, and Cotton-Barratt, "Moral Uncertainty," Oxford University Press, 2020. <a href="#fnref:24" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:25">
<p>Bai et al., "Constitutional AI: Harmlessness from AI Feedback," arXiv:2212.08073, 2022. <a href="#fnref:25" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:26">
<p>Taleb, "Skin in the Game: Hidden Asymmetries in Daily Life," Allen Lane, 2018. <a href="#fnref:26" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:27">
<p>Taleb, 2018, pp. 5–6. <a href="#fnref:27" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:28">
<p>Blanchard and Leigh, "Growth Forecast Errors and Fiscal Multipliers," IMF Working Paper, 2013. <a href="#fnref:28" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:29">
<p>Bar-Yam, "Making Things Work," NECSI Knowledge Press, 2004; Sterman, "Business Dynamics," McGraw-Hill, 2000. <a href="#fnref:29" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:30">
<p>Barandiaran et al., "Decidim: Political and Technopolitical Networks for Participatory Democracy," 2017. <a href="#fnref:30" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:31">
<p>Small et al., "Polis: Scaling Deliberation by Mapping High Dimensional Opinion Spaces," *Recerca* journal, 2021. <a href="#fnref:31" class="reversefootnote">&#8617;</a></p>
</li>
<li id="fn:32">
<p>Weyl and Posner, "Radical Markets," Princeton University Press, 2018. <a href="#fnref:32" class="reversefootnote">&#8617;</a></p>
</li>
</ol>
</div>