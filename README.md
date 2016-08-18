# Yieldmo Frond-end Development Style Guide() {

We take pride and demonstrate craftsmanship in our code. This style guide covers coding styles for JavaScript (ES5, ES6 and React.js), CSS, linters, Editor Config. Click to check the details for each:

  - [JavaScript](javascript/)
  - [CSS](css/)
  - [ES6](es6/)
  - [React](react/)
  - [Editor Config](editor-config/)
  - [Linters](linters/)

Below is the detailed documentation for review principles, etiquette, and flow.

## Table of Contents

  1. [Engineering Vision](#engineering-vision)
  1. [Review Principles](#review-principles)
  1. [Review Etiquette](#review-etiquette)
  1. [Review Flow](#review-flow)
  1. [Braching Strategy](#branching-strategy)
  1. [Commit Messages](#commit-messages)

## Engineering Vision
  
  **We strive for collaboration, architecture and quality in the products we build:**

  - In collaboration we value shared understanding, review process throughout and a culture of challenging ideas
  - Architecturally we strive for flexible, componentized and modularity.
  - In quality we value well tested and documented and clearly articulated code.

## Review Principles
  
  - **It's about the team**: When giving criticism, nothing is the committer’s fault. If there is a problem in a commit, it’s everyone’s problem in our codebase, and it’s everyone’s responsibility to rectify. 

  - **Focus on the substance**: It could be easy to get caught up with formatting and semantics. However we should try to leave that to automation as much as possible. The focus should be having a solid understanding of the logic to a point that it feels comfortable to contribute to the same piece of code.

  - **Make it a learning opportunity**: We all have something to learn from each other. Draw value from reading other people's code and collaborating with each other.

## Review Etiquette
  
  - **Criticism**: Code review shouldn't be an opportunity to show technical superiority over other people; it's about iterating on solutions and making each other better.
  
  - **Compliments**: Code review shouldn't be just about finding errors or giving constructive feedback, it's also a great place to promote good engineering. So do not shy away from giving your teammate a shout-out when you see brilliant thinking.

## Review Flow

  - Each review should be an open and ongoing conversation:
    - The PR is a live conversation happening among developers.
    - For new features or formats, mark it as "WIP" in Gitlab. Such a PR may last over the course of a sprint (or sprints) and have various check points in the converstion.
    - For a bug fix or quick tweak, create a pull request the normal way. Such a PR shouldn't contain too many changed lines.
  - Continuously push commits to remote:
    - Ask for feedback every a few commits proactively, or create a sub-PR if necessary, instead of lumping them together in a single review.
    - The author should specify: 
      - What to be looked at specifically
      - By what time should be code be reviewed
  - When in doubt, feel free to pair program or schedule quick review sessions.
  - Every commit should be accompanied by a message that describes the code change well.
  - For major features, merge production code to the feature branch often to ensure backwards compatibility.
  - Every PR should have a main assignee, who would sign off on the PR and notify the author to merge the code in.
  - All code should be well-tested and well-documented during the review process.

## Branching Strategy

  - Formats or major features: `feature/...`, branch off from `dev`
    - You can start sub branches off from the main feature branch: `feature/.../...`
    - Merge sub feature branches to the main `feature/...` branch
    - Eventually merge the main feature branch back to `dev`
  - Prod fixes: `hotfix/...`, branch off from `master` directly
  - Bug fixes: `bugfix/...`, branch off from `dev`
  - A/B tests: `abtest/...`, should NOT be merged to `dev` or `master`

## Commit Messages

  - Good commit messages matter. They make `git log` a very powerful tool to get a full picture of what has changed
  - Capitalize the subject line and limit it to 50 characters. Do not end the subject line with a period
  - For small changes, it's ok to leave the body empty; if the subject exceeds 50 characters, then consider adding a body
  - When a commit merits a bit of explanation and context, it's necessary to write a body
    - Separate the subject from the body with a blank line
    - Use the body to explain what and why vs. how
    - You can leave out details about how a change has been made, which is what comments in code is about
  - Use the imperative mood in the subject line. A commit subject should always be able to complete the following sentence:
    - If applied, this commit will your *subject line* here
    - For example: *If applied, this commit will update getting started documentation*
  - Reference: http://chris.beams.io/posts/git-commit/


**[⬆ back to top](#table-of-contents)**

# };
