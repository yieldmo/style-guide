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

  1. [Engineering Vision](#vision)
  1. [Review Principles](#principles)
  1. [Review Etiquette](#etiquette)
  1. [Review Flow](#flow)
  1. [Braching Strategy](#branching)
  1. [Commit Message](#commit)

## Engineering Vision
  
  :)

## Review Principles
  
  - **It's about the team**: When giving criticism, nothing is the committer’s fault. If there is a problem in a commit, it’s everyone’s problem in our codebase, and it’s everyone’s responsibility to rectify. 

  - **Focus on the substance**: It could be easy to get caught up with formatting and semantics. However we should try to leave that to automation as much as possible. The focus should be having a solid understanding of the logic to a point that it feels comfortable to contribute to the same piece of code.

  - **Make it a learning opportunity**: We all have something to learn from others, draw value from reading other people's code and collaborating with each other.

## Review Etiquette
  
  - **Criticism**: Code review shouldn't be an opportunity to show technical superiority over other people, it's about iterate on solutions and make each other better.
  
  - **Compliments**: Code review shouldn't be just about finding errors or constructive feedback, it's also a great place to promote good engineering. So do not shy away from giving your teammate a shout-out when you see brilliant thinking.

## Review Flow

  - Each review should be an open and ongoing conversation:
    - The PR is a live conversation happening among developers.
    - For new features or formats, mark it as "WIP" in Gitlab. Such PR may last over the course of sprint(s) and has various check points in the converstion.
    - For bug fix or quick tweaks, create pull request the normal way. Such PR shouldn't contain too many lines of code changes.
  - Continuously push commits to remote:
    - Ask for feedback every a few commits proactively, instead of lump them together in the end.
    - The author should specify: 
      - What to be looked at specifically
      - By what time should be code be reviewed
  - When in doubt, feel free to pair program or schedule quick review sessions.
  - Every commit should be accompanied by message that describes the code change well.
  - For major features, merge production code to feature branch often to ensure backwards compatibility.
  - Every PR should have a main assignee, who would sign off the PR and merge the code in.
  - All code should be well-tested and well-documented during the review process.

## Branching Strategy

  - Formats or major features: `feature/...`, branch off from `dev`
    - You can start sub branches off from the main feature branch: `feature/.../...`
    - Merge sub feature branches to the main `feature/...` branch
    - Eventually merge the main feature branch back to `dev`
  - Bug fixes: `hotfix/...`, branch off from `master` directly
  - A/B tests: `abtest/...`, should NOT be merged to `dev` or `master`

## Commit Messagees

  - Good commit messages matter, it makes `git log` a very powerful tool to get a full picture of what has changed
  - Capitalize the subject line, limit the message to 50 characters, otherwise make it a multi-line commit message
  - Do not end the subject line with a period
  - Use the imperative mood in the subject line, it should always be able to complete the following sentence:
    - If applied, this commit will your *subject line* here
    - For example: *If applied, this commit will update getting started documentation*
  - Reference: http://chris.beams.io/posts/git-commit/


**[⬆ back to top](#table-of-contents)**

# };
