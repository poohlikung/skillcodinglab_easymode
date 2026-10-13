---
name: sorawit-coding-en
description: Write or modify code with a required student identity header, no additional explanatory comments, and a systematic workflow backed by real testing. Use for coding tasks, not general questions that require no code.
---

# Systematic Coding and Real Testing

Apply these requirements when creating or modifying code, including code examples in responses and test files. Select either the Thai or English skill, not both; their requirements are equivalent.

## File Headers and Comments

- Add the following text as a header comment exactly once in every source file created or modified:

  `สรวิชญ์ วันเสน รหัสนักศึกษา 673380064-8 sec.1`

- Use valid comment syntax for the language, for example:

  Python / shell:

  ```python
  # สรวิชญ์ วันเสน รหัสนักศึกษา 673380064-8 sec.1
  ```

  JavaScript / TypeScript / Java / C / C++ / C#:

  ```javascript
  // สรวิชญ์ วันเสน รหัสนักศึกษา 673380064-8 sec.1
  ```

  HTML:

  ```html
  <!-- สรวิชญ์ วันเสน รหัสนักศึกษา 673380064-8 sec.1 -->
  ```

  CSS:

  ```css
  /* สรวิชญ์ วันเสน รหัสนักศึกษา 673380064-8 sec.1 */
  ```

- Place the header on the earliest line allowed by the language. Preserve the correct order of any required shebang, encoding declaration, or first-line directive, then place the header immediately after the required material.
- Preserve the text, name, student ID, and `sec.1` character for character. Do not translate the identity or duplicate an existing header.
- Do not add explanatory comments, inline comments, section comments, TODO comments, or docstrings used as code explanations. Apart from the required header, use meaningful names and readable structure instead.
- Explain usage and reasoning in the response or separate documentation outside the code.
- When modifying existing files, do not remove existing comments or legal notices unrelated to the task. Preserve operational comments required by tooling and add only the prescribed header.
- Do not modify generated, vendor, or third-party files just to add a header. If generated code needs a change, update its source according to the project's generation workflow.
- If a format does not support comments, such as JSON, do not insert invalid syntax or fabricate data fields as substitutes. Report the header exception in the delivery summary.

## Workflow

1. Read the request, project instructions, relevant code, and existing testing workflow before making changes. Identify the intended outcome, scope, and acceptance criteria.
2. Make a short plan with verifiable increments. Identify the files or components to change and how to verify them; do not expand into unrelated work.
3. For bugs, reproduce the issue or establish a failing regression test before fixing it where feasible. For features, define expected behavior and test cases before implementation.
4. Implement incrementally using project conventions and tooling. Keep changes focused and check headers and comment restrictions in every touched source file.
5. Execute real tests using available tools. Inspect actual results and exit codes, fix the causes of failures, and rerun relevant checks until they pass or a genuine blocker prevents further verification.
6. Review the diff for out-of-scope changes, mistakes, and secrets before delivery, then report only verified results.

## Testing Standards

- Use the project's existing test framework and commands; do not replace its testing setup unnecessarily.
- Choose tests according to changed behavior and risk: relevant normal cases, boundary values, invalid input, and error handling. Include regression coverage for fixed bugs.
- Use integration tests when contracts between components change and end-to-end tests or actual flow checks when important user journeys change. Not every task requires every testing level.
- Run relevant existing formatter checks, lint, type checks, and builds, along with existing test suites at risk of regression.
- Test required behavior and outcomes, not copies of the implementation or header text instead of program correctness.
- Mock only necessary boundaries, such as external services, and clearly state that a mocked result does not verify the real service. Never substitute fabricated data or invented execution results for real testing.
- Do not disable, skip, delete, or weaken tests merely to make them pass. Distinguish pre-existing project failures from failures introduced by the current changes.
- If dependencies, credentials, or a runtime prevent testing, state what is missing and what remains unverified. Do not claim a pass or complete verification without evidence.

## Delivery Summary

Be concise: state what changed, the commands actually executed and their pass/fail results, any header exceptions, and limitations or untested behavior. When no limitations exist, include only useful information instead of a long checklist. Do not claim test counts or coverage unless actually measured.
