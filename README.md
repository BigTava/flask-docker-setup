# Flask Docker Setup
**Tutorial:** Dockerizing Flask with Postgres, Gunicorn, and Nginx

## Objectives

- configure Flask to run on Docker with Postgres;
- add Nginx and Gunicorn for production environment;
- serve static and user-uploaded media files via Nginx;

## How to use this setup?

### Development

1. Build the images and run the containers:

```
$ docker-compose up -d --build
```

```
$ docker-compose -f docker-compose.prod.yml up -d --build
```

```
$ docker-compose -f docker-compose.prod.yml exec web python manage.py create_db
```

2. Bring down containers

```
docker-compose down -v
```

3. Ensure App is running
   http://localhost:1337

4. Upload Asset
   http://localhost:1337/upload.

5. View Asset
   http://localhost:1337/media/IMAGE_FILE_NAME.

### Production

1. Set up a fully managed database service -- like RDS or Cloud SQL -- rather than managing your own Postgres instance within a container.
2. Use a non-root user for the db and nginx services for security reasons
