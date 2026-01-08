# Git & GitHub Terminal Lab

Welcome! The goal of today's session is to master the **Git Terminal** workflow. You will first learn how to manage your own project locally and then contribute to a shared repository via a Pull Request.

---

## 0. Authentication: Setting up your Token
GitHub no longer accepts your account password for terminal operations. To upload your code, you must use a **Personal Access Token (PAT)**.

1.  **Generate Token:** Go to your GitHub [Settings](https://github.com/settings/profile) -> **Developer settings** -> **Personal access tokens** -> **Tokens (classic)**.
2.  **Configure:** Click **Generate new token (classic)**. Give it a name (e.g., "Lab Token"), set an expiration, and select the **'repo'** checkbox.
3.  **Save it:** Click **Generate token**. **Copy the code immediately** (you won't see it again).
4.  **Usage:** When the terminal asks for your **Username**, type your GitHub name. When it asks for your **Password**, paste this **Token**.

---

## Exercise 1: Individual Workflow (Local Merge)

In this exercise, you will practice how to work on your own project where you have full control and don't need to ask for permission to merge changes.

### 1. Fork and Clone
First, click the **"Fork"** button at the top right of this page. Once you have your own copy, clone it to your computer (replace `YOUR_USERNAME` with your actual GitHub username):

```bash
git clone https://github.com/YOUR_USERNAME/git-java-lab.git
cd git-java-lab
```

### 2. Create a "Solo" Branch
It is best practice to never work directly on `main`. Create a branch for a new feature:

```bash
git checkout -b my-solo-test
```

### 3. Make a Change
Create a new file called `notes.txt` using the terminal or your preferred text editor:

```bash
echo "Learning git is fun" > notes.txt
```

### 4. Commit and Merge locally
Instead of using the GitHub website, you will merge the change yourself directly in the terminal:

```bash
git add .
```

```bash
git commit -m "Add personal notes file"
```

Move back to main to bring the changes there
```bash
git checkout main
```

Merge the solo branch into main
```bash
git merge my-solo-test
```

### 5. Push to your Cloud
Now that your local `main` is updated, upload it to your GitHub profile:

```bash
git push origin main
```

---

## Exercise 2: Collaborative Workflow (Pull Request)

Now, you will contribute to the **original** repository (the professor's project). Since you don't have direct "Push" access there, you must submit a **Pull Request (PR)**.

### 1. Create a Contribution Branch
Create a new branch named after yourself (e.g., `mikel-idoyaga`):

```bash
git checkout -b your-name-surname
```

### 2. Edit the Code
Open `Participants.java` with any text editor and add your line inside the `main` method:
`greet("Your Name", "your-github-username");`

### 3. Stage and Commit
You must save your changes to the git history:

```bash
git add Participants.java
git commit -m "Add [Your Name] to the participants list"
```

### 4. Push the Branch to GitHub
Upload your specific branch to your fork:

```bash
git push origin your-name-surname
```

### 5. Open the Pull Request
1. Go to **your fork** on the GitHub website.
2. Look for a yellow notification bar that says **"Compare & pull request"** and click it.
3. Ensure the **"base repository"** points to the professor's original project.
4. Click the green **"Create pull request"** button.

---

*Note: Wait for the ✅ or ❌ icon in your PR to see if your Java code passed the automated tests.*
