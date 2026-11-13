# Agent instructions


## Modern Web Guidance — mandatory for relevant web work

Use [Google Chrome Modern Web Guidance](https://github.com/GoogleChrome/modern-web-guidance) as the source of current web-platform implementation guidance. This requirement applies to every coding agent working in this repository, including agents that do not have a dedicated plugin integration.

### When to use it
Before designing or changing browser-facing UI or client-side behavior, including HTML, CSS, DOM, browser APIs, responsive layout, animation, forms and validation, accessibility, performance/Core Web Vitals, web security, dates/time zones, and web components:
1. Search the relevant capability first:
   `npx -y modern-web-guidance@latest search "<focused 2–5 word action-oriented query>"`
2. Retrieve the best matching guide ID(s):
   `npx -y modern-web-guidance@latest retrieve "<guide-id>"`
3. Read and apply the relevant implementation rules, compatibility notes, and fallback requirements before coding.
4. Verify the changed implementation against the retrieved guidance and the repository's own acceptance criteria.

On Windows, use `npx.cmd` where required. If the environment blocks network access, request the necessary permission before execution. Do not claim the guidance was consulted if the commands did not run.

### Scope and guardrails
- Search first; never invent guide IDs or rely on remembered guide content. If the first search is weak, rephrase once; if no relevant guide exists, proceed without applying unrelated guidance.
- Follow the guide's browser-support and progressive-enhancement rules. Use required fallbacks for features that are not Baseline Widely available unless this project has an explicit browser-support policy.
- Do not adopt Origin Trial, volatile, or experimental features without explicit user approval.
- Adapt vanilla HTML/CSS/JS guidance to the repository's framework and architecture; do not add dependencies or refactor unrelated code merely to follow a guide.
- This is not required for backend-only work, SQL/ORM/API routes, Python/Go processing, GIS/data pipelines, CI/CD, Docker, Git operations, or trivial tooling/docs changes unless they affect browser-facing behavior.
- Preserve all existing repository instructions, specifications, security constraints, tests, and delivery gates. Modern Web Guidance supplements them; it does not override them.
- In the delivery response, include a concise **Modern Web Guidance** note naming the guide IDs actually retrieved and the material decisions they informed. If searched but no guide applied, say so briefly.
