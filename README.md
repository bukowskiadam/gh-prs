# gh prs

This is a gh cli extension that has two features:
- lists all open pull requests from a given list of people
- lists all open pull requests that you have to review or already reviewed

## Install

```
gh extension install bukowskiadam/gh-prs
```

or when using gh with GH enterprise use the full repo url:

```
gh extension install https://github.com/bukowskiadam/gh-prs
```

## Usage

### List PRs from a list of users

```
gh prs user1 user2
```

### List PRs for you to review

Use `-r|--review` flag instead of the list of users

By default it lists all PRs from last 7 days. You can set your own time span
with the optional flag parameter. It'll be blindly passed to the system's `date`
command.

For Linux: `date -d $param`
For MacOS: `date -v $param`

```
gh prs -r|--review [date param]
```

Examples:
```bash
# Default -7 days
gh prs -r

# Linux specific
gh prs -r "-30 days"
gh prs --review "-1 year"

# MacOS specific
gh prs -r -30d
gh prs --review -1y
```
