# Chapter Writing Specification (template + rules, no body prose)

## Template (every chapter; 1-3 lines of guidance each in writer brief)

1. Learning goals — 3-5 bullets, verbs (write/predict/fix), DS-prereq flag if any.
2. Previous chapter connection — 2-3 lines: what is reused, what breaks if skipped.
3. Why this concept exists — problem before solution; 1 concrete pain.
4. Terminology — table: term | read | meaning | misreading. EN kept where standard (dereference, decay...).
5. Syntax — minimal grammar box; one canonical form only.
6. Minimal example — compilable, <15 lines, `main` returns 0, no unexplained constructs.
7. Execution flow — numbered steps mapping code lines to order.
8. Memory model — VISUAL required for: vars/arrays/ptr/strings/stack/struct/heap (addr boxes + arrows).
9. Step-by-step example — 1 worked program, input->trace->output.
10. Common mistakes — table: bad pattern | symptom | cause (include warnings text).
11. Bad code / Why bad / Correct code — side-by-side trio, minimal diff.
12. K&R enhancement points — 1-3 bullets referencing [Kx.y]; purpose-only, no copied code.
13. Modern C notes — box: UB/warning/safety per gap C1-C5; tag [E] if external.
14. Summary — 5-8 bullets mirroring goals.
15. Exercises — mix: concept-check, output-predict, fill-blank, find-bug, fix, write, mini-build.
16. Next chapter bridge — 2 lines: open question the next chapter answers.

## Code rules (from README, binding)

- Compilable; init all pointers; check malloc/fopen; free/close shown; no unexplained globals;
  warnings-clean (`-Wall -Wextra`); beginner-simplified vs production form labeled when both shown.

## Exercise-type quota (per chapter)

- >=1 output-predict, >=1 find/fix-bug, >=1 write-from-scratch. Pointer/memory chapters: +1 draw-memory item.

## VISUAL required list

vars, array layout, `&/*`, ptr arithmetic, `**`, strings/`'\0'`, call stack, struct, heap alloc,
list-node bridge, tree-bridge (preview), file-stream model, TU/compile-link diagram.

## K&R-use rule

- Allowed: section ref, concept label, "example purpose" 1-liner.
- Forbidden: paragraph/code/exercise copy. Quicksort/allocator/dir-list = purpose-ref only.

## Chapter brief header (writer fills per chapter)

`Goal | Prereq secs | K&R refs | Gap IDs | VISUALs | Est. pages | DS-flag`
