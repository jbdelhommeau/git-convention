# iAdvize Git Convention

## <a name='TOC'>Table of Contents</a>

  1. [Rules](#rules)
  1. [Branching](#branching)
  1. [Start a feature](#start-feature)
  1. [Commit message](#commit-message)
  1. [Submission guidelines](#submission-guidelines)
  1. [Credits](#credits)

## <a name='rules'>Rules</a>

  - Branche `master` is always production-like and deployable.

  - Rebase during feature development.

  - Explicit (non fast-forward) merge when done.

  - Open a Pull Request as early as possible

Pull Requests are a great way to start a conversation of a feature, so start one as soon as possible - even before you are finished with the code. The team can comment on the feature as it evolves, instead of providing all their feedback at the very end.

## <a name='branching'>Branching</a>

You should always create a new branch when working on a new feature.

  - **master**: Should be exactly the same as production.
  - **develop**: Used as preproduction branch
  - **ABC-XXX-Description**: Feature branches

## <a name='start-feature'>Start a feature</a>

```bash
# Fetch commits from remote
$ git fetch origin

# Create feature branch
$ git checkout -b ABC-XXX-Description origin/develop

# Push your branch early to get feedback
# Use `rebase` if you need to fresh up your branch
# Follow convention for commit message
$ git push -u origin ABC-XXX-Description

# When you're ready, create a pull request following convention
```

## <a name='commit-message'>Commit message conventions</a>

Commit message must be readable and understandable.

### Commit message Format

```php
// Simple
<type>(<scope...>): <Description>

// Simple with issue
<type>(<scope...>): <Description>
#ABC-XXX

// Full description
<type>(<scope...>): <Short description>

<Explain more...>

#ABC-XXX

```

### Type

- **feature**: `feat(ApiController): Add post method for feature A`
    > Should represent a feature commit

- **fix**: `fix(MessageService): fix wrong status code on GET request`
    > Should represent a bug fix

- **style**: `style(ApiController): :lipstick:`
    > Changes that don't affect meaning of the code ony white-space, formatting

- **documentation**: `doc(ApiController, MessageService): add documentation in controller + Reword class description for  Service`
    > Should represent a documentation changes

- **refactor**: `refacto(MessageService): change message generation process`
    > A change for better readablilty (Don't add feature or fix bug)

- **performance**: `perf(UrlGenerator): Replace libA for libB`
    > Should represent a performance improvment

- **test**: `test(MessageService): Implement message service test for GET request`
    > Should represent a test implementation

##### Example

```text
feat(RestApiController): add constraint to email field

Now, each request must provide an email to be correctly executed.
If no email is provide, a 400 status code is returned.

ABC-XXX #closed
```

## <a name='submission-guidelines'>Submission guidelines</a>

- Create a PR (Pull Request) on github
- Use a title like: `ABC-XXX Some awesome description`
- Use a template for PR description:

    ```
        #### What's this PR do?
        > Ticket link [#XXXX](url)

        Little description
        #### PR Dependencies
        #XXX
        #XXX
    ```

## <a name='credits'>Credits</a>

  - http://blogs.atlassian.com/2014/01/simple-git-workflow-simple/
  - https://gist.github.com/jbenet/ee6c9ac48068889b0912
  - https://github.com/blog/1124-how-we-use-pull-requests-to-build-github

