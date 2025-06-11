Selenium IDE Basics
========================================

A small project to apply Selenium IDE concepts and techniques that I have learned so far, including:

- Navigating the Selenium IDE UI and creating tests
- Storing variables
- Control flow (conditional statements and loops)
- Alerts and pop-ups

Notes on my personal findings are stored in Personal Findings.txt

----------------------------------------

## Resources Used

1. [The Internet Heroku App](https://the-internet.herokuapp.com/)

----------------------------------------

## Personal Learnings

### General

- Need to review CSS selectors
- Need to learn XPath

- This project has made me realize that Selenium IDE feels quite clunky and is limited in what and how it can handle different situations


### Specific Scenarios

#### Alerts & Pop-ups
- Selenium IDE's handling of JavaScript alerts is very limited
- Cannot handle browser HTTP authentication prompts
  - Selenium IDE can only interact with elements rendered inside the browser
  - Elements like JavaScript alert and HTTP authentication prompts are part of the browser and therefore at the OS level

#### Looping Through List of Links
- For the list of links on the index page, I originally wanted to use the `for each` command
  - I.e. for each `<li>` in `<div id="content"><ul>`, click on the link
- However, `for each` needs to be used with variable containing a collection, e.g. an array
- Collecting and storing a collection of the `<li>` with the links feels like it might be overcomplicating things
- Used a `while` loop instead with a count of the total number of links

#### Verifying Page Links
When attempting to verify that each link to an example page worked, I used the `assert element present` to verify the title of the page (in an `<h3>`) was present since only the example pages use `<h3>` and the main index page did not. I used the following Target values with the command:

- `xpath=//div[@id='content']/div/h3`
  - Ran into an example page where `<h3>` was not inside a second `<div>` after the first `<div id="content">`

- So then I tried `xpath=//div[@id='content']/h3` to see if it would still cover the `<h3>` inside a second `<div>` inside of `<div id="content">`
  - It did not
  - XPath is exact

- Then I tried `css=h3`
  - Only look for `<h3>` on the page since `<h3>` is only used on the example pages and not the main index page
  - Ran into an issue where some example pages did not have `<h3>`
  - https://the-internet.herokuapp.com/dynamic_controlsand uses `<h4>` instead
    - Looked up to see if `assert element present` supports using an OR operator so I could verify if `<h3>` or `<h4>` was present
      - It does not
  - Then found https://the-internet.herokuapp.com/javascript_error has no headers at all so checking for a header presence would not work

- Tried to use `assert element not present` to assert that `<h1>` is not present on the page since none of the example pages uses `<h1>` and the 404 page for the-internet.herokuapp.com has an `<h1>` with the text, "Not Found"
  - But ended up running into an example page that has a `<h1>`: https://the-internet.herokuapp.com/shadowdom

May revisit this in the future
  - The solutions I came up with above do not verify that the link clicked goes to the correct page
