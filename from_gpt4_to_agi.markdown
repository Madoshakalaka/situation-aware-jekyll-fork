---
layout: post
title: "From GPT-4 to AGI: Counting the OOMs"
toc: true
---


**AGI by 2027 is strikingly plausible. GPT-2 to GPT-4 took us from ~preschooler to ~smart high-schooler abilities in 4 years. Tracing trendlines in compute (~0.5 orders of magnitude or OOMs/year), algorithmic efficiencies (~0.5 OOMs/year), and “unhobbling” gains (from chatbot to agent), we should expect another preschooler-to-high-schooler-sized qualitative jump by 2027.**


> Look. The models, they just want to learn. You have to understand this. The models, they just want to learn.
>
> — Ilya Sutskever (circa 2015, via Dario Amodei)

GPT-4’s capabilities came as a shock to many: an AI system that could write code and essays, could reason through difficult math problems, and ace college exams. A few years ago, most thought these were impenetrable walls.

But GPT-4 was merely the continuation of a decade of breakneck progress in deep learning. A decade earlier, models could barely identify simple images of cats and dogs; four years earlier, GPT-2 could barely string together semi-plausible sentences. Now we are rapidly saturating all the benchmarks we can come up with. And yet this dramatic progress has merely been the result of consistent trends in scaling up deep learning. 

There have been people who have seen this for far longer. They were scoffed at, but all they did was trust the trendlines. The trendlines are intense, and they were right. The models, they just want to learn; you scale them up, and they learn more.

I make the following claim: **it is strikingly plausible that by 2027, models will be able to do the work of an AI researcher/engineer.** That doesn’t require believing in sci-fi; it just requires believing in straight lines on a graph. 

![image tooltip here](/base_scaleup.png)

In this piece, I will simply “count the OOMs” (OOM = order of magnitude, 10x = 1 order of magnitude): look at the trends in 1) compute, 2) algorithmic efficiencies (algorithmic progress that we can think of as growing “effective compute”), and 3) ”unhobbling” gains (fixing obvious ways in which models are hobbled by default, unlocking latent capabilities and giving them tools, leading to step-changes in usefulness). We trace the growth in each over four years before GPT-4, and what we should expect in the four years after, through the end of 2027. Given deep learning’s consistent improvements for every OOM of effective compute, we can use this to project future progress. 

