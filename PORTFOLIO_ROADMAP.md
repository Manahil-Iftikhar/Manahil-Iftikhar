# Portfolio development roadmap

Status reviewed: **September 29, 2026**. This is a development plan, not a claim that the remaining work is complete.

[Back to profile](README.md)

## Established foundation

| Project | Completed and inspectable | Evidence |
| --- | --- | --- |
| AI/ML foundations | Six maintained notebooks, preserved originals, a measured UCI Cleveland case study, reusable utilities, offline tests and CI | [Verification record](https://github.com/Manahil-Iftikhar/developershub-aiml-internship-tasks-2025/blob/main/docs/VERIFICATION.md) |
| Advanced AI/ML | Five maintained notebooks, reusable components, five-seed synthetic-churn evaluation, reproducible lexical retrieval evidence, real-model ticket-tagging diagnostics, project guides, offline tests and CI | [Verification record](https://github.com/Manahil-Iftikhar/DevelopersHub-AI-ML-Internship-Assignment-2/blob/main/docs/VERIFICATION.md) |
| YouTube Metadata Explorer | Repaired Django workflow, keyless fictional demo, separate reproducible engagement experiment, web and ML CI | [Verification summary](https://github.com/Manahil-Iftikhar/YoutubeTitlePredictor#verification-at-a-glance) |
| Collaborative Editing System | JWT authentication, owner-only APIs, external signing configuration, disabled database consoles, guarded snapshot numbers, optimistic document revisions, transactional change history, and real-service HTTP/Chromium checks | [Architecture and roadmap](https://github.com/Manahil-Iftikhar/collaborative-editing-system/blob/main/docs/ARCHITECTURE.md) |

The profile, project guides, setup instructions, and evidence links now provide the core portfolio presentation. Further changes should add reproducibility, measured results, or useful functionality.

## Completed milestone: Chromium editor workflow

[Pull request #9](https://github.com/Manahil-Iftikhar/collaborative-editing-system/pull/9) added an automated Chromium flow and repaired document visibility mapping and asynchronous event handling. [CI run 36468441375](https://github.com/Manahil-Iftikhar/collaborative-editing-system/actions/runs/36468441375) passed registration/login, private document creation, save/reload, snapshot creation/loading, and cross-account denial against the real services. Browser requests exercise CORS across local origins; screenshots and traces are retained by CI for 14 days.

This completes the initial browser milestone for one desktop Chromium workflow. Other browsers, exhaustive UI behavior, accessibility and concurrent editing remain outside this coverage. See [reproduction instructions and limits](https://github.com/Manahil-Iftikhar/collaborative-editing-system/blob/main/docs/BROWSER_TESTING.md).

## Completed milestone: external-data classification case study

[Foundations pull request #2](https://github.com/Manahil-Iftikhar/developershub-aiml-internship-tasks-2025/pull/2) adds a separately sourced UCI Cleveland experiment with attribution, a hash-verified download, validated label/category conversion, and reproducible notebook/CLI workflows. Validation-based selection chose logistic regression; the 61-row test partition produced ROC-AUC 0.9578 versus 0.5000 for the baseline, with two false negatives and six false positives.

[The case study](https://github.com/Manahil-Iftikhar/developershub-aiml-internship-tasks-2025/blob/main/docs/projects/03-heart-disease.md) links full metrics and held-out predictions. All 13 local offline tests and [hosted CI](https://github.com/Manahil-Iftikhar/developershub-aiml-internship-tasks-2025/actions/runs/36469803224) passed; the maintained notebook executed locally. The original internship dataset and scores remain separate. This completes the initial external-data milestone, not external-site or clinical validation.

## Completed milestone: model-backed NLP diagnostic evaluation

[Advanced portfolio pull request #2](https://github.com/Manahil-Iftikhar/DevelopersHub-AI-ML-Internship-Assignment-2/pull/2) adds a real CPU evaluation of a pinned FLAN-T5-small revision on 15 declared synthetic tickets. Both unchanged prompt modes matched **3 of 15** reference answers, equal to a constant-label baseline. Zero-shot returned Login Problem for every ticket; few-shot also failed to improve exact match.

[The case study](https://github.com/Manahil-Iftikhar/DevelopersHub-AI-ML-Internship-Assignment-2/blob/main/docs/projects/05-ticket-tagging.md) publishes every raw response, reference labels, model revision, data hash, package versions and runtime. All 19 offline tests and [hosted CI](https://github.com/Manahil-Iftikhar/DevelopersHub-AI-ML-Internship-Assignment-2/actions/runs/36501003791) passed. CI tests the utilities; the real inference was a separate local run.

This completes the evaluation milestone, not a tagging-quality target. The small synthetic sample, project-defined labels and mismatch between the reference policy and existing few-shot examples limit interpretation. A larger independently labelled set and a consistent label policy are needed before assessing a revised classifier.

## Completed milestone: targeted write-conflict protection

[Pull request #10](https://github.com/Manahil-Iftikhar/collaborative-editing-system/pull/10) prevents duplicate snapshot numbers with a database constraint and returns HTTP 409 for conflicting writes. [Pull request #11](https://github.com/Manahil-Iftikhar/collaborative-editing-system/pull/11) requires the document revision on saves, rejects stale updates, and commits document content and change history in one transaction. The browser keeps an unsaved draft visible when a save conflicts.

At source commit `deb291a092d10e51d9d5660698304e9ac96a930a`, [Java checks](https://github.com/Manahil-Iftikhar/collaborative-editing-system/actions/runs/36548713215) and [real-service HTTP/Chromium checks](https://github.com/Manahil-Iftikhar/collaborative-editing-system/actions/runs/36548713206) passed. The project now has 72 declared Java tests. Focused H2 tests force competing transactions and verify a single winning write without extra history or contribution records; HTTP checks verify revision preconditions, and Chromium checks verify draft preservation.

This completes the targeted consistency milestone. Document saves and snapshots remain separate operations; snapshot revert does not update current document content. Automatic text merging, cross-service atomicity, production-database behavior and load capacity remain outside the verified scope. See the [architecture](https://github.com/Manahil-Iftikhar/collaborative-editing-system/blob/main/docs/ARCHITECTURE.md) and [API recovery instructions](https://github.com/Manahil-Iftikhar/collaborative-editing-system/blob/main/docs/API.md#document-revision-precondition).

## Completed milestone: retrieval baseline and evidence verification

[PR #3](https://github.com/Manahil-Iftikhar/DevelopersHub-AI-ML-Internship-Assignment-2/pull/3) adds an authored six-document, 12-question TF-IDF diagnostic. The correct source ranks first for all eight answerable questions, but three of four unanswerable questions still receive context. [PR #4](https://github.com/Manahil-Iftikhar/DevelopersHub-AI-ML-Internship-Assignment-2/pull/4) makes CI reproduce the corpus hash, settings, rankings, scores and metrics without overwriting the report. The [case study](https://github.com/Manahil-Iftikhar/DevelopersHub-AI-ML-Internship-Assignment-2/blob/main/docs/projects/04-context-assistant.md#recorded-offline-retrieval-baseline) includes every retrieved passage and the limits of this small diagnostic.

This completes the lexical baseline and reproducibility check. It does not execute MiniLM, FAISS or answer generation; an independent evaluation set and model-backed comparison remain future work.

## Completed milestone: churn sensitivity across seeds

[PR #5](https://github.com/Manahil-Iftikhar/DevelopersHub-AI-ML-Internship-Assignment-2/pull/5) repeats the unchanged workflow with five predeclared split-and-estimator seeds on one fixed synthetic dataset. Mean test ROC-AUC is **0.7352** (sample standard deviation **0.0114**), with range **0.7186–0.7492**. Validation selects logistic regression four times and random forest once. All 7,045 exported test predictions were checked against the reported metrics.

The [case study](https://github.com/Manahil-Iftikhar/DevelopersHub-AI-ML-Internship-Assignment-2/blob/main/docs/projects/02-churn-pipeline.md#five-seed-sensitivity-study--2026-09-29) publishes the protocol, individual results and reproduction command. [Hosted checks](https://github.com/Manahil-Iftikhar/DevelopersHub-AI-ML-Internship-Assignment-2/actions/runs/36613595908) passed with 25 offline tests and retrieval-report verification; the five training runs were a separate local experiment. Overlapping holdouts are correlated, and sample standard deviation is not a confidence interval or evidence of real-customer performance.

## Next development milestones

These are proposed priorities, with a concrete completion criterion for each.

| Priority | Milestone | What completion means | Prerequisite |
| --- | --- | --- | --- |
| 1 | Validate live YouTube search | Run a small, documented integration check with real provider responses and sanitized evidence | An owner-provided API key and available quota |
| 2 | Prepare a deployment candidate | Establish persistent storage, restricted origins, protected service transport, dependency review and deployment checks for the selected application | A chosen deployment target and operational configuration |

Browser verification is distinct from the existing HTTP smoke test. A model-backed run is distinct from offline tests using mocked retrieval or generation. A public deployment is a separate milestone from successful local execution.

## Research directions after the next milestones

- **Churn:** extend the completed seed study to new data-generation assumptions and study classification thresholds on separate validation data; label all simulated results as synthetic.
- **YouTube ML:** obtain a larger dataset with observation times and video identifiers before making forecasting claims; retain the current negative result as evidence.
- **Housing:** establish a measured tabular baseline before introducing a paired-image model.
- **BERT:** publish held-out evaluation and representative errors before claiming classification quality.
- **Ticket tagging:** agree on a consistent label policy and collect an independent evaluation set before revising the classifier; retain the current negative result.
- **Document assistant:** compare the embedding retriever against the published lexical baseline on an independent labelled set; evaluate answer grounding and abstention separately.
- **Support chatbot:** distinguish pretrained inference from actual fine-tuning and evaluate the intended behavior before expanding its scope.

## Completion standard

For each milestone, record the problem, code change, reproducible commands, observed result and remaining limitations in the relevant project repository. Link a passing check or a measured report where applicable. Preserve the distinction between original 2025 internship submissions and later portfolio improvements.
