## 🔹 Steps to Create a Repository on GitHub

1. **Login to GitHub**

   * Go to [https://github.com](https://github.com)
   * Sign in with your account.

2. **Click on New Repository**

   * On the top-right corner, click the **“+” icon** → select **New repository**.

<img width="955" height="242" alt="image" src="https://github.com/user-attachments/assets/3cb90938-72d8-462b-928d-0ecb6fa13728" />

3. **Enter Repository Details**

   * **Repository name** → e.g., `my-first-repo`.
   * **Description (optional)** → short note about the project.
   * **Visibility** →

     * **Public** (everyone can see)
     * **Private** (only you and invited collaborators can see).

4. **Initialize the Repository (optional but recommended)**

   * Check ✅ **“Add a README file”** (explains the project).
   * Optionally add:

     * **.gitignore file** → tells Git which files not to track (e.g., logs, temporary files).
     * **License** → open-source license (MIT, Apache, etc.).

<img width="434" height="433" alt="image" src="https://github.com/user-attachments/assets/7a3ffb37-5e58-4a3a-8572-3d82b8b5f6c6" />

5. **Click Create Repository** 🚀

   * Your new repository is ready!
   * You’ll see a page with your repo URL (e.g., `https://github.com/username/my-first-repo`).

<img width="956" height="388" alt="image" src="https://github.com/user-attachments/assets/ed9bebc2-e980-48da-9d3b-7638e391586c" />

---

## 🔹 Next Steps (Connecting Local Code)

If you already have code on your computer, you can push it to GitHub:

```bash
# 1. Initialize git (if not already done)
git init

# 2. Add remote GitHub repo
git remote add origin https://github.com/username/my-first-repo.git

# 3. Add all files
git add .

# 4. Commit changes
git commit -m "Initial commit"

# 5. Push code to GitHub
git branch -M main
git push -u origin main
```
