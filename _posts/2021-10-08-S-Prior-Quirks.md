---
title: Quirks with the Solomonoff Prior
---

A standard formalization of Occam's razor is to fix some universal turing machine, weight all programs for that machine exponentially inversely related to their complexity, and then say the prior of a given bit string is the sum of all the weights of all programs that output that bit string. This is generally called the Solomonoff prior (although technically it's a collection of priors, one for each universal Turing machine). Despite having a number of problems, this is my current best guess for what prior ignorant agents should have over sensory experiences. However, this prior also has a bunch of semi-unintuitive properties:

* The Solomonoff prior is often used to justify the universe being simple to describe. However, it can also be used to justify the universe being such that the final outcome is simple to describe. For example, the program "search over programs until you find one with behavior B" has approximately complexity B, so outcomes that are simpler have higher weight in the Solmonoff Prior.
* The Solomonoff prior is extremely aggressive. If some description of the world is 10 bits simpler than some other description, you should be 1000x more confident that the simpler description is true. This property means that nearly all hypotheses that have any amount of complexity not totally pinned down by evidence can be rejected as false outright.
* You have a pick a universal turing machine. Python is such a machine. You can also imagine Python+Bob, a programming language that has a `Bob` function that accepts strings as input and outputs whatever Bob would have said if you read him that string. This is also a universal turing machine. Bob has some complexity C in Python, so the probabilities assigned to various programs by these two universal turing machines can differ by at most about $$2^{-C}$$. However, C can be unboundedly large. AIso observe that it's possible to construct universal turing machines with any computably enumerable list of properties (I think). Consider this an interesting open problem in thinking about universal priors.
* The Solomonoff prior assigns 0 prior probability to uncomputable universes existing. I'm not sure how to feel about this one. It seems at least plausible to me that uncomputable universes exist, so this is another interesting open problem.
* If you draw two bit strings from the Solomonoff prior, the changes that they're the same are like 1/4. To see this, just notice that there's approximately a 1/2 chance that you draw the simplest bit string. That's sort of weird. The chances that two functions are the same is also like 1/4 for the same reason. (Hence the saying "all is one" is mostly true. The saying "all is zero" is just as true, so I'm not sure how many points to get.)
*  If you restrict the Solomonoff prior to programs that output integers (uncomputable, but whatever), the expectation of any non-negative quantity is infinity. To see this, simply note that functions are penalized exponentially inversely proportionally to complexity and super-exponential functions exist. I'm tempted to claim something like "therefore the amount of balloons that exist is infinite in expectation", but that has the wrong type signature. It might be possible to make that argument work in combination with the observation that the Solomonoff prior can also be used as a prior over outcomes. Consider this another semi-open problem, although I think it can basically be easily resolved if you take the flesh out all the details of what you're actually doing when you compute the expectation with respect to the Solomonoff prior.