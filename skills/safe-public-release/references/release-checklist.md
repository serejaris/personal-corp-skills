# Safe Public Release Checklist

Use this checklist for the release dry run. Mark only checks that actually ran or were manually verified.

## Intent and ownership

- [ ] Public artifact and audience are named.
- [ ] Internal owner issue exists.
- [ ] Inventory/review and publish/verify scopes are separated.
- [ ] Release approval owner is known.
- [ ] Maintenance owner is known.
- [ ] Public target repository/registry is exact and unambiguous.

## Inventory

- [ ] `release-manifest.yaml` exists.
- [ ] Every candidate has a stable artifact ID.
- [ ] Source provider/owner is known.
- [ ] Source version/tag/commit/product version is recorded.
- [ ] Complete companion-file bundle is recorded.
- [ ] Runtime state, generated files, logs and user data are classified.
- [ ] Symlinks, submodules, archives and binaries are explicitly inspected.

## Provenance

- [ ] Every allowlisted file has a known source.
- [ ] Owner-authored modifications are described.
- [ ] Public manifest contains no private absolute paths or internal URLs.
- [ ] Unknown-source files are excluded or blocked.
- [ ] Visibility inside a vendor/runtime product is not used as permission evidence.

## Licensing

- [ ] Root license was checked.
- [ ] Per-file and embedded notices were checked.
- [ ] Dependency/asset licenses were checked where distributed.
- [ ] Generated-output/vendor terms were checked.
- [ ] Intended public license is compatible with all allowlisted material.
- [ ] Required notices/attribution are preserved.
- [ ] Unknown/custom/missing licenses are blocked or excluded.

## Security and privacy

- [ ] `.env*`, credentials, tokens, cookies and key material are excluded.
- [ ] Logs, queues, caches, sessions and histories are excluded or separately reviewed.
- [ ] Customer/student/user/employee data is excluded.
- [ ] Private paths, hostnames and private document/repo links are removed.
- [ ] Hidden files were reviewed.
- [ ] Large files were reviewed.
- [ ] Symlink targets were reviewed.
- [ ] Manual secret-pattern scan ran on the staging tree.
- [ ] Manual private-path scan ran on the staging tree.
- [ ] `git diff --check` passed.
- [ ] `gitleaks` result recorded, or unavailability stated.
- [ ] `trufflehog` result recorded, or unavailability stated.
- [ ] Any exposed live secret was rotated and the scans rerun.

## Allowlist and package

- [ ] `allowlist.txt` is derived from reviewed manifest decisions.
- [ ] Package was built into a new clean staging directory.
- [ ] No whole runtime/private directory was copied first.
- [ ] Main files include required references, examples, scripts and notices.
- [ ] Generated files were regenerated when practical.
- [ ] Full staged file list matches the allowlist/manifest.

## Public documentation

- [ ] `README.md` explains purpose and audience.
- [ ] Install/use command is documented.
- [ ] Verification/smoke command is documented.
- [ ] Public license exists.
- [ ] Attribution/notices exist.
- [ ] Security contact exists.
- [ ] Compatibility/version notes exist.
- [ ] Known limitations are stated.
- [ ] Maintenance owner/update policy is stated.

## Approval dry run

- [ ] Release name shown to approver.
- [ ] Exact public target shown.
- [ ] Allowed artifact list/count shown.
- [ ] Blocked/excluded list/count and reasons shown.
- [ ] License summary shown.
- [ ] Checks actually run and their results shown.
- [ ] Fresh-clone verification plan shown.
- [ ] Open risks shown.
- [ ] Explicit approval received for this exact target and artifact set.

## Publication

- [ ] Public repository/registry was created or updated from the clean staging package.
- [ ] Visibility and default branch were verified.
- [ ] Public license and notices are present.
- [ ] Internal issue content/private links were not copied into the public artifact.
- [ ] Publication commit/release identifier was recorded.

## Fresh public verification

- [ ] Fresh directory created.
- [ ] Public URL cloned/read without private authentication.
- [ ] Documented install/discovery/import command passed.
- [ ] Bounded example/test/smoke passed.
- [ ] Private-path scan reran on the fresh clone.
- [ ] Secret scan reran on the fresh clone.
- [ ] Public links and referenced files resolve.
- [ ] Status moved from `PUBLISHED` to `VERIFIED` only after these checks.

## Maintenance

- [ ] Maintenance owner accepted the artifact.
- [ ] Next review date is recorded.
- [ ] Update/version policy is recorded.
- [ ] Blocked/excluded candidates remain documented internally.
- [ ] New lesson/failure mode was added to the playbook or skill.

## Dry-run summary

```text
Release:
Target:
Current status:
Allowed artifacts:
Blocked/excluded artifacts:
License basis:
Security/privacy checks run:
Fresh-clone plan/result:
Maintenance owner:
Open risks:
Approval:
Next gate:
```
