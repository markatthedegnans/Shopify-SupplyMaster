# Dropbox + VS Code Configuration Checklist

> **Purpose:** One-time setup to minimize Dropbox sync conflicts that cause VS Code file-write crashes in this workspace.
> **Created:** 2026-06-21
> **Applies to:** All VS Code workspaces stored in Dropbox-synced folders

---

## Pre-Requisites

- [ ] Dropbox desktop app installed and running
- [ ] VS Code installed
- [ ] Target project folder(s) identified

---

## Step 1: Dropbox Folder Settings

### Make Project Folders Available Offline

- [ ] Right-click the project root folder in Windows Explorer
- [ ] Select **Dropbox** → **Smart Sync** → **Local**
  - This ensures all files are physically present on disk (not placeholder files)
- [ ] Repeat for any parent folders that contain the project (e.g., `TP Tech Projects\`, `Shopify\`)

**Verification:**
- [ ] Open the folder in Windows Explorer
- [ ] Confirm no cloud icons appear on files (should show green checkmarks or no overlay)
- [ ] Confirm file sizes are visible and non-zero

---

## Step 2: VS Code Settings (Workspace or User Level)

### Add Dropbox Cache Exclusions

Edit your VS Code `settings.json` (User or Workspace settings):

```json
{
  "files.exclude": {
    "**/.dropbox": true,
    "**/.dropbox.cache": true,
    "**/.dropbox.attrs": true
  },
  "search.exclude": {
    "**/.dropbox": true,
    "**/.dropbox.cache": true,
    "**/.dropbox.attrs": true
  },
  "files.saveConflictResolution": "overwriteFile"
}
```

- [ ] Add the `files.exclude` entries above
- [ ] Add the `search.exclude` entries above
- [ ] Set `files.saveConflictResolution` to `"overwriteFile"`
- [ ] Save `settings.json`
- [ ] Reload VS Code window (`Ctrl+Shift+P` → "Developer: Reload Window")

**Why these settings:**
- Dropbox creates `.dropbox*` metadata files that VS Code can index or conflict with
- `overwriteFile` reduces temp file churn during saves

---

## Step 3: Verify the Configuration

### Test a File Write Operation

- [ ] Open any `.md` file in the project
- [ ] Make a small edit
- [ ] Save the file
- [ ] Confirm no error dialogs appear
- [ ] Confirm the change persists after closing/reopening the file

### Check Sync Status

- [ ] Open Dropbox desktop app
- [ ] Confirm no sync errors or conflicts for the project folder
- [ ] Pause/resume sync once to force a reconciliation (optional stress test)

---

## Step 4: Reference the Permanent Workaround

This workspace uses a documented workaround for all file append operations:

**See:** `PERSISTENT-REQUIREMENTS.md` → "CRITICAL — How to Write to the Observations Log"

- [ ] Confirm you understand: `write_to_file` and `replace_in_file` are avoided
- [ ] All log appends use `execute_command` + PowerShell `Add-Content`
- [ ] This bypasses the VS Code diff editor crash that Dropbox triggers

---

## Maintenance Notes

- Re-run this checklist if:
  - Moving the workspace to a new machine
  - Dropbox updates its Smart Sync behavior
  - VS Code releases a major update that changes save mechanisms
- The `files.saveConflictResolution` setting can be reverted to default (`"askUser"`) if no crashes occur after 30 days of normal use

---

## Quick Reference — One-Line Summary

> **"Local files + exclude Dropbox cache + overwriteFile saves + PowerShell appends = stable Dropbox + VS Code environment."**
