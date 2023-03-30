
## Start project

* Start drupal and mysql

```
docker compose up -d 
```

* Create `.env.local` file inside `nextjs/` folder:

```
# See https://next-drupal.org/docs/environment-variables
NEXT_PUBLIC_DRUPAL_BASE_URL="http://localhost:8080"
NEXT_IMAGE_DOMAIN=localhost

# Required for On-demand Revalidation
DRUPAL_REVALIDATE_SECRET=secret
```

* Start nextjs

```
cd nextjs/
npm install
npm run dev
```

* Go to [http://localhost:8080](http://localhost:8080) to open drupal

```
Username: admin
Password: password
```

* Go to [http://localhost:3000](http://localhost:3000) to open NextJS site


---


## Setup project

What was done to setup this project:

* Start containers 

```
docker compose up -d
```

* Create drupal website


```
docker compose exec drupal composer create-project drupal/recommended-project .
```

* Open [http://localhost:8080](http://localhost:8080) and setup database

```
Database name: drupal
Username: drupal
Password: password
Host: mysql
```

* Install drupal nextjs module

> Follow instructions starting here: https://next-drupal.org/learn/quick-start/install-drupal

> Remember to prefix every composer command with `docker compose exec drupal composer ...`
