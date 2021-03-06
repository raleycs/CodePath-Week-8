# Project 8 - Pentesting Live Targets

Time spent: **6** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: SQLi

When going through one of the employee's page, in the URL when you replace salesperson.php?id=#, you can replace # with " 'OR SLEEP(5)=0--' ". This will prompt the website to wait for 5 seconds before loading the first employee on the top of the "Find a Salesperson" page.

Walkthrough: ![](https://github.com/raleycs/CodePath-Week-8/blob/master/sql.gif)

Vulnerability #2: Session Hijacking/Fixation

When logging into the Blue website you can use the session id tool (provided by CodePath) and copy that session id into a different browser on the Red website. Once you use the same tool for the Red website to change the session id of the Blue website, the browser with the Red website is logged in without needing to type any credentials.

Walkthrough: ![](https://github.com/raleycs/CodePath-Week-8/blob/master/sess.gif)

## Green

Vulnerability #1: XSS

A user can go to the "Contact" tab and fill out a form with JavaScript in the "Feedback" section of the form. Once the administrator checks the feedback, the JavaScript gets executed.

Walkthrough: ![](https://github.com/raleycs/CodePath-Week-8/blob/master/xss.gif)

Vulnerability #2: Username Enumeration

In the "Login" tab of the website when the user enters an invalid username the resulting text is unbolded. However, when the user enters a valid username, but with the wrong password the text is bolded.

Walkthrough: ![](https://github.com/raleycs/CodePath-Week-8/blob/master/enum.gif)

## Red

Vulnerability #1: CSRF

A user can enter a malicious link in the feedback section in the "Contact Us" tab. Assuming that some sort of social engineering works and the admin clicks on the link, allowing for CSRF to occur.

Walkthrough: ![](https://github.com/raleycs/CodePath-Week-8/blob/master/CSRF.gif)

Vulnerability #2: IDOR

In the tab that allows you to access all the employees, a user can change the id in the URL to access a page of an employee that he shouldn't have access to. The other websites checked for this by redirecting web traffic whenever a user tries to access a page with an id that they shouldn't be seeing.

Walkthrough: ![](https://github.com/raleycs/CodePath-Week-8/blob/master/IDOR.gif)

## Notes

Describe any challenges encountered while doing the work

Essentially have to check every single possibility (aka takes a lot of time)
