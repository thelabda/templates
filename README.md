# Report Templates

![Markdown Linter](https://github.com/bugcrowd/templates/workflows/Markdown%20Linter/badge.svg)

Directory Structure notes:

Script `generate-directories.py` grabs the current latest version of the VRT structure from GitHub and creates any missing directories. Does not remove or rename directories based on items removed from VRT.

Script follows standard entry names and keeps underscores / case as provided by VRT `id` field.

---

## Working with this repo

This repo has 'Protected Master' enabled; which means that only project admins can commit to the master branch, via Pull Requests. All updates need to come via pull request to ensure integrity.

The following is written assuming SSH access is correctly configured.

First, check out the master branch:

`git clone git@github.com:bugcrowd/templates.git ## n.b. using SSH aliases can make this much simpler`

Once you have master on your system, you will need to create a branch for the work you are about to perform:

`git checkout -b <branch-name>` 

Example branch names could be `XXE-templates` `XSS-templates`, something that denotes what the parcel of work is. These should be kept small, preferrably a group of templates and not much more. Commit and push often!

`git commit -am "Comments about what you changed go here"` saves your changes in the *local* git repo. *Always* leave a descriptive commit message.

When you have completed your templates, you can push them to the repo. These will still be their own branch, but when you push the linter will run and validate the markdown against a set of rules. If you followed the example template and didn't deviate much, the templates should pass.

`git push --set-upstream origin <branch-name>` This will create the branch on the origin server (github) and push your changes. This only needs to be done once for the branch, and subsequent pushes for the branch can be performed with `git push`.

Once the linter has run successfully, you can then create a Pull Request (PR)

Select the branch in the GitHub interface. You should see a 'Pull request' button above the code.

Select that button, then fill out some details about what changed for the project admins to review, then click 'Create pull request'.

At that point, you're done! We'll review the PR and merge or reject as appropriate.

---

## Template Structure

Below is an example template. All sections should be updated to include correct information.

```

# Overview
<!--
**Please replace text in each section below**

SQL Injection Vulnerability Report

Resources:

- <https://owasp.org/www-community/attacks/SQL_Injection>
- <https://owasp.org/www-community/attacks/Blind_SQL_Injection>
-->

## Walkthrough & PoC
<!--
Provide a step-by-step walkthrough on how to access the vulnerable injection point, and how to exploit the vulnerability.
Adding a dot-pointed walkthrough with relevant screenshots will speed triage time and result in faster rewards!

Example:

1. Login to in-scope asset at <www.inscope.com/login>
1. Browse to account page
1. Modify ID token to add single quote
1. View error which states 'SQL Syntax Error'
1. Replace ID value with `1' waitfor delay '00:00:10'; `
-->

## Vulnerability Evidence
<!--
Your submission MUST include evidence of the vulnerability and not be theoretical in nature.

For an SQL Injection vulnerability, please include specific NON-PII information discovered in the database, such as Database Version, a listing of database tables, or an injected 'sleep' payload.

You may present your evidence as output from a tool such as SQLMap, unless the program forbids the use of these tools, and it may be in the format of terminal output, screenshots, or video..

**DO NOT ACCESS PII**
-->

## Demonstrated Impact
<!--
Demonstrating access to data other than the database version or database tables is NOT permitted without explicit permission from the program.
**DO NOT ACCESS PII**
--> 

```

