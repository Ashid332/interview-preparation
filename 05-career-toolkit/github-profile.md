# GitHub Profile Optimization

As an engineering manager, if a candidate includes a GitHub link, I'm going to click it. However, I rarely have time to read hundreds of lines of code. I do a quick 3-minute scan to gauge your engineering maturity, documentation skills, and consistency.

## The Profile Readme

GitHub allows you to create a repository with your username and add a `README.md`. This acts as your developer landing page.
*   Keep it clean. List your primary stack, what you're currently learning, and how to reach you.
*   Avoid overly flashy widgets unless you are applying for a UI/UX-heavy frontend role.

## The "Pinned Repositories" Rule

Your pinned repositories are your highlight reel. Never leave this to the default algorithm.
1.  **Pin 2 to 4 high-quality repositories.** 
2.  **Ensure EVERY pinned repo has an outstanding `README.md`.** I cannot stress this enough. If I see a repo with no instructions on what the project is or how to run it, I assume you don't care about documentation or onboarding other developers.
3.  **Clean up the commit history.** A project with a history of "fix bug", "wip", "asdf" shows a lack of version control discipline. Use semantic commit messages.

## What I Look for in Your Code

If I do dive into a repository, I'm looking for signs of a mature engineer:
*   **Tests:** Do you have automated tests? (Unit, integration). This is a massive green flag.
*   **CI/CD:** Are there GitHub Actions configured for linting or testing?
*   **Architecture:** Is the code organized logically, or is it one massive `app.js` file?
*   **Dependency Management:** Is there a `package.json`, `requirements.txt`, or `go.mod`?

Don't worry about having a perfect streak of green squares on your contribution graph. Quality of contributions matters much more than daily commits to arbitrary files.

---
### 🤖 AI Interview Coach Prompts
*Copy and paste these into your AI assistant to improve your GitHub presence.*

> "Act as a Senior Staff Engineer. I am going to paste the `README.md` from my most important GitHub repository. Critique it brutally. Tell me what is missing, how the structure could be improved, and what would make you trust this project. [Paste README]"

> "I want to create a standout GitHub Profile README. I am a [Role] focused on [Technologies]. Generate a professional, clean Markdown template for my profile README that highlights my skills, current focus, and contact info, without being overly cluttered."
