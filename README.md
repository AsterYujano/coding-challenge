# Coding coding-challenge

## Todo

- [ ] Add doc to change password in Docker-compose

Coding challenge for DevOps position

## Getting started

```
git clone --recursive git@gitlab.com:AsterYujano/coding-challenge.git
```

> Note the `--recursive` flag permits to clone submodules inside the project.
> 
> This project is divided in 3 services.
> 2 nodejs applications & 1 database.
> The 2 applications have their own repository, they are included into that project thanks to git submodules.

```
docker-compose up
```


## Original Challenge

```
Use Puppeteer by Google to build a simple web crawler.

Start a query search on Amazon. Randomly choose from 5 keywords and loop through the
first 3 pages of results. For each of these 3 pages of products, go to the PDP to gather
following information: title, price, # reviews, avg. rating, date first listed on Amazon.
Store the results in your favorite database. Create a simple Node.js application which
retrieves the results from the database, sorts them by product title and outputs them as a
JSON response.

Make sure the application is production-ready and self-documenting. The stability of the
downstream service may not be affected by the stability of the upstream services.
Limit of results on the downstream services must be configurable per environment and
preconfigured to 25.

Please document how we can run it.

Please shortly document your justification of technology / mechanism choice.
```