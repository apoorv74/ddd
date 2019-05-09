
# Dealing with medium to large data

Another common situation that researchers face is in dealing with data that fall somewhere between small (tabular data such as csvs that are in the order of bytes to megabytes to gigabytes that can be easily compressed) to large (what falls under the umbrella of `big data`). The happy medium is generally data that are too big to fit on memory of most standard machines, but can successfully fit on disk (https://ropensci.github.io/arkdb/articles/articles/noapi.html). In this case, users who do not have the support to maintain resource intensive database servers can instead rely on light serverless databases such as MonetDB or SQLite. These databases provide disk based storage and using language agnostic interfaces, a analyst can easily query these data in manageable chunks that don't overrun memory limitations. Using software packages such as arkdb (https://ropensci.github.io/arkdb/index.html) one could easily chunk large data from flat text files to these lite databases without running into memory limitations.

As for making these files available alongside compute, one ingenious but short-term solution is to use the GitHub release feature to attach such large database dumps. GitHub releases are designed to serve software releases and provide the opportunity to attach binary files. This mechanism can also be used to attach arbitrary files such as large data files, binary data, and database dumps as long as each file does not exceed 2gb. The R package `piggyback` allows for uploading and downloading such files to GitHub releases, which would make it easy for anyone to access data files wherever the script is being run. It's worth emphasizing again that this is a short-term solution that is dependent on GitHub maintaining this service.