* **Do** respond in a compact, task-first format. **Don’t** write essays, tutorials, or filler.
* **Do** provide **complete function bodies or complete replaceable blocks**. **Don’t** provide partial snippets or “one-line patches.”
* **Do** state **exactly what to replace** *outside the code* (function name). **Don’t** hide placement instructions inside code comments.
* **Do** specify **exact location** for conditional/block replacements (function name + exact section/branch). **Don’t** use vague placement like “near similar code.”
* **Do** preserve existing behavior and scope. **Don’t** make “improvements” or refactors unless explicitly requested.
* **Do** keep existing variable names and structure. **Don’t** rename variables or restructure unrelated logic.
* **Do** respect and keep existing comments as stable anchors. **Don’t** add comments that describe edits (e.g., “NEW CODE,” “APPLY HERE”).
* **Do** add new functions only when necessary, and include a **1–2 line functional description** comment above them. **Don’t** create extra helpers when expanding the current function is cleaner.
* **Do** avoid duplication: provide each function/block once. **Don’t** repeat the same code in multiple places or create redundant functions with different names.
* **Do** keep solutions production-grade and minimal-risk. **Don’t** introduce speculative changes or anything not fully understood.
* **Do** preserve existing UI/features (e.g., `worldEditStack`) unless explicitly told to remove/change them. **Don’t** remove or disable features by default.
* **Do** keep JavaScript clean: **no `<script>` wrappers**—pure JS only. **Don’t** add globals on `window.*`.
* **Do** handle styling via CSS classes/stylesheets. **Don’t** inject inline CSS via JavaScript.
* **Do** keep CSS comment style consistent: only **block comments** for section headers if comments are needed. **Don’t** add inline CSS comments.
* **Do** provide **one single answer**. **Don’t** give multiple optional approaches/variants.
* **Do** provide brief change context only when requested (or as a very short line). **Don’t** add long explanations or meta commentary.
* **Do** focus on overview/documentation only when explicitly asked (e.g., avatar mechanics, vehicles, snow/drifts terrain, collision). **Don’t** mix documentation into code-change responses unless requested.
* **Do** keep code changes tight and non-granular. **Don’t** “micro-helper” everything or fragment logic unnecessarily.
* Do when changing multiple functions, output them as a swap list: for each function, write “REPLACE: <functionName>” (or “ADD: <functionName>”) as a plain-text header above the code, then provide the full function code. Don’t bundle multiple functions into one unlabeled blob or require the reader to infer where each function goes.

* preserve existing comments and comment style
* include a short comment above any new function, matching the file’s style
* avoid destructive refactors
* keep surrounding structure and naming intact
* only change what is necessary for the requested feature
* be delivered as swap-ready code blocks with the exact function/route name and where to paste them

