# Repository Cleanup Guide

This guide helps you remove build artifacts from Git history that were accidentally committed.

## Quick Cleanup (Recommended)

Run this command to remove all tracked build artifacts:

```bash
# Remove tracked cache files from Git (but not from disk)
git rm --cached -r \
  .gradle/ \
  build/ \
  .idea/ \
  *.bin \
  *.lock \
  *.xml \
  cache.properties \
  deploymentTargetSelector.xml \
  deviceStreaming.xml \
  file-system.probe \
  "download (1)" \
  "executionHistory (5).lock" \
  "executionHistory.bin" \
  "gc (10).properties" \
  "last-build (6).bin" \
  "fileHashes (7).bin" \
  "sha1-checksums (3).bin" \
  buildOutputCleanup.lock

# Commit the removal
git commit -m "Remove IDE and build cache artifacts from tracking"

# Push to remote
git push origin main
```

## For Large File History Cleanup

If you want to completely rewrite history and remove these files:

### Option 1: Using Git Filter-Branch (Simple)
```bash
# Backup first!
git clone --mirror https://github.com/raoviveksingh3-ai/kutira-kone-app.git kutira-kone-app.git

# Remove files from history
cd kutira-kone-app.git
git filter-branch --tree-filter 'rm -f *.bin *.lock *.xml cache.properties deploymentTargetSelector.xml' -- --all

# Cleanup
git reflog expire --expire=now --all
git gc --prune=now --aggressive

# Force push
git push --mirror --force https://github.com/raoviveksingh3-ai/kutira-kone-app.git
```

### Option 2: Using BFG Repo-Cleaner (Faster)
```bash
# Install BFG: https://rtyley.github.io/bfg-repo-cleaner/
bfg --delete-files "*.bin" --delete-files "*.lock" --delete-files "*.xml" .

# Cleanup
git reflog expire --expire=now --all
git gc --prune=now --aggressive
git push --force
```

## ⚠️ Important Notes

- **Backup first**: These operations rewrite Git history
- **Force push**: If working with a team, notify them before force pushing
- **Mirrors**: Use `--mirror` for complete history rewrite

## Verification

After cleanup, verify the repository size:
```bash
git count-objects -v
```

Expected output should show significant reduction in loose objects.
