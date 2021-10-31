# coding-challenge

In this repo I designed the opportunity archive page of the Deals as a task to implement using HTML, WindiCSS, Vuejs/Nuxtjs.

## The Layout hierarchy

As shown in the below code snippet, the default layout carries not only The "nuxt" tag, but also has with it a tag created for the left side navigation bar on the website. Such action is beneficial because the bar should be static in the project and should appear in all routes connected to the same layout

```html
<template>
  <div class="flex flex-row">
    <TheNavBar />
    <Nuxt />
  </div>
</template>

<script>
  import TheNavBar from "~/components/TheNavBar.vue";

  export default {
    components: {
      TheNavBar,
    },
  };
</script>
```

## The Pages' hierarchy

There are two pages created for the investment opportunities, one is a generic page that shows all the results from the API and the other is a dynamic page which shows specific results depending on their status (active or coming soon)

## The Components

To have an easy organization, the components are divided into **normal**, **SVGS** and **UI**

The **normal** components are: </br></br>1.**TheNavBar**: The component created to display the left side navigation bar. </br>2. **RecommendationBlock**: The component created as a part of the navigation bar to display an option to recommend primeCROWD. </br>3. **HelpBlock**: The component created as a part of the navigation bar to reveal the contact information of the company if the user needs support. </br>4. **InvOppHeader**: The component created to display the upper header that tells the user which tab he accessed and how many opportunities he found, along with a link for the user's profile, notifications icon and language button. </br>5. **UserInfo**: The component created to act as a link for the user's profile. </br>6. **NotificationButton**: The component used to create a notifications button for the user to see their notifications.
</br>
</br>

The **UI** components are: </br></br>1. **Funding Round**: The component created as a child to the **OppCard** component to show the user what is the opportunity's investment goal. </br>2. **LanguageButton**: The component created to enable the user to change the language </br>3. **NumberOfInvestors**: The component created as a child to the **OppCard** component to show the user how many investors want to invest. </br>4. **OppCard**: The component that is configured to be a card-view component for each opportunity displayed on the webpage. </br>5. **OppStatus**: The component created as a child to the **OppCard** component to show the user the status of the opportunity </br>6. **OppType**: The component created as a child to the **OppCard** component to show the user the type of the opportunity </br>7. **ProgressBar**: The component created as a child to the **OppCard** component to show the user in a fancy way how much money the opportunity collected in percentage. </br>8. **Tabs**: The component created to navigate between opportunities whether to display all opportunities or to display specific ones according to the status.
</br>
</br>

The **SVGS** components are: </br></br>1. **CardLineSVG**: The SVG that is located inside the opportunity card tht splits content for a better organization. </br>2. **CockpitSVG**: The SVG that is located beside the **Cockpit** option in the left side navigation bar. </br>3. **FeeModelSVG**: The SVG that is located beside the **Fee Model** option in the left side navigation bar. </br>4. **FlagSVG**: The SVG that is created for the **LanguageButton** component to display the English language flag. </br>5. **InvOppSVG**: The SVG that is located beside the **Investment Opportunities** option in the left side navigation bar. </br>6. **KnowledgeCenterSVG**: The SVG that is located beside the **Knowledge Center** option in the left side navigation bar. </br>7. **LikeSVG**: The SVG created to show the "Like" symbol in the **RecommendationBlock** component. </br>8. **LineSVG**: The SVG created to show the "Line" splitter in the **TheNavBar** component. </br>9. **MyInvSVG**: The SVG that is located beside the **My Investments** option in the left side navigation bar. </br>10. **NotificationButtonSVG**: The SVG that is created to show the notification icon in the **NotificationButton** component. </br>11. **VenturePoolSVG**: The SVG that is located beside the **Venture Pool** option in the left side navigation bar.

## How data is fetched

In Nuxt to enhance Search Engine Optimization a property called **asyncData** was created to fetch data from the server and pre-render it before even the component loads. in "pages/investment-opportunities/\_status/index.vue" this property was used so that **OppCard**, its child, can take the returned data as props and finally display the cards of the gathered data from the API.

```javascript
asyncData(context, callback) {
    fetch("https://prime-crowd.com/api/mock/rounds")
      .then((res) => res.json())
      .then((res) => {
        callback(null, { res });
      })
      .catch((err) => {
        console.log(err);
      });
  },
```

## How to filter between opportunities

Three tabs are created above the displayed cards (All, Active and Coming Soon). Each tab is a **NuxtLink** that navigates to the page with the new status updated on the **$route.params** that way we have the root of "investment-opportunities" page to display all cards, "investment-opportunities/active" to display only active cards, and "investment-opportunities/coming_soon" to display only coming soon cards.

## Notes

1.  The source code took me 7 hours (30/10/2021 from 9 PM to 4 AM)
2.  This documentation took me an hour and a half (31/10/2021 from 12:30 PM to 2 PM)
3.  I apologize for any delays but It took much more time as this is literally my first time to use Nuxtjs and WindiCSS.

## Hosted link

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, check out the [documentation](https://nuxtjs.org).

## Special Directories

You can create the following extra directories, some of which have special behaviors. Only `pages` is required; you can delete them if you don't want to use their functionality.

### `assets`

The assets directory contains your uncompiled assets such as Stylus or Sass files, images, or fonts.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/assets).

### `components`

The components directory contains your Vue.js components. Components make up the different parts of your page and can be reused and imported into your pages, layouts and even other components.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/components).

### `layouts`

Layouts are a great help when you want to change the look and feel of your Nuxt app, whether you want to include a sidebar or have distinct layouts for mobile and desktop.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/layouts).

### `pages`

This directory contains your application views and routes. Nuxt will read all the `*.vue` files inside this directory and setup Vue Router automatically.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/get-started/routing).

### `plugins`

The plugins directory contains JavaScript plugins that you want to run before instantiating the root Vue.js Application. This is the place to add Vue plugins and to inject functions or constants. Every time you need to use `Vue.use()`, you should create a file in `plugins/` and add its path to plugins in `nuxt.config.js`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/plugins).

### `static`

This directory contains your static files. Each file inside this directory is mapped to `/`.

Example: `/static/robots.txt` is mapped as `/robots.txt`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/static).

### `store`

This directory contains your Vuex store files. Creating a file in this directory automatically activates Vuex.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/store).
