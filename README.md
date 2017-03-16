# Git Buildkite

Start [Buildkite](https://buildkite.com) builds using [Git](https://git-scm.com) with a clickable link:

![Running a build of MailCatcher](https://cloud.githubusercontent.com/assets/14028/3793323/c2ce4b52-1b93-11e4-9777-3e7b52ef688f.png)

Walks you through first time configuration.

## Installation

Install on macOS using [Homebrew](https://brew.sh/):

```
brew install sj26/git-buildkite/git-buildkite
```

Or just download the git-buildkite script in this repository somewhere into your `$PATH`. It works on Linux, too.

Add a Buildkite [API Access Token](https://buildkite.com/user/api-access-tokens) with:

```
$ git config global buildkite.apikey my-api-key
```

  Or store it more securely in your macOS Keychain, GNOME Keychain, or other secret stores which [Keyring](https://pypi.python.org/pypi/keyring) supports:

```
$ pip install keyring
$ keyring set api.buildkite.com "$USER"
Password: *****
```

## Usage

Start a build on your current branch and commit:

```
$ git buildkite
```

Start a build on another branch and its current commit:

```
$ git buildkite my-branch-name
```

Start a build on another branch at a specific commit:

```
$ git builkdite my-branch-name 87cba321
```

`HEAD` can be used as an alias for the current branch name when you only want to specify a commit:

```
$ git buildkite HEAD 87cba321
```

Any [Git revision](https://git-scm.com/docs/gitrevisions) works as a commit:

```
$ git buildkite HEAD "@{1 week ago}"
```

## To Do

 * Better result parsing and error handling

## License

MIT, see LICENSE.
