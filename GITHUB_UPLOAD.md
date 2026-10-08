# Upload to GitHub (Windows PowerShell)

1. Create a **new, empty** GitHub repository named exactly `ATCPCqN2T4VTrt14`. Do not initialize it with a README.
2. Extract the ZIP and open PowerShell **inside the `ATCPCqN2T4VTrt14` folder**.
3. Run:

```powershell
git init
git add .
git commit -m "Initial bank subscription prediction project"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/ATCPCqN2T4VTrt14.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your GitHub username. If `origin` already exists, use:

```powershell
git remote set-url origin https://github.com/YOUR-USERNAME/ATCPCqN2T4VTrt14.git
```

If Git asks for your identity, configure `git config --global user.name "Your Name"` and `git config --global user.email "you@example.com"`, then commit again.

Check that the repository contains the notebook and README. Upload the CSV only if sharing it is permitted.
