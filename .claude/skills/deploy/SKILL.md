---
description: Deploy to Firebase Hosting with pre-flight validation checks
argument-hint: [deploy message (optional)]
---

# Deploy to Firebase

Deploy the PotêncIA Tech website to Firebase Hosting with pre-flight checks.

## Deploy message (optional)
$ARGUMENTS

## Instructions

Follow these steps in order:

### 1. Pre-flight Checks
Run the following validations before deploying:

- **Git status**: Check for uncommitted changes. If there are uncommitted changes, warn the user and ask if they want to commit first or deploy anyway.
- **Branch check**: Verify which branch is active. If not on `main`, warn the user.
- **File integrity**: Verify `public/index.html` exists and is non-empty.
- **Firebase config**: Verify `firebase.json` and `.firebaserc` exist and are valid JSON.
- **HTML validation**: Do a basic check that the HTML has proper opening/closing tags for `<html>`, `<head>`, `<body>`.
- **React check**: Verify the Babel script block exists and contains the App component.
- **Theme check**: Verify both light and dark theme CSS variables are defined.

### 2. Report Pre-flight Results
Present a checklist of all pre-flight checks with pass/fail status. If any critical checks fail, stop and help the user fix issues before deploying.

### 3. Deploy
If all checks pass (or user approves despite warnings):

- If the user provided a deploy message, use: `firebase deploy --only hosting -m "<message>"`
- If no message provided, generate a descriptive message based on recent git commits
- Run the deploy command

### 4. Post-Deploy Verification
After deployment completes:
- Extract the hosting URL from deploy output
- Report the live URLs:
  - https://potencia-74784.web.app
  - https://potencia-74784.firebaseapp.com
- Suggest the user verify the live site

### 5. Summary
Present a deployment summary including:
- Deployment timestamp
- Files deployed
- Hosting URLs
- Any warnings from pre-flight checks
