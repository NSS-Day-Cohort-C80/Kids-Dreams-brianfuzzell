# Events and Debugging Assessment

Time to assess how well you have learned to use the debugging tools in Chrome Dev Tools, and writing click event listeners. This application is to show kids with illnesses and the memories the would like to make. Celebrities sign up to help kids make memories.

> 🧨 Make sure you answer the vocabulary and understanding questions at the end of this document before notifying your coaches that you are done with the project

## Event Listeners to Create

1. When the kid name is clicked, it should display their wish.
1. When the celebrity name is clicked, it should display their sport.
1. The pairings list should should contain the pairing in the following format.
    ```html
    {child name} will be making memories with {celebrity name}, a {celebrity sport} star, by {child wish}
    ```

Below is an animation showing how the application should look when complete and how the event listeners should work.

<img src="./images/debugging-events-assessment.gif" width="700px">

## Setup

Your instruction team will provide a link for you to create your assessment repository. Once your repo is created, clone it to your machine.

1. Make sure you are in your `workspace` directory.
1. `git clone {github repo SSH string}`.
1. `cd` into the directory it creates.
1. `code .` to open the project code.
1. Use the `serve` command to start the web server.
1. Open the URL provided in Chrome.

Make sure your Developer Tools are open at all times while working on this project. Use the messages provided in the Console to determine what code needs to be fixed or implemented, and use breakpoints in the Sources tab to step through your code as you debug.

## Vocabulary and Understanding

Before you click the "Complete Assessment" button on the Learning Platform, add your answers below each question and make a commit.

1. When a child is clicked on in the browser, which module contains the code that will execute on that event happening? Can you explain the algorithm of that logic?
   > The Kids.js module. The algorithm of that logic is:
   >1. Listen for a click on the page
   >2. Let's assign the click event's target into a variable, named `itemClicked`
   >3. Let's also assign the `itemClicked`'s browser dataset id to a variable, named `childId`
   When you hear a click...
   >4. If the item clicked has a browser dataset type that matches "child", then loop through each matching "child" type that is in the database children's array.
   >5. If the clicked matching "child" type has a `childId` browser dataset id that is equal to the database child object's id
   >6. Then display a window popup alert that says "The {child}'s wish is {the value listed with the db child's wish property}

2. In the **Pairings** module, why must the `findCelebrityMatch()` function be invoked inside the `for..of` loop that iterates the kids array?
   > The `findCelebrityMatch()` function has the recipe we need to do the work of finding the child's celebrity id with the celebrity's id. This function needs to be invoked inside the `for..of` loop iterating the kids array because we can't add the matching child and celebrity to the `<li>` string until after the `findCelebrityMatch()` function first finds the match.
3. In the **CelebrityList** module, can you describe how the name of the sport that the celebrity plays can be displayed in the window alert text?
   >First, by importing the getCelebrities() structured clone, I have access to a copy of the celebrity array in the database. Secondly, I added data attributes into the `<li>` elements for the list of celebrities, so I can now extract that data when a click occurs. 
   >
   >A user's click on a celebrity's name is an event that triggers a loop looking through the entire celebrities database array. If one of the individual celebrity object's id property value matches the stored dataset id value, then I can display a window alert. The window alert produces text by using string interpolation to include the celebrity's sport value within that displayed text.
4. Can you describe, in detail, the algorithm that is in the `main` module?
   > Import the Pairings function from the Pairings module
   > Import the Celebrities function from the CelebrityList module
   > Import the Kids function from the Kids module
   > In the document, return the first element that includes the CSS id `container`. Assign that to a variable named `mainContainer`.
   > Create a string of HTML that includes headers and different sections for the list of kids, celebrities, and pairings we want to display on the page. Assign this string to the variable named `applicationHTML`.
   > Take that `applicationHTML` string and set it into the page element `mainContainer`, which I declared earlier. 
