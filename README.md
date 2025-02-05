# Italian Verb Conjugation Practice Site

## Project Overview
This is a project that allows users to practice Italian verb conjugations. A word is chosen at random from the database in the relevant tense and then passed to the client. The user can then type their answers into a form and on submission the answers are validated with a script and are compared against the answers held in the object taken from the word database. The script then makes a message appear in the conjugation form informing the user whether their answers are correct or not. When correct answers are given for all conjugations, the user can then click a button to go onto the next verb. This button is disabled until all correct answers are given. 

This project also offers a content management system that can interact with the database so that new verbs can be added/edited/removed easily instead of having to repeatedly add seed data to the database.

This tech stack for this project is C#, ASP.NET MVC, JavaScript, JQuery, Entity Framework Core, MS SQL Server, AutoMapper, HTML and CSS. The project also uses the front-end library Bootstrap. N-Tier Architecture and Repository Design Pattern has been used for separation of concerns and abstraction. 

This site was inspired by a very old and very basically styled site I used years ago when learning noun declinations and verb conjugations with Latin. This site was instrumental for cementing the various declinations and conjugations in my mind through the exercise of typing the various verb and noun forms. I was searching for a similar website that could do the same with Italian and decided to create the site myself as a dual-exercise in the languages C# and Italian!

## Cloning This Project

This project has been built with .NET version 7, so the .NET Software Development Kit will be required to run the project. 

To clone this project, navigate to the folder of your choice via a terminal and then type the following command:

> git clone <span>https://</span>github.com/RoKen1000/ItalianConjugationPractice

Then open the folder using the code editor of your choice.

If using Visual Studio simply run the project as normal by clicking the launch button in the toolbar. If using another code editor, such as Visual Studio Code, you can run the project with the following command:

> dotnet run

## Features

The site uses responsive design for both mobile, tablet and desktop views. An example of this would be the character code reference button for accented characters that appears in the conjugation practice views. Clicking the button creates an offcanvas side bar showing the various character codes required to input accented characters when using a keyboard. This button only appears when using a view width for laptop and desktop views (1025px or greater). Views that are below this width threshold have this button hidden as mobiles and tablets have their own methods of inputting accented characters and do not need to manually input character codes.

When a user gives a correct answer in the conjugation forms, an animation plays to provide visual feedback. If incorrect answers are given then a different animation will play. This is done using CSS keyframe animations. 

## Challenges, Decisions and Lessons Learned
The present perfect (passato prossimo) tense can be irregular when used with the auxiliary verb essere (to be) rather than avere (to have) which most present perfect phrases use. It was a bit of a challenge to work out how to allow these irregular past participle forms when the verb uses essere. I decided to make a custom script that validates input in the client side to allow for any of the alternate correct answers rather than hardcode all of the answers into the PresentPerfect class object. If the retrieved word has a "usesEssere" property then alternate validation logic is used in the script where it allows masculine or feminine forms of the past participle to be correct. 

Due to the similarity of each class model used for each table, I have decided to make a ManagementController that will handle CRUD operations for the whole application rather than creating multiple CRUD controllers for each type of class model.

I learned that shared views can be very useful for importing various using statements that can be used in many different views. This avoids having lots of duplicate code at the top of each file.

## Packages and Frameworks Used

Besides AutoMapper and the required NuGet packages used to make the database work, the only additional package that was installed was Bootstrap Icons for the edit and delete icons in the views where all available verbs in the specified table are shown.
