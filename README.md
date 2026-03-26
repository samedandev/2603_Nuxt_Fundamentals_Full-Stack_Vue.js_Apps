# This git

> https://github.com/samedandev/2603_Nuxt_Fundamentals_Full-Stack_Vue.js_Apps

# Add page

> npx nuxi add page index -> /app/pages/index.vue

# Add Pages to app.vue

> app.vue -> <NuxtPage></NuxtPage>

# Navigation

> app.vue

```
<nav>
      <NuxtLink to="/">Home</NuxtLink>
      <NuxtLink to="/movies">Movies</NuxtLink>
      <NuxtLink to="/Songs">Songs</NuxtLink>
      <NuxtLink to="https://vueschool.io">VueSchool</NuxtLink>
    </nav>
```

## Slugs in URL

> ![slugs](https://github.com/samedandev/2603_Nuxt_Fundamentals_Full-Stack_Vue.js_Apps/blob/main/_printscreens/print02.jpg)

# Reading the Slug Data

> ![reading slugs](https://github.com/samedandev/2603_Nuxt_Fundamentals_Full-Stack_Vue.js_Apps/blob/main/_printscreens/print01.jpg)

## Movie DBB

> app/pages/movies/index.vue -> http://www.omdbapi.com/?apikey=&s=${query.value}

> ![searchimdb](https://github.com/samedandev/2603_Nuxt_Fundamentals_Full-Stack_Vue.js_Apps/blob/main/_printscreens/print03.jpg)
