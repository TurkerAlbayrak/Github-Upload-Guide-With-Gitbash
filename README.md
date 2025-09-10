# 🚀 Upload Project/File to GitHub Using Git Bash

A simple step-by-step guide to upload your local project files to **GitHub** using **Git Bash**.  

---

## 📌 Steps

1. **Open your GitHub account** and create a new repository.  
2. **Give a repository name** and (optional) add a description.  
3. **Choose visibility**: Public 🔓 or Private 🔒.  
4. (Optional) Add a `README.md` file.  
5. Click on **"Create Repository"**.  
6. Open **Git Bash** (or terminal).  
7. Navigate to your project folder: `cd projectfolder`  
8. Initialize Git in the project: `git init`  
9. Add files to Git: `git add .`  
10. Commit the changes: `git commit -m "Your commit message"`  
11. Go to your GitHub repository and copy the **HTTPS URL**, e.g.: `https://github.com/username/project.git`  
12. Link local repo with GitHub: `git remote add origin https://github.com/username/project.git`  
13. Push your project to GitHub: `git push origin master`  

---

## ✅ Notes
- Replace `username` and `project` with your actual GitHub username and repository name.  
- If you are using the newer Git version, you might need to use `main` instead of `master`:  
  `git push origin main`  

---

💡 Now your project is live on GitHub! 🎉