Publicly, things [have been quiet](https://x.com/leopoldasch/status/1768868127138549841) for a year since the GPT-4 release, as the next generation of models has been in the oven—leading some to proclaim stagnation and that deep learning is hitting a wall. But by counting the OOMs, we get a peek at what we should actually expect. 

The upshot is pretty simple. GPT-2 to GPT-4—from models that were impressive for sometimes managing to string together a few coherent sentences, to models that ace high-school exams—was not a one-time gain. We are racing through the OOMs extremely rapidly, and the numbers indicate we should expect another ~100,000x effective compute scaleup—resulting in another GPT-2-to-GPT-4-sized qualitative jump—over four years. Moreover, and critically, that doesn’t just mean a better chatbot; picking the many obvious low-hanging fruit on “unhobbling” gains should take us from chatbots to agents, from a tool to something that looks more like drop-in remote worker replacements. While the inference is simple, the implication is striking. Another jump like that very well could take us to AGI, to models as smart as PhDs or experts that can work beside us as coworkers. Perhaps most importantly, if these AI systems could automate AI research itself, that would set in motion intense feedback loops—the topic of [the next piece in the series](https://situational-awareness.ai/from-agi-to-superintelligence/).

Even now, barely anyone is pricing all this in. But situational awareness on AI isn’t actually that hard, once you step back and look at the trends. If you keep being surprised by AI capabilities, just start counting the OOMs.

# The last four years

We have machines now that we can basically [talk to like humans](https://openai.com/index/hello-gpt-4o/). It’s a remarkable testament to the human capacity to adjust that this seems normal, that we’ve become inured to the pace of progress. But it’s worth stepping back and looking at the progress of just the last few years.

## GPT-2 to GPT-4

Let me remind you of how far we came in just the ~4 (!) years leading up to GPT-4. 

**GPT-2** (2019) ~ preschooler: “Wow, it can string together a few plausible sentences.” A very-cherry-picked example of a semi-coherent story about unicorns in the Andes it generated was incredibly impressive at the time. And yet GPT-2 could barely count to 5 without getting tripped up; when summarizing an article, it just barely outperformed selecting 3 random sentences from the article.

![image tooltip here](/gpt2_examples.png)

**GPT-3** (2020) ~ elementary schooler: “Wow, with just some few-shot examples it can do some simple useful tasks.” It started being cohesive over even multiple paragraphs much more consistently, and could correct grammar and do some very basic arithmetic. For the first time, it was also commercially useful in a few narrow ways: for example, GPT-3 could generate simple copy for SEO and marketing.

...

## The trends in deep learning

The pace of deep learning progress in the last decade has simply been extraordinary. A mere decade ago it was revolutionary for a deep learning system to identify simple images. Today, we keep trying to come up with novel, ever harder tests, and yet each new benchmark is quickly cracked. It used to take decades to crack widely-used benchmarks; now it feels like mere months.


![image tooltip here](/owid-test-scores.png)

We’re literally running out of benchmarks.  As an anecdote, my friends Dan and Collin made a benchmark called MMLU a few years ago, in 2020. They hoped to finally make a benchmark that would stand the test of time, equivalent to all the hardest exams we give high school and college students. Just three years later, it’s basically solved: models like GPT-4 and Gemini get ~90%. 

Or consider the [MATH benchmark](https://arxiv.org/pdf/2103.03874), a set of difficult mathematics problems from high-school math competitions. When the benchmark was released in 2021, the best models only got ~5% of problems right. And the original paper noted: “Moreover, we find that simply increasing budgets and model parameter counts will be impractical for achieving strong mathematical reasoning if scaling trends continue. To have more traction on mathematical problem solving we will likely need new algorithmic advancements from the broader research community”—we would need fundamental new breakthroughs to solve MATH, or so they thought. [A survey of ML researchers](https://bounded-regret.ghost.io/ai-forecasting-one-year-in/) predicted minimal progress over the coming years; and yet within just a year (by mid-2022), the best models went from ~5% to 50% accuracy; now, MATH is basically solved, with recent performance over 90%. 

# Counting the OOMs

How did this happen? The magic of deep learning is that it just works—and the trendlines have been astonishingly consistent, despite naysayers at every turn. 

With each OOM of effective compute, models predictably, reliably get better. If we can count the OOMs, we can (roughly, qualitatively) extrapolate capability improvements. That’s how a few prescient individuals saw GPT-4 coming. 

We can decompose the progress in the four years from GPT-2 to GPT-4 into three categories of scaleups:

1. *Compute*: We’re using much bigger computers to train these models.
2. *Algorithmic efficiencies*: There’s a continuous trend of algorithmic progress. Many of these act as “compute multipliers,” and we can put them on a unified scale of growing effective compute.
3. *”Unhobbling” gains*: By default, models learn a lot of amazing raw capabilities, but they are hobbled in all sorts of dumb ways, limiting their practical value. With simple algorithmic improvements like reinforcement learning from human feedback (RLHF), chain-of-thought (CoT), tools, and scaffolding, we can unlock significant latent capabilities.

## Compute

I’ll start with the most commonly-discussed driver of recent progress: throwing (a lot) more compute at models. 

Many people assume that this is simply due to Moore’s Law. But even in the old days when Moore’s Law was in its heyday, it was comparatively glacial—perhaps 1-1.5 OOMs per decade. We are seeing much more rapid scaleups in compute—close to 5x the speed of Moore’s law—instead because of mammoth investment. (Spending even a million dollars on a single model used to be an outrageous thought nobody would entertain, and now that’s pocket change!)

| Model      | Estimated compute       | Growth            |
|------------|-------------------------|-------------------|
| GPT-2 (2019) | ~4e21 FLOP             |                   |
| GPT-3 (2020) | ~3e23 FLOP             | + ~2 OOMs         |
| GPT-4 (2023) | 8e24 to 4e25 FLOP      | + ~1.5–2 OOMs     |

We can use public estimates from Epoch AI (a source widely respected for its excellent analysis of AI trends) to trace the compute scaleup from 2019 to 2023. GPT-2 to GPT-3 was a quick scaleup; there was a large overhang of compute, scaling from a smaller experiment to using an entire datacenter to train a large language model. With the scaleup from GPT-3 to GPT-4, we transitioned to the modern regime: having to build an entirely new (much bigger) cluster for the next model. And yet the dramatic growth continued. Overall, Epoch AI estimates suggest that GPT-4 training used ~3,000x-10,000x more raw compute than GPT-2.

## Algorithmic efficiencies

While massive investments in compute get all the attention, algorithmic progress is probably a similarly important driver of progress (and has been dramatically underrated).

To see just how big of a deal algorithmic progress can be, consider the following illustration of the drop in price to attain ~50% accuracy on the MATH benchmark (high school competition math) over just two years. (For comparison, a computer science PhD student who didn’t particularly like math scored 40%, so this is already quite good.) Inference efficiency improved by nearly 3 OOMs—1,000x—in less than two years.
Though these are numbers just for inference efficiency (which may or may not correspond to training efficiency improvements, where numbers are harder to infer from public data), they make clear there is an enormous amount of algorithmic progress possible and happening. 

In this piece, I’ll separate out two kinds of algorithmic progress. Here, I’ll start by covering “within-paradigm” algorithmic improvements—those that simply result in better base models, and that straightforwardly act as compute efficiencies or compute multipliers. For example, a better algorithm might allow us to achieve the same performance but with 10x less training compute. In turn, that would act as a 10x (1 OOM) increase in effective compute. (Later, I’ll cover “unhobbling,” which you can think of as “paradigm-expanding/application-expanding” algorithmic progress that unlocks capabilities of base models.)

## Unhobbling

Finally, the hardest to quantify—but no less important—category of improvements: what I’ll call “unhobbling.”

Imagine if when asked to solve a hard math problem, you had to instantly answer with the very first thing that came to mind. It seems obvious that you would have a hard time, except for the simplest problems. But until recently, that’s how we had LLMs solve math problems. Instead, most of us work through the problem step-by-step on a scratchpad, and are able to solve much more difficult problems that way. “Chain-of-thought” prompting unlocked that for LLMs. Despite excellent raw capabilities, they were much worse at math than they could be because they were hobbled in an obvious way, and it took a small algorithmic tweak to unlock much greater capabilities.

- *Reinforcement learning from human feedback (RLHF).* Base models have incredible latent capabilities, but they’re raw and incredibly hard to work with. While the popular conception of RLHF is that it merely censors swear words, RLHF has been key to making models actually useful and commercially valuable (rather than making models predict random internet text, get them to actually apply their capabilities to try to answer your question!). This was the magic of  ChatGPT—well-done RLHF made models usable and useful to real people for the first time. The original InstructGPT paper has a great quantification of this: an RLHF’d small model was equivalent to a non-RLHF’d >100x larger model in terms of human rater preference.
- *Chain-of-thought (CoT).* CoT is a simple but powerful idea: instead of asking the model to answer a question immediately, you ask it to work through the problem step-by-step. This is how we solve hard problems, and it turns out that models can do this too. CoT was key to making models actually useful for math problems, and it was a key part of the MATH benchmark solution.
- *Scaffolding.* Scaffolding is a general idea that we can give models tools to make them more useful. For example, we can give them a calculator, or a scratchpad, or a way to remember what they’ve said before. These tools can make models much more useful, and they’re a key part of making models more useful for real-world tasks.
- *Tools.* Tools are a more general version of scaffolding. For example, we can give models a way to remember what they’ve said before, or a way to remember what they’ve been asked before. These tools can make models much more useful, and they’re a key part of making models more useful for real-world tasks.
- *Context Length.* Context length is a simple but powerful idea: instead of asking the model to answer a question immediately, you ask it to work through the problem step-by-step. This is how we solve hard problems, and it turns out that models can do this too. CoT was key to making models actually useful for math problems, and it was a key part of the MATH benchmark solution.

<details>
  <summary>Show more</summary>
  
  Not much to see here.

</details>
