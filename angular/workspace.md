# Angular : Workspace

## Typical Workspace

```text
application/
├── angular.json
├── package.json
├── tsconfig.json
├── public/
└── src/
    ├── app/
    │   ├── app.config.ts
    │   ├── app.routes.ts
    │   ├── app.ts
    │   ├── app.html
    │   └── app.scss
    ├── index.html
    ├── main.ts
    └── styles.scss
```

## Workspace Commands

```bash
ng generate application admin
ng generate library shared-ui
ng build shared-ui
ng serve application
ng config projects.application.architect.build.options.outputPath dist/application
```

## Configuration

```bash
ng config cli.analytics false
ng config projects.application.prefix app
ng version
```

