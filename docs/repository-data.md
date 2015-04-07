# Working with Repositories

Repositories are one of the most important elements of the GitHub API.

## Listing repositories

**TODO**

## Creating a repository

**TODO**

## Reading repository commits

You can also explore the list of commits for a repository:

```csharp
var commits = await client.Repository.Commits.GetAll("octokit", "octokit.net");
```

Each commit has a number of details, including the author, committer, files and statistics.

You can pass filters to this query, by using the `CommitRequest` overload:

```csharp
var request = new CommitRequest
{
    Sha = "shiftkey/my-feature-branch",
    Path = "Octokit.Reactive/",
    Author = "shiftkey",
    Since = DateTimeOffSet.Now.Subtract(TimeSpan.FromDays(7)),
    Until = DateTimeOffSet.Now
};

var commits = await client.Repository.Commits.GetAll("octokit", "octokit.net", request);
```
