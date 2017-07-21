# Git Buildkite

Start [Buildkite](https://buildkite.com) builds using [Git](https://git-scm.com) with a clickable link:

<img width="715" alt="git buildkite building buildkite on buildkite" src="https://user-images.githubusercontent.com/14028/28461425-e3fd347a-6e59-11e7-9672-755e0c4a54b5.png">

Walks you through first time configuration.

## Installation

Install on macOS using [Homebrew](https://brew.sh/):

```
brew install sj26/git-buildkite/git-buildkite
```

Or just download the git-buildkite script in this repository somewhere into your `$PATH`. It works on Linux, too.

Add a Buildkite [API Access Token](https://buildkite.com/user/api-access-tokens) with:

```
$ git config --global buildkite.apikey my-api-key
```

Or store it more securely in your [macOS Keychain](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/security.1.html):

```
$ security add-generic-password -s api.buildkite.com -a "$USER" -w
password data for new item:
retype password for new item:
```

Or in GNOME Keychain, or other secret stores which [Keyring](https://pypi.python.org/pypi/keyring) supports:

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

You can automatically open the build in your browser, too:

```
$ git buildkite --browse
```

## To Do

 * Better result parsing and error handling

## License

MIT, see LICENSE.
