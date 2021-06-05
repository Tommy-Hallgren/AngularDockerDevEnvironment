# AngularDockerDevEnvironment

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 12.0.3.

## Docker
Start the development server run `docker-compose up -d --build`
Inspect the server logs with `docker-compose logs -f dev`

Access the dev server from your browser run `docker-machine ip` and access the given ip at port 4200.
Once the server is running it will poll changes from host and auto reload the page.

Attach the container with
```
docker-compose exec dev sh
```

ssh into container with 
```
docker exec -it dev /bin/sh
```

### Copying node_modules

You should copy the `node_modules` directory from your container after every package addition, to do so run:

```
docker cp dev:/usr/src/app/package-lock.json . && \
docker cp dev:/usr/src/app/node_modules - > temp_node_modules.tar && \
    tar -xf temp_node_modules.tar && \
    rm -f temp_node_modules.tar
```

This process might take some time, but keep in mind you won't run it so often

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.
