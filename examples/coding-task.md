# Coding Task Clarification

## User Request

```text
Fix the login problem.
```

## Expected Clarification

```text
I need two quick details before editing:

1. What happens now?
A. Error message or failed request (Recommended): fastest path to the root cause
B. Wrong page/state after login: likely routing or session handling
C. Intermittent failure: likely timing, cache, or backend availability

2. Scope:
A. Minimal fix only (Recommended): lowest regression risk
B. Fix plus tests: better confidence
C. Broader refactor: useful if the login code is already messy
```

## Notes

If the repository contains failing tests or clear logs, inspect those before asking additional questions.
