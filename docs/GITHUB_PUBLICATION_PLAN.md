## Confirmed publication and preparation verification ? October 18

The owner subsequently instructed public visibility. After a clean full-history audit of 7 commits / 117 objects / 87 blobs, safe preparation commit 597695330ed353a7ceb847650cb43af773c4321a was pushed and verified against GitHub main. The repository was changed to PUBLIC via GitHub CLI. Anonymous unauthenticated GitHub API and web-page requests both returned HTTP 200; API reports private=false and the same main SHA. Existing five personal-author-email commits remain; no history rewrite/force push occurred.

All 54 lightweight files / 71 relative links passed the local checks; three original raster checksums/sizes remain unchanged. No imagery, secret, application code or heavy dependencies were added. Two milestones/five planning issues exist. Current docs remain preparation only and CONDITIONALLY_READY remains unchanged. A final documentation receipt commit follows; its SHA and independent verification are stored outside Git in E:/TerraScope_AI/00_Project_Management/handoff/last_verified_commit.txt and publication_receipt.json.

Remaining blockers: official Ahmedabad start/reuse ruling, actual roster/registration confirmation, dated event/reference evidence, October28 full requirements and November13 guides. No organizer was contacted. The public visibility instruction does not authorize competition implementation.

# GitHub publication and history privacy plan

2026-10-18 baseline: private main at caeee8bf4ebffeae712c902fa703182dc4f0eb3a. Existing Apache-2.0, NOTICE and attribution retained. Five original commits carry a personal author/committer email; values are intentionally not repeated. Future commits use a GitHub noreply identity. No visibility/history change is authorized.

| Option | Consequences | Approval needed |
|---|---|---|
| Keep private (recommended now) | Preserves history, references and collaborators' clones; limits public disclosure but does not erase email | Already requested |
| Publish unchanged | Personal historical email becomes public and can be copied/indexed; later deletion cannot guarantee removal | Explicit informed owner approval after fresh audit |
| Rewrite identifying metadata then publish | New hashes for affected commits and descendants; old references, reviews and clones may become inconsistent; remote caches/forks may retain old objects | Separate explicit rewrite/force-push authorization, collaborator coordination, backups and re-audit, then visibility approval |
| New sanitized publication history/repository | Preserves private research history separately but loses original public ancestry and creates continuity/URL trade-offs | Explicit owner decision; no automatic replacement |

Before any authorized remediation: inventory branches/tags, PRs/issues/releases and collaborators; preserve a private backup on E:; agree scope; document old/new reference mapping privately; coordinate clone reset/reclone; verify licensing attribution survives; rescan all reachable objects. History editing must never be used to disguise pre-event work. No remediation command is executed by this plan.

Publication checklist: owner controls all original content; contributor/license consent; no copied guides/code/data with unreviewed terms; honest preparation label; full-history and staged/tree secret/data checks; no personal email exposure without approval; current remote hash verified; explicit visibility confirmation. A scanner cannot guarantee detection of encoded/unknown secrets.

See [publication audit](PUBLICATION_AUDIT.md), [workflow](GITHUB_WORKFLOW.md), [third-party notices](../THIRD_PARTY_NOTICES.md). Detailed local audit results remain outside Git; no credential values or private email are in this plan.

## Superseding owner instruction ? October 18

After the preparation/privacy review, the owner explicitly requested public visibility. Preserve existing history, including the five personal-author-email commits; do not rewrite or force-push. Earlier private-only instructions in this document describe the prior state and are superseded for this publication action. Complete the fresh object scan, push safe documentation, change visibility and verify anonymously. The final verified visibility/commit receipt is recorded in the external handoff directory; never assume success from this plan alone. Competition implementation remains gated and unbuilt.
