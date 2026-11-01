# GitHub review-gate authorization lab

This repository is an isolated `GreyFogSec` security lab. It reproduces the
authorization shape of a privileged workflow that treats any submitted
`APPROVED` review as authorization.

The vulnerable path intentionally performs only bounded lab operations:

- create a `staging` deployment;
- enable auto-merge while branch protection keeps the PR pending; and
- dispatch a same-repository canary consumer that writes only a SHA-256 hash
  of a synthetic secret to a dedicated evidence branch.

The hardened path requires both live `write`-equivalent repository permission
for the reviewer and an exact match between the reviewed commit and the
current PR head before reaching its sink.

No third-party repository is modified by this lab.
