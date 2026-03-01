# Git Integration Strategies: Merge vs. Rebase vs. Squash

This repository serves as a practical guide and record of my workflow for managing feature branches and integrating code into a main branch.

---

## The Development Workflow

In a distributed version control system, we follow a structured path to ensure code quality and stability:

1.  **Branching:** Based on new requirements, a **Feature Branch** is created to isolate development.
2.  **Incremental Steps:** Changes are moved to the **Staging Area** (`git add`) and recorded with unique commit IDs (`git commit -m "Description"`).
3.  **Integration:** Once requirements are met, a **Pull Request (PR)** is initiated to bring the code into the `main` or target branch.

### Pull Request (PR) Requirements
Before a merge can occur, the following steps are typically completed:
* **Remote Access:** User logs into the remote console (GitHub/Bitbucket).
* **Target Selection:** Explicitly define the branch (e.g., `main`) to receive the code.
* **Documentation:** Describe the new features and changes within the PR description.
* **Peer Review:** Team members review the code and provide approval.
* **Finalization:** The PR creator or a maintainer executes the merge.

---

## 🛠 Integration Strategies

I have practiced three primary methods for merging code, each with distinct impacts on the project history:

### 1. Standard Merge
The most common strategy that preserves the complete history of the feature branch.
* **Mechanism:** Creates a new **Merge Commit** that points to two parents (the feature branch head and the target branch head).
* **Structure:** Maintains a "chain" or "diamond" structure.
* **Best For:** Projects where seeing the full context of a feature's development is critical.

### 2. Git Rebase
Rebasing is the process of moving or combining a sequence of commits to a new base commit.
* **Mechanism:** Re-applies the changes from the feature branch on top of the latest commit on `main`.
* **History:** It **rewrites history** with new commit IDs. It hides the "messy" intermediate history and provides a **linear timeline**.
* **Best For:** Small groups or individual developers who want a clean, straight-line project history.

### 3. Squash and Merge
This method condenses all commits from a feature branch into a single, unified commit on the target branch.
* **Mechanism:** Groups all finished work and rebases it into one commit ID.
* **Benefits:** Prevents "polluting" the main branch with dozens of tiny commit IDs (like "fixed typo" or "temp save").
* **Best For:** Short sprint cycles, microservices, and fast-paced environments where only the final result matters for the long-term log.

---

## Practice Examples in this Repo

| Feature Branch | Strategy Used | Result |
| :--- | :--- | :--- |
| `feature-1` | **Merge** | Preserved the chain structure with a dedicated merge commit. |
| `rebase-branch` | **Rebase** | Achieved a linear history; updated API for remote stock inventory. |
| `sprint-squash` | **Squash** | Combined multiple incremental steps into one clean commit for the main branch. |

> **Note:** While Rebasing creates a cleaner history, it should be used cautiously on public/shared branches as it changes existing commit IDs.