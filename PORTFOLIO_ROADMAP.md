# Portfolio development roadmap

Status reviewed: **September 28, 2026**. This is a development plan, not a claim that the remaining work is complete.

[Back to profile](README.md)

## Established foundation

| Project | Completed and inspectable | Evidence |
| --- | --- | --- |
| AI/ML foundations | Six maintained notebooks, preserved originals, project guides, reusable utilities, offline tests and CI | [Verification record](https://github.com/Manahil-Iftikhar/developershub-aiml-internship-tasks-2025/blob/main/docs/VERIFICATION.md) |
| Advanced AI/ML | Five maintained notebooks, reusable components, synthetic-churn evaluation, project guides, offline tests and CI | [Verification record](https://github.com/Manahil-Iftikhar/DevelopersHub-AI-ML-Internship-Assignment-2/blob/main/docs/VERIFICATION.md) |
| YouTube Metadata Explorer | Repaired Django workflow, keyless fictional demo, separate reproducible engagement experiment, web and ML CI | [Verification summary](https://github.com/Manahil-Iftikhar/YoutubeTitlePredictor#verification-at-a-glance) |
| Collaborative Editing System | JWT authentication, owner-only APIs, external signing configuration, disabled database consoles, Java tests and real-service gateway checks | [Architecture and roadmap](https://github.com/Manahil-Iftikhar/collaborative-editing-system/blob/main/docs/ARCHITECTURE.md) |

The profile, project guides, setup instructions, and evidence links now provide the core portfolio presentation. Further changes should add reproducibility, measured results, or useful functionality.

## Next development milestones

These are proposed priorities, with a concrete completion criterion for each.

| Priority | Milestone | What completion means | Prerequisite |
| --- | --- | --- | --- |
| 1 | Verify browser workflows | An automated browser run demonstrates registration/login, document editing, and owner-only version access against the real services; captures failures and checks browser CORS behavior | Local browser automation environment and the existing Java services |
| 2 | Complete one external-data ML case study | Document dataset source, terms and schema; run a baseline and candidate model with a justified split; publish metrics, error analysis and reproduction commands | An appropriate available dataset for a pending heart-disease, housing or stock task |
| 3 | Evaluate one model-backed NLP workflow | Pin model revision and data provenance; run a declared evaluation set; record outputs, failures, runtime and resource use | Compatible model environment, weights and suitable evaluation data |
| 4 | Strengthen Java consistency | Define save/snapshot and revert semantics; test concurrent writes and prevent conflicting version numbers | A documented consistency design |
| 5 | Validate live YouTube search | Run a small, documented integration check with real provider responses and sanitized evidence | An owner-provided API key and available quota |
| 6 | Prepare a deployment candidate | Establish persistent storage, restricted origins, protected service transport, dependency review and deployment checks for the selected application | A chosen deployment target and operational configuration |

Browser verification is distinct from the existing HTTP smoke test. A model-backed run is distinct from offline tests using mocked retrieval or generation. A public deployment is a separate milestone from successful local execution.

## Research directions after the next milestones

- **Churn:** test stability across seeds and study classification thresholds on validation data; label all simulated results as synthetic.
- **YouTube ML:** obtain a larger dataset with observation times and video identifiers before making forecasting claims; retain the current negative result as evidence.
- **Housing:** establish a measured tabular baseline before introducing a paired-image model.
- **BERT and ticket tagging:** publish held-out evaluation and representative errors before claiming classification quality.
- **Document assistant:** measure retrieval relevance and answer grounding, including cases where the system should abstain.
- **Support chatbot:** distinguish pretrained inference from actual fine-tuning and evaluate the intended behavior before expanding its scope.

## Completion standard

For each milestone, record the problem, code change, reproducible commands, observed result and remaining limitations in the relevant project repository. Link a passing check or a measured report where applicable. Preserve the distinction between original 2025 internship submissions and later portfolio improvements.
