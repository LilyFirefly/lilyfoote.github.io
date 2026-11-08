+++
title = "Django and LLMs"
date = 2026-11-08
draft = false
categories = ["Django"]
tags = ["django", "llms"]
+++

## Why I don't use LLMs myself

I don't like LLMs.

Firstly, I think they have [deep ethical problems](https://whynoai.info/ ). Creating them depends on mass plagiarism of creative work. The energy demand to train and run a model is leading to the creation of vast numbers of data centres, often running on fossil fuels, which exacerbates global warming. Cleaning training data often relies on exploitation of impoverished people across the world. The companies creating LLMs claim that it might "destroy humanity" but continue anyway in search of profit and self-interest.

Secondly, I enjoy the craft of programming, of learning new techniques and how to apply them to my projects. I also enjoy mentoring other humans, seeing them grow as a programmer and thriving. I enjoy working with friends on a shared goal. I do not want to become a supervisor of a machine that can never learn from its own mistakes and can never have an original thought. I am scared of becoming addicted (I already watch too much YouTube and scroll my phone too much when bored), and of deskilling myself by relying on an LLM.

## LLMs and Django Rusty Templates

[Django Rusty Templates](https://github.com/LilyFirefly/django-rusty-templates) is my project to re-implement Django's templating language in Rust. Early on, I accepted some contributions from people using LLMs. Over time, I found that this required a large amount of effort on my own part when reviewing to ensure that the contributed code matched my own quality requirements. In combination with the ethical problems noted above, this led me to [add an AI policy](https://github.com/LilyFirefly/django-rusty-templates/pull/394) which forbids using LLMs on "good first issue" tickets, to reserve these for onboarding humans who want to learn. For more experienced developers, the policy is slightly less strict, requiring an author who wishes to use an LLM to be very careful about copyright, their own understanding of the contribution and to be willing to accept full responsibility for it. In practice, since adding this policy I have received no more LLM contributions.

## LLMs and Django

I am a member of Django's Steering Council for the 6.x release series, along with Carlton, Emma, Frank and Tim.

Over the past couple of years Django has accepted LLM contributions, but this has not been free of negative impact. The Django Security Team has been receiving a high volume of security reports found by LLMs, which has taken a significant amount of time and effort to triage and handle. Many of these reports are either not a real issue, or are of low impact or require using Django in a configuration that is not recommended. Other open source projects ([curl](https://curl.se/dev/vuln-disclosure.html#lowmedium-severity-issues-are-public), [perhaps Wagtail](https://github.com/wagtail/rfcs/pull/117)) are reacting to this by no longer handling low and medium severity issues via the security process, instead moving them to public issue trackers. Django may well follow this example.

The flood of low-effort contributions doesn't just affect the Security Team. We have introduced a [GitHub actions bot](https://github.com/django/django/blob/main/scripts/pr_quality/check_pr.py) to automatically close PRs that don't follow Django's contribution guidelines. We are also [making changes](https://forum.djangoproject.com/t/proposed-changes-to-trac-to-address-problematic-contribution-patterns-please-vote/46191) to Trac (Django's bug tracker) in response to high volumes of LLM-driven PRs. These high volumes are especially prevalent in the run up to Google Summer of Code as aspiring applicants try to get contributions in to increase their chances of being accepted.

I'm writing this blog post in response to [Carlton's recent post in the Django Forum](https://forum.djangoproject.com/t/trust-in-django-llm-generated-code-in-core/46358) opening a discussion about reviewing the project's stance on LLM usage. I share the same fears that Carlton expresses that as a community we might start to damage the foundations that Django provides for projects to build upon by relying more on LLMs. In the short term I believe we will maintain Django's high quality through human diligence in review, especially by the Django Fellows and subject matter experts within the community. But this human diligence can also be exhausting, especially for the volunteers that make up the majority of the Django community, and I worry that continuing to permit LLM contributions will sap maintainer time and energy, and potentially lead to some maintainers stepping back because open source is no longer enjoyable.

As Carlton says, there are places where LLM usage is having a positive impact. However, on balance I think the community and the world would be healthier without LLMs, and I encourage the Django community to focus on making sure open source remains a place for human collaboration and community.

## Join me

I'm going to continue to write code by hand and I encourage everyone else to spend at least some of their coding time doing the same. Now that I've written this, I'm going to return to building Django Rusty Templates. If working on a project that prioritises human collaboration and learning sounds fun to you, I welcome you to [join me](https://github.com/LilyFirefly/django-rusty-templates/issues?q=is%3Aissue+state%3Aopen+label%3A%22good+first+issue%22)!
