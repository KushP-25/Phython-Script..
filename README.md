# 🐍 GitHub Repo Audit Script – CircleCI & Last Commit Check

## ✅ Goal

Fetch all repositories under the **Helium10 GitHub organization** and identify:

- 🔁 Whether they have a `.circleci` workflow folder  
- 🕓 Their last commit date  
- 📉 Filter out repos with no commits in the last 12 months  
- 🌐 Output a summary as a **clean HTML table**

---

## 🧠 What I Learned

- How to make authenticated API calls using Python (`requests`)  
- How to paginate GitHub API results  
- Check for `.circleci` folder existence  
- Parse and compare commit dates  
- Format output using `tabulate`  
- Debug issues with empty repos and bad responses  

---

## 🧪 Challenges & Fixes

- **404 error**: Due to typo in org name (`"heluim10"` → `"helium10"`)
- **Pagination**: Solved with loop over `per_page` and `page`
- **Empty Repos**: Handled with safe `if else` logic
- **CircleCI Check**: Used GitHub `/contents/.circleci` API
- **Output**: HTML format using `tabulate`

---
1. Authentication
   ```
   headers = {
    "Authorization": f"token {Github_TOKEN}"
   }
   ```
3. Get All Repos
Paginated API requests to get up to 100 repos per page.

4. Get Last Commit
Checks the most recent commit date for each repo.

5. Check .circleci Folder
Tries accessing /contents/.circleci using the GitHub API.

6. Build Final List
Only keeps repos that:

Had a commit in the last 12 months

Contain a .circleci folder

6. Export as HTML
Formats the list using tabulate and saves it as repo_report.html.
---

