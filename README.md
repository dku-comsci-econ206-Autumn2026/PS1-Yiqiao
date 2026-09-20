# Who Pays to Know?
Strategic Information Acquisition Before AI Collective Decisions

**Author:** Yiqiao Liu (Mickey)

**Course:** COMSCI/ECON 206 — Computational Microeconomics, Autumn 2026 Session 1

This is the final PS1 v2 research proposal and reproducibility project. The author replaced the earlier attention/interruption topic with a two-agent game of costly information acquisition before a collective AI decision.

## Final paper and source

The **root `main.tex`** is the final ACM paper for course/Overleaf use. Its root `sections/`, `appendices/`, `figures/`, `field_trip/`, bibliography, and ACM support files form the synchronized final paper source. Figure 1 has an editable Draw.io master and vector PDF. The root paper includes five numbered sections, Author Notes, Appendices A–E, the field-trip photographs, AI-use disclosure, Open Science statement, and SDG statement.

`paper/` is a byte-identical development and validation copy of the same 24-file Overleaf package. The project scripts build and validate this copy. At integration finalization, every file from the authoritative Overleaf source ZIP was compared byte for byte with both root and `paper/`; do not edit one copy without synchronizing the other. See `docs/course_integration.md` for the source and preservation audit.

## Research question and verified baseline

When information is costly but collectively valuable, when will decision makers research rather than free-ride, and how might future observed choices compare with the formal benchmark? The behavioral comparison remains untested.

Agents A and B each choose **Research (R)** or **Skip (S)**. If either researches, each receives information value **V**; each researcher privately pays **c**. The baseline is **V = 4, c = 2**.

| Agent A / Agent B | Research | Skip |
| --- | --- | --- |
| **Research** | (2, 2) | (2, 4) |
| **Skip** | (4, 2) | (0, 0) |

The author initially predicted (R,S) and (S,R) as pure Nash equilibria. Independent best-response enumeration and NashPy verified both; the symmetric mixed equilibrium has p(Research) = 0.5. The V = 4 cost sweep checks c = 0 through 5. These are formal-model results, not observations of people or AI agents.

## Public artifacts

- [Final development and reproducibility branch](https://github.com/micL1222/PS1-Yiqiao/tree/v2-information-acquisition)
- [GitHub-backed Colab notebook](https://colab.research.google.com/github/micL1222/PS1-Yiqiao/blob/v2-information-acquisition/notebooks/information_acquisition_baseline.ipynb) (executed locally; hosted Colab runtime not independently checked)
- [Author-uploaded Hugging Face Static Space](https://huggingface.co/spaces/dku-comsci-econ206-2026/who-pays-to-know)
- [Verified scientific artifact commit `b986771d1e79979825cd375c8ed663994bdc67ec`](https://github.com/micL1222/PS1-Yiqiao/commit/b986771d1e79979825cd375c8ed663994bdc67ec)

The final Static Space source is `deployment/huggingface-static/`. Its browser-side game logic is checked against the trusted Python model by `scripts/validate_static_space.py`. `deployment/huggingface/` records an earlier, unsuccessful Gradio deployment preparation.

## Reproducibility and evidence limits

After installing the dependencies described by `requirements.txt` and `demo/requirements.txt` in local `.venv` and `.venv-demo` environments, run:

```bash
./scripts/verify_all.sh
```

This runs the Python tests, notebook, research validator, static-model parity check, citation and claim audits, and local paper checks. The `src/`, `notebooks/`, `tests/`, `outputs/`, `scripts/`, `docs/`, `demo/`, and `deployment/` directories contain the final project's implementation and provenance. Behavioral experiment: not conducted. Human experiment: not conducted. Educational effectiveness has not been evaluated. Final authoritative Overleaf compilation and Canvas submission remain the author's manual steps.

## Course Template Provenance

This project adapts the [COMSCI/ECON 206 PS1 Overleaf starter](https://github.com/sunshineluyao/ps1-overleaf-template). The course `instructions/`, `companion/`, `scaffolding/`, `.gitattributes`, `acmart.dtx`, and `acmart.ins` are retained for provenance and reference. The final paper uses the supplied ACM class and bibliography style. Course and ACM template materials are not claimed as the author's original work.

OpenAI Codex assisted with implementation, drafting, checking, and Static Space source preparation. The author made the research decisions and manually uploaded the final Static Space. See `AI_USE_LOG.md` and Appendix A.1 of the paper for disclosure.
