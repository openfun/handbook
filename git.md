# FUN with Git

[Git](https://git-scm.com) is used as a [DVCS](https://en.wikipedia.org/wiki/Distributed_version_control) for every FUN project involving code or documentation. In this chapter, you will find how we use Git on a daily-basis to code and collaborate with the team.

If you are looking for a good introduction to Git, take a look at the [_Git In Practice_](https://github.com/GitInPractice/GitInPractice#readme) book from Mike McQuaid.

## Git conventions

### Commit message

We follow an emoji-driven commit message format adapted from [Angular guidelines](https://github.com/angular/angular/blob/master/CONTRIBUTING.md#-commit-message-guidelines). A typical commit message should look like:

```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

Where **type** must one of the following:

* 👷‍♀ \(_aka_ **build**\): changes that affect the build system or external dependencies \(example scopes: pip, npm, docker\)
* ⛑ \(_aka_ **ci**\): changes to our CI configuration files and scripts \(example scopes: Circle, GitLab\)
* 📝 \(_aka_ **docs**\): documentation only changes
* 😎 \(_aka_ **feat**\): a new feature
* ✌️ \(_aka_ **fix**\): a bug fix
* 👩‍🏭 \(_aka_ **refactor**\): a code change that neither fixes a bug nor adds a feature
* 👩‍🎨 \(_aka_ **style**\): changes that do not affect the meaning of the code \(white-space, formatting, missing semi-colons, etc\)

And the **scope** should point to the django application or stack component that may be affected, _e.g._:

* docker
* apps:core
* plugins:foo

The **subject** contains succinct description of the change:

* use the imperative, present tense: "change" not "changed" nor "changes"
* don't capitalize first letter
* no dot \(.\) at the end

Just as in the subject, use the imperative, present tense for the **body**: "change" not "changed" nor "changes". The body should include the motivation for the change and contrast this with previous behavior.

The **footer** should contain any information about breaking changes and is also the place to reference GitHub/GitLab issues that this commit Closes.

Breaking changes should start with the word `BREAKING CHANGE`: with a space or two newlines. The rest of the commit message is then used for this.

## Git workflow

## Working with GitHub





