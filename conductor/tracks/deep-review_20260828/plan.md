# Implementation Plan: Deep Solution Review & Cold Environment Validation

## Phase 1: Product, Tech, and Scoring Audit
- [ ] Task: Review against GTM Skillathon Rules
  - [ ] Cross-check the solution against `RULES.md` and `AGENTS.md` non-negotiables.
  - [ ] Validate that no facts are invented and that sources/retrieval dates are properly cited.
  - [ ] Ensure the skill stops at a reviewable draft before taking any consequential action.
- [ ] Task: Repository Asset Inspection
  - [ ] Verify `SKILL.md` contains only `name` and `description` in the YAML frontmatter.
  - [ ] Verify `demo/seed-prompt.md` exists, is accurate, and names the input path correctly.
  - [ ] Verify `DEMO.md` and `demo/evals.md` are completely filled and accurately reflect the current state.
  - [ ] Apply immediate fixes for any identified documentation or structural gaps.
- [ ] Task: Phase Verification & Checkpoint (Refer to workflow.md)

## Phase 2: Input Diversity & Test Cases
- [ ] Task: Evaluate Existing Inputs
  - [ ] Review current inputs in `demo/input/examples/` for diversity across product categories and target countries.
  - [ ] Identify any missing edge cases or representation gaps (e.g., highly restricted products vs. unrestricted).
- [ ] Task: Expand Test Suite
  - [ ] Create or update representative inputs to ensure broad, rigorous coverage.
  - [ ] Verify that the fallback output (`demo/output/`) aligns perfectly with the latest script logic.
- [ ] Task: Phase Verification & Checkpoint (Refer to workflow.md)

## Phase 3: Cold Environment Execution
- [ ] Task: Prepare Cold Environment
  - [ ] Create a fresh `/tmp/` directory for the cold clone.
  - [ ] Clone the current local branch into the `/tmp/` directory.
  - [ ] Strip any residual API keys, environment variables, or local configs from the clone to ensure a truly "cold" state.
- [ ] Task: Execute Judged Path
  - [ ] Run the seed prompt command on the diverse inputs within the cold environment.
  - [ ] Verify that execution completes flawlessly and swiftly (well under the 75-second limit).
  - [ ] Verify the output matches expectations without relying on external authenticated APIs or MCP servers.
- [ ] Task: Immediate Remediation
  - [ ] Fix any execution failures, missing dependencies, or pathing issues discovered during the cold run in the primary repository.
- [ ] Task: Phase Verification & Checkpoint (Refer to workflow.md)
