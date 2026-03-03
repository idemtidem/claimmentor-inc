# Adjuster QA & Training Features

**Requested by:** Farm Bureau (Steve Love)
**Date:** 2026-02-26
**Source:** Demo meeting

## The Ask
Three related capabilities:
1. **QA/Assessment:** Supervisors review recorded statements and provide feedback to adjusters
2. **Training mode:** Use scenarios to train junior adjusters on statement-taking
3. **Real-time coaching:** Guide adjusters through questions during live statements

## The Need
> "Taking statements is a skill. And it's one that's difficult to teach. Some people are just naturals."

Steve (WC Claims Manager) reviews adjuster files to provide feedback. With transcripts, he could:
- Identify questions that should have been asked but weren't
- Evaluate statement-taking technique
- Spot patterns across adjusters (who needs coaching)
- Train junior adjusters with real examples

He gave a vivid example: new adjusters awkwardly leading up to the alcohol/drug question ("I just want to ask you a question, by golly, we ask absolutely everyone this...") vs. experienced adjusters who just ask it directly.

## Context
- Junior adjusters take years to learn proper statement technique
- Head trauma requires completely different questioning than finger laceration
- SIU assists on death claims — lots of detail required
- No current way to systematically review and improve statement quality

## Suggested Implementation

**Phase 1 - QA Dashboard:**
- Supervisor can review any adjuster's statements
- Flag sections for feedback
- Track feedback history per adjuster
- Aggregate metrics (avg statement length, questions asked, etc.)

**Phase 2 - Training Mode:**
- Simulated scenarios (not real claimants)
- Practice statements with AI or recorded scenarios
- Feedback on technique

**Phase 3 - Real-time Coaching:**
- Template of questions appears during statement
- Prompts based on what claimant says (e.g., "They mentioned head trauma — ask about...")
- Checklist of required questions

## Priority Signals
- [x] Multiple customers asked — Common need for claims managers
- [ ] Blocking a deal
- [ ] Causing churn risk
- [ ] Competitive pressure

## Notes
DJ (their mentor/advisor) has been helping think through this. Chuck mentioned it's on the roadmap. This could be a significant differentiator and expansion revenue opportunity (premium feature).
