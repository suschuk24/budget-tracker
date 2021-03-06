# Budget Tracker

## Description:

![License](https://img.shields.io/badge/License-MIT-blue.svg "License Badge")

Giving users a fast and easy way to track their money is important, but allowing them to access that information at any time is even more important. Having offline functionality is paramount to the success of an application that handles users’ financial information. With that in mind, enter Budget Tracker. A Progressive Web Application that uses a noSQL database and offline persistance to deliver the ultimate end user experience for budgeting on the go. 


# Table of Contents 

- [Repository](#repository)
- [Walkthrough Video](#walkthrough%20video)
- [Screenshots](#screenshots)
- [Service Worker Details](#Service%20Worker%20Details)
- [User Story](#user%20story)
- [Acceptance Criteria](#Acceptance%20criteria)
- [Contributions](#contributing)
- [Tests](#tests)
- [License](#license)
- [Questions](#questions)
- [Technologies Used](#languages)

## Repository: 
- [My Github Profile](https://github.com/suschuk24)

- [This Repository](https://github.com/suschuk24/budget-tracker)

- [Deployed Application](https://budget-tracker-106.herokuapp.com/)


## Screenshots

### Initial Lighthouse Score before refactor
![Initial Lighthouse Score](public/images/initial-lighthouse-score.jpg)

### Final Lighthouse metrics after refactor
![Final Lighthouse Score Overall](public/images/final-lighthouse-score.jpg)

### Final Lighthouse PWA Score
![Final Lighthouse Score PWA](public/images/final-lighthouse-pwa.jpg)

### PWA Screenshot
![PWA Screenshot](public/images/pwa-screenshot.jpg)

## Service Worker Details:
- When caching files for offline functionality, it is important to keep in mind which files to cache, and which to allow not to render for a usable MVP. In a simple application, the developer may be enticed to include all files. However, upon scaling, that can cause unforeseen performance issues. 

- Generally, it is a good idea to prioritize JavaScript files, HTML files and CSS files so that in worse case scenario, the application still functions with a basic user experience. 

* Files Cached for this application:
``` JavaScript
const FILES_TO_CACHE = [
    "./index.html",
    "./css/styles.css",
    "./js/index.js",
    "./js/idb.js"
];
```
In this application, I also used IndexDB for offline persistance, which stores user submissions, and saves them until regaining a stable internet connection. 

- Fetch Post Method Used to send info back to DB
- Note: This is within an ```if()``` statement, that is nested inside of a larger ```onSuccess()``` function. See 
this [IndexDB JS File ](public/js/idb.js) for the full code 
``` JavaScript
fetch('/api/transaction', {
    method: 'POST',
    body: JSON.stringify(getAll.result),
    headers: {
        Accept: 'application/json, text/plain, */*',
        'Content-Type': 'application/json'
    }
```
## User Story: 

* AS AN avid traveler
* I WANT to be able to track my withdrawals and deposits with or without a data/internet connection
* SO THAT my account balance is accurate when I am traveling 

## Acceptance Criteria: 

* GIVEN a budget tracker without an internet connection
* WHEN the user inputs an expense or deposit
* THEN they will receive a notification that they have added an expense or deposit
* WHEN the user reestablishes an internet connection
* THEN the deposits or expenses added while they were offline are added to their transaction history and their totals are updated

## License:
For more information about licenses, please visit:
[License](https://opensource.org/licenses/MIT)

## Contributing:

[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-v2.0%20adopted-ff69b4.svg)](CODE_OF_CONDUCT.md)

Seth Uschuk


## Tests:

Testing completed using InsomniaCore, Optimized using Chrome DevTools and Lighthouse, Checked for typos and bugs


## Technologies Used:

* JavaScript
* Node
* Express
* Mongoose



## Questions:


If you have any questions, please see my GitHub Page, or feel free to reach out by email:

-[GitHub's Guide to a Professional README](https://github.com/coding-boot-camp/potential-enigma/blob/master/readme-guide.md)


- [My Github Profile](https://github.com/suschuk24)

- [This Repository](https://github.com/suschuk24/budget-tracker)

- [My Email](test@gmail.com)
