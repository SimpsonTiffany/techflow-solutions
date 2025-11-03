# Workflow Analysis

### 1. What triggers this workflow to run?
This workflow is triggered automatically **when changes are pushed to the `main` branch**. It can also be run manually from the GitHub Actions tab if needed. The trigger is defined in the `on:` section of the `deploy.yml` file.

---

### 2. What are the four main steps this workflow performs?
The four main steps are:
1. **Checkout code** – Downloads the latest version of the repository to the runner.
2. **Setup Node or Environment** – Prepares the runtime environment used to test or build the site.
3. **Run validations or checks** – Validates the HTML and checks for any broken links or syntax issues.
4. **Deploy to GitHub Pages** – Publishes the website to GitHub Pages once all tests pass.

---

### 3. What does the “Checkout code” step do and why is it necessary?
The checkout step pulls all the files and code from the repository into the virtual environment where GitHub Actions runs.  
Without it, the workflow wouldn’t have access to the project files to build, test, or deploy them.

---

### 4. What is the purpose of the environment configuration?
The environment configuration ensures the GitHub runner has the right tools, dependencies, and permissions needed to build and deploy the project safely. It creates consistency so that deployments behave the same every time.

---

### 5. How does this automated deployment improve reliability compared to manual deployment?
Automation removes human error. Instead of manually uploading files or forgetting steps, the workflow automatically validates, tests, and deploys the project. This makes deployments faster, more consistent, and less likely to break the site.

---

### 6. What would happen if you pushed code to a different branch (not `main`)?
If code is pushed to another branch (like `feature/about-section` or `feature/profiles`), the workflow would **not run automatically**, since the trigger is only set for `main`. You would need to either merge that branch into `main` or manually trigger the workflow.
“This workflow ensures consistent, automated deployments using GitHub Pages.”