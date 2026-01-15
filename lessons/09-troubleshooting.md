# 🔧 Troubleshooting: When Things Break

Things will break. That's normal. This section helps you fix the most common issues without panicking.

---

## The Mindset

**When something breaks:**
1. Don't panic
2. Read the error message
3. Ask Cursor to fix it
4. If that doesn't work, ask the community

**Most errors are simple fixes. You just need to know where to look.**

---

## Common Firebase Issues

### "Firebase is not defined"

**What it means:** Your Firebase SDK isn't loaded or configured correctly.

**How to fix:**
1. Make sure you've included the Firebase SDK in your HTML
2. Check that your Firebase config is correct
3. Ask Cursor: "I'm getting 'Firebase is not defined' error. Check my Firebase configuration and make sure it's set up correctly."

### "Permission denied" in Firestore

**What it means:** Your security rules are blocking the operation.

**How to fix:**
1. Go to Firebase Console → Firestore Database → Rules
2. For development, you can temporarily use:
   ```
   rules_version = '2';
   service cloud.firestore {
     match /databases/{database}/documents {
       match /{document=**} {
         allow read, write: if request.auth != null;
       }
     }
   }
   ```
3. **Warning:** This allows any logged-in user to read/write everything. Fine for learning, not for production.

**Ask Cursor:** "I'm getting permission denied errors. Help me set up basic Firestore security rules for development."

### Authentication not working

**What it means:** Auth might not be enabled or configured correctly.

**How to fix:**
1. Go to Firebase Console → Authentication → Sign-in method
2. Enable "Email/Password"
3. Make sure your auth code matches your Firebase config
4. Check the browser console for specific error messages

**Ask Cursor:** "My Firebase authentication isn't working. Check my auth code and help me debug it."

---

## Common Cursor Issues

### Cursor generates code that doesn't work

**What it means:** The prompt wasn't specific enough, or Cursor made an assumption.

**How to fix:**
1. Be more specific in your prompt
2. Show Cursor the error message
3. Ask: "This code isn't working. Here's the error: [error]. Fix it."
4. Provide context about what you're trying to do

**Example:**
❌ "Fix this"
✅ "This Firebase auth code isn't working. The error says 'auth/operation-not-allowed'. I'm trying to let users sign up with email and password. Fix it."

### Cursor doesn't understand my project

**What it means:** Cursor needs more context about your codebase.

**How to fix:**
1. Make sure you've opened the entire project folder in Cursor
2. Reference specific files in your prompts
3. Show Cursor related code: "Here's my auth code [code]. Now I want to add a logout button. Make it work with this existing code."

---

## Common GitHub Issues

### "Repository not found"

**What it means:** GitHub can't find your repo, or you're not authenticated.

**How to fix:**
1. Make sure you're logged into GitHub
2. Check that the repo name is correct
3. Verify you have access to the repo
4. Try cloning it fresh: `git clone [repo-url]`

### "Changes not showing up"

**What it means:** You haven't committed and pushed your changes.

**How to fix:**
1. Commit your changes: `git add .` then `git commit -m "Your message"`
2. Push to GitHub: `git push`
3. Refresh GitHub in your browser

**Ask Cursor:** "Help me commit and push my changes to GitHub. Walk me through the git commands."

---

## Common Deployment Issues

### Build errors when deploying

**What it means:** Your code has errors, or the build process is failing.

**How to fix:**
1. Test your app locally first
2. Check the Firebase deployment logs for specific errors
3. Fix the errors locally
4. Try deploying again

**Ask Cursor:** "I'm getting build errors when deploying to Firebase. Here's the error: [error]. Help me fix it."

### App works locally but not when deployed

**What it means:** Environment variables or paths might be wrong.

**How to fix:**
1. Check that your Firebase config is correct
2. Make sure all file paths are relative (not absolute)
3. Check the browser console on the deployed site for errors
4. Verify your Firebase project settings match your code

**Ask Cursor:** "My app works locally but breaks when deployed. Help me debug the differences between local and deployed environments."

---

## The "It Just Doesn't Work" Problem

**When nothing seems to work:**

1. **Take a break** — Sometimes stepping away helps
2. **Simplify** — Strip it down to the absolute basics
3. **Start fresh** — Sometimes starting over is faster than debugging
4. **Ask for help** — In the [Skool community](https://www.skool.com/vibe-coding-with-chris-7196)

**Remember:** Every builder hits this. It's normal. You're not broken. The code is.

---

## How to Ask for Help

**When asking for help (in the community or to Cursor), include:**

1. **What you're trying to do** — The goal
2. **What you expected to happen** — Expected behavior
3. **What actually happened** — Actual behavior
4. **The error message** — Copy/paste the exact error
5. **What you've tried** — Steps you've already taken

**Example:**
"I'm trying to let users save notes to Firestore. I expected the note to save when they click submit. Instead, I get an error: 'Permission denied'. I've checked that auth is enabled and the user is logged in. What am I missing?"

**Good questions get good answers. Be specific.**

---

## The Debugging Mindset

**When something breaks:**

1. **Read the error** — It usually tells you what's wrong
2. **Check the console** — Browser dev tools show errors
3. **Simplify** — Remove features until it works, then add them back
4. **Use Cursor** — Ask it to debug: "Debug this code. Here's the error: [error]"
5. **Ask the community** — Someone has probably hit this before

**Most bugs are simple. You just need to find them.**

---

## 🎯 Quick Reference: Common Fixes

| Problem | Quick Fix |
|---------|-----------|
| Firebase not defined | Check Firebase SDK is loaded |
| Permission denied | Update Firestore security rules |
| Auth not working | Enable Email/Password in Firebase Console |
| Cursor code doesn't work | Be more specific in your prompt |
| GitHub repo not found | Check you're logged in and repo exists |
| Build errors | Test locally first, fix errors, then deploy |
| Works locally, breaks deployed | Check environment variables and paths |

---

**Remember:** Breaking things is how you learn. Every error is a lesson.

**Next:** Keep building. Keep breaking. Keep fixing. That's vibe coding.

---

*Stuck? Join the [Vibe Coding with Chris Skool community](https://www.skool.com/vibe-coding-with-chris-7196) for help and support.*


