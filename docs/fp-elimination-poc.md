# False-positive elimination PoC

`test by poneglyph, bug bounty attempt`

This same-repository PR verifies that a genuinely read-only reviewer can
trigger a `pull_request_review` workflow that receives a repository secret,
creates a deployment, requests auto-merge, and dispatches a privileged
consumer without satisfying native required-review protection.

Only a SHA-256 hash of the synthetic canary is recorded.
