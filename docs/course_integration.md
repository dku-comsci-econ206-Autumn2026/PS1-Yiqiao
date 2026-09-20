# Course integration provenance

The `course-final-v2` integration branch starts from the public course repository's `main` commit `752da53550e118115334e0ef42ed54576952a37f`. It is separate from the final development branch, `v2-information-acquisition` at `43604b35519b7e8d9cab4077f81f65129a72c30c`. No unrelated-history merge, rebase, or history rewrite was used.

## Final paper source

The authoritative paper overlay is `PS1-yl1081-overleaf-source.zip`, prepared from the final development commit. Its 24 entries were inspected before extraction: root `main.tex`, bibliography, ACM class and style, sections, appendices, figures, and field-trip evidence were present; no path traversal, symlink, build file, local absolute path, or credential signature was found.

The ZIP's contents were copied to the integration repository root for course/Overleaf use. The same 24 files are present byte for byte under `paper/`, the development/validation copy used by `scripts/build_paper.sh` and `scripts/validate_paper.py`. The root and `paper/` PDFs compiled with pdfLaTeX/BibTeX to seven pages, with Section 5 ending on page 2; all seven rendered page images were byte identical. Root `figures/` also contains additional documented research figures from the development branch.

## Reproducibility source and preservation

The final development commit supplied only named research paths: `src/`, `notebooks/`, `tests/`, `outputs/`, `scripts/`, `deployment/`, `docs/`, `demo/`, `paper/`, `figures/`, `AI_USE_LOG.md`, `PROJECT_CONTEXT.md`, and `requirements.txt`. Local environments, caches, build products, submission archives, and private review material were not copied.

The course versions of `instructions/`, `companion/`, `scaffolding/`, `acmart.dtx`, and `acmart.ins` remain unchanged. No `.gitattributes` file existed at the fetched course commit; this branch adds a narrow whitespace rule for the two byte-preserved ACM support copies under `paper/`. The final verified `acmart.cls` and `ACM-Reference-Format.bst` from the paper package are used at the root. Existing `.gitignore` rules were retained and extended for the final project's local environments and generated files.

Eight upstream files were intentionally removed because they represented superseded starter paper source or generated output:

- `appendices/supporting.tex` and `sections/proposal.tex`: replaced by the final v2 appendices and five sections.
- `figures/README.md`, `figures/figure_manifest.json`, `figures/ps1_teaser.png`, and `figures/ps1_teaser.svg`: starter figure metadata/previews superseded by the final editable Draw.io source, vector PDF, and documented research figures.
- `main.bbl` and `preview.pdf`: stale compiled starter outputs, not the final v2 paper.

No course instruction, companion, scaffolding, or ACM provenance file was deleted. The public course repository was used read-only; this branch is intended for a normal author-created PR from the personal fork.
