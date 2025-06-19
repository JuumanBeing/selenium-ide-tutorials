Selenium IDE Tutorials
========================================

Learning Selenium IDE with online tutorials.

The purpose of this project is to learn QA automation concepts without code so that I can focus on fundamentals rather than get caught up with syntax. This is not meant to in-depth learning as Selenium IDE, the record and play tool, is not industry standard and not a highly sought skill from employers.

### Folders
**Notes**: Notes I took while studying concepts.

**Project**: A small project I undertook to practise the basics.

**Tutorials**: Tutorial instructions and files.

----------------------------------------

## Resources Used

1. Selenium Tutorial for Beginners by [Simplilearn](https://www.simplilearn.com/tutorials/selenium-tutorial)
  - Up to and including Lesson 2.
  - Switched tutorials because this wasn't quite what I was looking for.

2. Selenium Tutorial by [Tutorialspoint](https://www.tutorialspoint.com/selenium/index.htm)
  - Overall, tutorials were pretty mediocre. Lots of technical errors (with some things not even working at all), missing information, unclear explanations, and repetition.
  - Ended up making some tweaks in the tutorial instructions in my own notes for clarity and to fix mistakes from the original source.

----------------------------------------

## Personal Learnings and Next Steps

- Selenium IDE feels very clunky and sometimes buggy
- Feels very limited in what it can do (e.g. handling JS alerts and other elements outside the DOM and no test management)

- Will need do more in-depth learning for element locating strategies and when to use them
- Depending on what is being asserted, test scripts can be brittle
  - Need to assert something that is stable (doesn't constantly change) and unique
- For dynamic content, some pattern matching strategies that can be used are globbing and regular expressions
- Test scripts need to consider load times and states otherwise tests can be flaky (produce inconsistent results)
  - Wait for states before asserting/verifying
- Need to learn best practices for writing automation scripts
  - What to actually automate
  - When and how often to wait
  - How many verification points to include in a script
  - etc.
