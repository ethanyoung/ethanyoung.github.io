---
layout: post
title:  How to Publish .NET Core Nuget to nuget.org
date:   2020-06-09 10:06:18 +1000
published: false
---

## Create a library project

Choose Class Library(.NET Core) as you code.

## Edit project packag properties

Tick "Generate NuGet package on build".

- Packag id
- Package version
- Authors
- Company
- Product
- Description
- Licensing
- Repository URL
- Tags

## Pack project

Either from Visual Studio or CLI.

## Publish to NuGet.org

Upload the `nupkg` file into NuGet.org

Once you upload the package, you cannot delete or update it.

After indexing and validation (usually one hour). The package is available for downlaoding from NuGet.org

## References

[GitHub Repo](https://github.com/ethanyoung/AppLogger)

[Youtube tutorial](https://www.youtube.com/watch?v=bCoVexnomuk)
