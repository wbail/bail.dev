---
layout: post
title: "semantic_commits"
date: "2021-03-13 7:31:00"
category: blog
---

# Introduction
The specification of conventional appointments is a simple and broad convention used for the writing of commits messages. It offers a set of rules that make it easier to understand what to do.


# Because
Each commit in the repository concerns a fact that happened in the application. For this reason the act of committing is important to know about the past and the future of the application. Maintaining a standard for the team helps in organizing the team and prioritizing the next steps by the PO (Oroduct Owner), Tech Lead or whoever is performing this task. Maintaining a standard helps in creating tools to automate tasks, for example when creating an application CHANGELOG.

# How
Bearing in mind that the team must follow a standard, there is the Conventional Commits, an international standard used by several repositories such as: Angular, Jenkins and Electron.

Below is the logic and details of how to follow the pattern.

## Structure

```
<type> ([optional scope]): <description>

<body>

[optional footer (s)]
```

## Types
* *build*: Changes that affect the build system or affect external dependencies (Ex: npm, gulp)

* *ci*: Changes to CI configuration files and scripts (Ex: TravisCI, Jenkins)

* *docs*: Documentation changes only

* *feat*: New features

* *fix*: Bug fixes

* *perf*: Changes in code that increase performance

* *refactor*: Changes to the code that are not bug fixes or new features

* *style*: Changes that do not affect the code itself (Ex: whitespace, formatting)

* *test*: Add or correct tests

## Scope
The scope can be added to inform which application layer this commit concerns.

Scope examples:

* *service*
* *common*
* *upgrade*
* *core*
* *forms*
* *app*

## Description
The Description contains a succinct message, following the pattern below:

Use of verbs in the *present tense imperative*. Ex: "change" and not "changed or" changes "

The first letter in *lowercase*

Do not use a period (.) At the end of the sentence

## Body
As in the *Description*, use of imperative language in the present: "change" and not "changed or" changes ".

*The body must include what and why and not how.*

## Baseboard
The footer should contain information about Breaking Changes, add the reference to the ticket / issue that this commit is referencing.

If it is a Breaking Change, the line must begin with ```BREAKING CHANGE :```, the message must begin with a space or a line break.

```
BREAKING CHANGE: lorem ipsum
```

OR

```
BREAKING CHANGE:

lorem ipsum
```

# Template
A solution to always keep the pattern to be followed is to create a file called *.gitmessage* with the contents of the subsection *Structure* in the same directory as the projects, on windows the default directory can be found below:

* ```C:\Users\%userprofile%\source\repos\``` (copy and paste in windows explorer)

# Example

* Example # 1 - Use of type, description, body and footer.

```
feat: database rollback

implement the database rollback in the service layer
using the default Microsoft's solution, the 
TransactionScope

Refs #1337
```

* Example # 2 - Use of scope and footer with Breaking Change

```
fix(service): request validation 

the field 'xpto' doesn't allow special characters
for any requests

BREAKING CHANGE: all requests will pass by the validation 
and will impact the clients
```

# References

https://www.conventionalcommits.org/

https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#-commit-message-guidelines

https://chris.beams.io/posts/git-commit/