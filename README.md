# coding-challenge

In this repo I designed the opportunity archive page of the Deals as a task to implement using HTML, WindiCSS, Vuejs/Nuxtjs.

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

[Click here for the hosted link](https://coding-challenge-heroku.herokuapp.com/)
