---
title: "Solving Hugo Module Resolution Issues with Traditional Chinese Content"
date: 2025-01-02T14:30:00+08:00
authors:
  - name: Shin
    link: https://github.com/shin13
    image: https://github.com/shin13.png
categories:
  - Development
tags:
  - Problem Solving
  - Hugo
  - Multilingual
  - Go Modules
  - Traditional Chinese
draft: true
summary: "Debugging Hugo build failures when adding Traditional Chinese content to a multilingual site"
---

## The Problem

### Context
What were you working on when this issue occurred?
- **Project:** shin13.github.io website - adding Traditional Chinese translations
- **Environment:** Hugo v0.133.1, macOS Sonoma, Hextra theme v0.8.2
- **Timeline:** Weekend project, no urgent deadline but wanted to ship the multilingual feature

### Problem Description

```markdown
**Expected Behavior:**
Hugo should build the site successfully with both English and Traditional Chinese content, generating separate language directories.

**Actual Behavior:**
Build process failed when adding zh-tw content, despite en content working perfectly.

**Error Messages:**
```
Error: failed to resolve output format "RSS" from site config
failed to create target directory: mkdir /public/zh-tw: permission denied
ERROR: render of "page" failed: "/layouts/_default/single.html:8:14": 
  execute of template failed: template: _default/single.html:8:14: 
  executing "_default/single.html" at <.Site.Language.Lang>: 
  can't evaluate field Language on type *hugolib.SiteInfo
```
```

### Impact
- **Severity:** Medium - blocked multilingual feature development
- **Blocked:** Couldn't publish Traditional Chinese content for Taiwan audience
- **Time Lost:** 3 hours of weekend debugging time

## Investigation Process

### Initial Hypotheses
1. **Language Configuration Issue:** Syntax error in hugo.yaml language configuration
2. **Theme Compatibility:** Hextra theme might not fully support Traditional Chinese
3. **File Permissions:** macOS permissions blocking directory creation

### Debugging Steps

```markdown
1. **Checked hugo.yaml Configuration**
   - Result: Language config looked correct, similar to working examples
   - Conclusion: Not a basic syntax issue

2. **Tested with Minimal Content**
   - Result: Created simple zh-tw/_index.md - same error
   - Conclusion: Not related to specific content structure

3. **Checked File Permissions**
   - Result: public/ directory had correct permissions
   - Conclusion: Not a filesystem permissions issue

4. **Investigated Hugo Module Cache**
   - Result: Ran `hugo mod clean` and `hugo mod get -u`
   - Conclusion: Module cache corruption was the culprit!
```

### Tools Used
- [x] **Hugo Built-in Debugging:** `hugo server --debug --verbose`
- [x] **File System:** `ls -la` to check permissions
- [x] **Hugo Modules:** `hugo mod verify` and `hugo mod graph`
- [x] **Community:** Hugo Discourse forum and Hextra GitHub issues

## The Solution

### Root Cause
The issue was caused by corrupted Hugo module cache combined with an outdated go.sum file.

```markdown
**Technical Explanation:**
Hugo modules cache contained stale references to an older version of Hextra theme that didn't properly support the multilingual configuration I was using. The new zh-tw language config triggered a code path that relied on newer theme functionality.

**Why It Happened:**
I had previously experimented with different themes and language configurations, leaving behind cached module data that conflicted with the current setup.
```

### Implementation

```bash
# Before (failing commands)
hugo server
# -> Error: failed to resolve output format "RSS"

# Solution steps
# 1. Clean module cache
hugo mod clean

# 2. Update go.mod and go.sum
hugo mod get -u github.com/imfing/hextra

# 3. Verify module integrity
hugo mod verify

# 4. Clean build cache
rm -rf public/ resources/

# 5. Rebuild
hugo server
# -> Success! Both languages now build correctly
```

### Verification
- [x] **English Content:** All existing pages render correctly
- [x] **Traditional Chinese:** New zh-tw pages build and display properly
- [x] **Language Switching:** Navigation between languages works
- [x] **Production Build:** `hugo --minify` succeeds without errors

## Prevention & Best Practices

### What I Learned
- **Technical:** Hugo module cache can become corrupted during development iterations
- **Process:** Always run `hugo mod clean` when encountering mysterious build errors
- **Tools:** `hugo mod verify` is invaluable for debugging module issues

### Prevention Strategies
1. **Better Module Hygiene:** Regular `hugo mod clean` during development
2. **Version Pinning:** Lock theme versions in go.mod for stability
3. **Build Scripts:** Create consistent build/clean scripts for the project

### Code Quality Improvements
```yaml
# Added to hugo.yaml for better debugging
params:
  debug: true  # Enable in development
  
# Pinned theme version in go.mod
module github.com/shin13/shin13.github.io
go 1.23.0
require github.com/imfing/hextra v0.8.2 // pinned version
```

## Resources & References

### Helpful Links
- [Hugo Modules Documentation](https://gohugo.io/hugo-modules/): Essential reading for module troubleshooting
- [Hextra Multilingual Setup](https://imfing.github.io/hextra/docs/guide/multilingual/): Theme-specific language configuration

### Documentation
- **Hugo Discourse:** Found similar issue thread that pointed to module cache problems
- **Hextra GitHub Issues:** Confirmed my language config was correct

### People Who Helped
- Hugo Discourse community provided the key insight about module cache corruption

## Related Issues

### Similar Problems
- Previous Hugo theme switching left behind cached data
- Will watch for similar issues when updating dependencies

### Follow-up Tasks
- [x] **Documentation:** Added troubleshooting section to project README
- [x] **Automation:** Created make clean command that includes module cleanup
- [ ] **Monitoring:** Set up GitHub Actions to test both language builds
- [x] **Team Knowledge:** Will share this pattern with other Hugo users

## Difficulty & Time Investment

**Problem Complexity:** ⭐⭐⭐☆☆ (3/5 stars)
**Time to Solve:** 3 hours total (2 hours debugging + 1 hour verification)
**Could Have Been Faster If:** I had tried module cache cleanup earlier in the process

---

*Tags for future reference: hugo, multilingual, module-cache, build-errors, hextra-theme*

*Update: 2025-01-03 - Confirmed this solution works for other theme updates as well*

*Note for future self: When Hugo build errors seem unrelated to recent changes, suspect module cache first!*
