# ⚔️ Resolving Merge Conflicts in Git

Merge conflicts occur when Git cannot automatically reconcile differences between two branches. This usually happens when changes are made to the same lines in a file or when a file is deleted in one branch but modified in another.

---

## 🛑 When Do Merge Conflicts Happen?

- Merging branches (`git merge`)
- Rebasing (`git rebase`)
- Cherry-picking (`git cherry-pick`)
- Pulling changes (`git pull`)

---

## 📝 How to Identify a Merge Conflict

When a conflict occurs, Git will:

- Pause the operation and mark conflicted files.
- Show conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`) in the affected files.
- List conflicted files in `git status`.

---

## 🛠️ Steps to Resolve a Merge Conflict

1. **Check the conflicted files:**

   ```bash
   git status
   ```

   Files with conflicts will be marked as "unmerged".

2. **Open each conflicted file and look for conflict markers:**

   ```
   <<<<<<< HEAD
   Your changes
   =======
   Incoming changes
   >>>>>>> branch-name
   ```

3. **Edit the file to resolve the conflict:**

   - Decide which changes to keep (yours, theirs, or both).
   - Remove the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).

4. **Mark the conflict as resolved by staging the file:**

   ```
   git add <filename>
   ```

5. **Continue the operation:**

   - For merge:
     ```
     git commit
     ```
   - For rebase:
     ```
     git rebase --continue
     ```

6. **Repeat for all conflicted files.**

---

## 🧰 Example

Suppose you see this in `app.js`:

```
<<<<<<< HEAD
console.log('Hello from main branch');
=======
console.log('Hello from feature branch');
>>>>>>> feature
```

Edit to resolve:

```
console.log('Hello from main branch');
console.log('Hello from feature branch');
```

Or choose one version, then save and stage the file.

---

## 🧹 Abort the Merge or Rebase (if needed)

- Abort a merge:
  ```sh
  git merge --abort
  ```
- Abort a rebase:
  ```
  git rebase --abort
  ```

  

---

## 💡 Tips

- Use a visual merge tool:
  ```
  git mergetool
  ```
- Always communicate with your team when resolving conflicts on shared branches.
- Commit your resolved changes with a clear message.

---

## 📚 Resources

- [Git Docs: Resolving a Merge Conflict](https://git-scm.com/docs/git-merge#_how_conflicts_are_presented)
- [Atlassian: Resolve Merge Conflicts](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts)

---
