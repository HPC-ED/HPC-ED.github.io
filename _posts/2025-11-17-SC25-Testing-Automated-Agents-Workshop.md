---
layout: post
title:  "[SC25] HPC-ED: Testing Automated Agents to Assess the Quality of Training Resource Metadata"
dateofevent: 2025-11-17 10:30:00 -0600
categories: workshop
presenters: 
- David Joiner
location: "St. Louis, Missouri"
eventurl: https://sc25.conference-program.com/presentation/?id=ws_bphpcte105&sess=sess203
abstract: >
    We present a proof-of-concept system for automating quality assurance (QA) in the HPC-ED federated training catalog using large language models (LLMs). The HPC-ED project aggregates metadata for training resources from multiple partner catalogs, improving discoverability for the high-performance computing (HPC) and cyberinfrastructure (CI) communities. While metadata publication processes have matured, QA remains largely manual, making it difficult to maintain accuracy and relevance at scale. We have created an agent using commercial AI API calls to evaluate user submitted metadata and return a quality score, to help content providers improve their submitted metadata. The agent bases its score on a combination of the submitted catalog metadata and an AI created summary of a low-level crawl of the content item, with automated extraction of embedded content such as YouTube video transcripts. We evaluated this agent on the HPC-ED Beta Catalog using four OpenAI models—GPT-3.5 Turbo, GPT-4o Mini, GPT-4.1 Nano, and GPT-4.1 Mini.
associated_event: ["Supercomputing 25", "https://sc25.supercomputing.org"]
image: "downloads/photos/SC25_DavidJoiner.jpg"
image_description: "Photo of David Joiner."
---
<!-- Added this to have post link on listing instead of host event (in front matter as "eventurl" ) link --> 
