# RELEASE Prompt

Do not declare a SAMA release until the release gates are evidenced.

Verify:
- requirements traceability
- architecture consistency
- database integrity
- business-rule tests
- RBAC/authorization
- security review
- regression suite
- performance checks appropriate to the deployment environment
- backup and restore procedure
- reporting/printing where applicable
- documentation
- deployment/rollback readiness

Any unresolved BLOCKER or CRITICAL issue blocks release.

Output a release decision with PASS/FAIL, evidence, unresolved risks and exact next actions.
