<h1 align="center">GitHub API Client</h1>

> :octocat: [GitHub REST API v3]

# Table of Contents
- [Run Containers:](#run-containers)
- [APIs](#apis)
- [API Usage Examples](#api-usage-examples)
    - [Search](#search)
        - [Repositories](#search-repositories)
        - [Users](#search-users)
        - [Commits](#search-commits)
    - [GitHub Emojis](#github-emojis)
    - [Trending](#trending)
        - [Repositories](#trending-repositories)
        - [Developers](#trending-developers)
- [Tech](#tech)
- [Author](#author)

## Run Containers:
```bash
docker-compose up
# Python Flask - localhost:5064
# Redis - localhost:6379
```

APIs
---
- [api/modules/] 
    - [emojis.py] & [search.py] utilizes [GitHub REST API v3]
    - [trending.py] scrapes data from https://github.com for trending repositories/developers

API Usage Examples
----

## Search

### Repositories <a id="search-repositories"></a>
- [Example 1a](http://localhost:5064/api/search/repositories/stars:>1+forks:>1?sort=stars+forks&order=desc)
- [Example 1b](http://localhost:5064/api/search/repositories/stars:>1+forks:>1?sort=stars+forks&order=desc&refresh=true)

### Users <a id="search-users"></a>
- [Example 2a](http://localhost:5064/api/search/users/lightn?)
- [Example 2b](http://localhost:5064/api/search/users/lightn?refresh=true)

### Commits <a id="search-commits"></a>
- [Example 3a](http://localhost:5064/api/search/commits/test+repo:vuejs/vue)
- [Example 3b](http://localhost:5064/api/search/commits/test+repo:vuejs/vue?refresh=true)

## GitHub Emojis
- [Example 4a](http://localhost:5064/api/emojis)
- [Example 4b](http://localhost:5064/api/emojis?emoji=octocat)

## Trending

### Repositories <a id="trending-repositories"></a>
- [Example 5a](http://localhost:5064/api/trending)
- [Example 5b](http://localhost:5064/api/trending?since=weekly)

### Developers <a id="trending-developers"></a>
- [Example 6a](http://localhost:5064/api/trending?developers=true)
- [Example 6b](http://localhost:5064/api/trending?developers=true&since=monthly)

Tech 
------
* [flask]
* [Mamba]
* [beautifulsoup4]
* [Docker]
* [Docker-Compose]
* [Redis]

Author
--------
* Osarodion Irabor

[flask]: http://flask.pocoo.org/
[GitHub REST API v3]: https://developer.github.com/v3/
[Mamba]: https://pypi.org/project/mamba/
[Docker]: https://docs.docker.com/engine/reference/builder/#usage
[Docker-Compose]: https://docs.docker.com/compose/compose-file/
[beautifulsoup4]: https://pypi.org/project/beautifulsoup4/
[emojis.py]:./api/modules/emojis.py
[search.py]:./api/modules/search.py
[trending.py]:./api/modules/trending.py
[api/modules/]:./api/modules/
[Redis]: https://redis.io/