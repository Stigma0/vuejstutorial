## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```
Understanding the Code

    main.js: This file creates a new Vue instance and mounts the app to the DOM. It's the entry point of the Vue application.

    App.vue: This is the main component of the application. It serves as the root container for the Vue app.

    TaskComponent.vue: This file defines a reusable Vue component for individual tasks. It showcases how to define a Vue component and handle data and events.

Features

    Task Display: The TaskComponent.vue displays individual tasks.
    Reactivity: Demonstrates Vue's reactive data binding. Changes in the application's state are automatically reflected in the UI.