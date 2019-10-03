# Coding Challenge


* [API](https://gitlab.com/AsterYujano/node-api)

* [Scrapper](https://gitlab.com/AsterYujano/scrapper)


## Getting started

```
git clone --recursive git@gitlab.com:AsterYujano/coding-challenge.git
```

> Note the `--recursive` flag permits to clone submodules inside the project.
> 
> This project is divided in 3 services.
> 2 nodejs applications & 1 database.
> The 2 applications have their own repository, they are included into that project thanks to git submodules.

### To launch the database and the API:

```
docker-compose up
```

`ENV` variables are defined in the docker-compose.yml file.

If you want to run the project without docker, please use `.env` file with the correct variables (see `.env.example` as example).

### To start the scrapper, look at the README.ME in the scrapper repository.

## Note

If you need to pull new changes from submodule reposotories, run:

```
git submodule update --recursive --remote
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

## F.A.Q.

### Why 3 "micro-services"?

As the stability of downstream services may not be affected by the stability of the upstream services, the architecture splits in different parts the application.

Even if the scrapper is down or finished to run, the API is still fully available as well as the database.

If in the future the API/database needs to support more requests and to be run in different containers (for load-balancing, etc), it is possible. While the scrapper is untouched.

### Why MongoDB?

No information about scaling or number of requests were provided, so there are no constraints about it.

As I was workin with NodeJS, I thought it could be interesting to try MongoDB database.