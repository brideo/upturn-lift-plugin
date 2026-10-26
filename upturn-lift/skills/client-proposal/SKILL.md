---
name: client-proposal
description: "Write a client proposal PDF for a website, backed by what Upturn Lift measured: a decision summary, the opportunity in dollars, strategy and roadmap, priced options with a return model, success measures, risks and an acceptance block. Use when the owner asks for a \"proposal\", \"quote\", \"pitch\", \"scope of work\" or \"something to send the client\" for a site."
allowed-tools: Read, Write, Bash
---

# Client proposal

The proposal is optional and comes last in the run order: it works best once the strategy and task plan exist.

1. Pick the site (`list_sites`). Call `get_proposal_inputs`: the client's brief, the measured evidence, the latest strategy, the saved sender details and the PDF spec. **Follow the method it returns.**
2. **Ask the owner** for the scope, the prices and any missing sender details. Save sender details with `save_proposal_sender`.
3. Write the proposal and build it as a PDF to the spec returned. It isn't stored in Upturn Lift: hand the owner the file.

## Never invent

Prices, results, case studies, testimonials or guarantees. If something the spec asks for isn't known, ask, or leave a clearly marked placeholder and say so.
