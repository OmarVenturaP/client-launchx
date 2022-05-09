# Diagrama Funcionalidad "VUE client-launchx - Prisma DataBase"
```mermaid
flowchart TD;
    BAB[vue.config.js]<-->BA{Cliente-LaunchX}
    BA{Cliente-LaunchX}<-->ExplorerServices<-->Router.js;
    http-common.js--class<-->ExplorerServices<-->Router.js
    Router.js<--GET-->E[explorers]<--COMPONENT-->ExplorerList;
    Router.js<--GET-->F[explorer:id]<--COMPONENT-->Explorer;
    Router.js<--POST-->D[add]<--COMPONENT-->AddExplorer;
    YA[localhost:3000 CORS localhost:8081]<--AXIOS-->http-common.js;
    YA[localhost:3000 CORS localhost:8081]<--localhost:8081-->BAB[vue.config.js]
    
    A[DBexplorers_api]<-.-B(PostgreSQL);
    Migration<-->DDD(Create, Modifie, Delete);
    DDD(Create, Modifie, Delete)<--ModelPrisma-->YB[seeds.js]
    YB[seeds.js]-->CCC[server.js];
    AA[DBstudents_api]<-.-B(PostgreSQL)<-->Migration<-->CC{PrismaDataBase}<-->CCC[server.js]<--localhost:3000-->YA[localhost:3000 CORS localhost:8081];
```

# vue-3-crud

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
