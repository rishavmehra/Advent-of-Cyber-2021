# Advent-of-Cyber-2021
  An event providing a new set of security challenges each day starting from December 1st 2021 to December 26th 2021

  Topics that will be in these challenges include: Web Exploitation, Forensics, OSINT, Scripting, Networking, and Reverse Engineering

<h2>Day1</h2><h3>Web Exploitation [Save The Gifts]:</h3> </hr>

<b>Learning Objectives</b>

1. What is an IDOR vulnerability?
2. How do I find and exploit IDOR vulnerabilities?
3. Challenge Walkthrough.

<hr>

## What is an IDOR vulnerability?

IDOR stands for Insecure Direct Object Reference and is a type of access control vulnerability. An access control vulnerability is when an attacker can gain access to information or actions not intended for them. An IDOR vulnerability can occur when a web server receives user-supplied input to retrieve objects (files, data, documents), and too much trust has been placed on that input data, and the web application does not validate whether the user should, in fact, have access to the requested object.

## How do I find and exploit IDOR vulnerabilities?
   
   As previously mentioned, an IDOR vulnerability relies on changing user-supplied data. This user-supplied data can mainly be found in the following three places:

<b>Query Component:</b>

Query component data is passed in the URL when making a request to a website. Take, for instance, the following screenshot of a URL.

                                  https:website.thm/profile?id=23


We can breakdown this URL into the following:

 ###### Protocol: https://

###### Domain: website.thm

###### Page: /profile

###### Query Component: id=23  

<hr>

# Challenge Walkthrough:
   
   
    
* After finding Santa's account, what is their position in the company?
  ***The Boss!***
 
* After finding McStocker's account, what is their position in the company?
 ***Build Manager***
  
 * After finding the account responsible for tampering, what is their position in the company?
   ***Mischief Manager***
    
 * What is the received flag when McSkidy fixes the Inventory Management System?
    ***THM{AOC_IDOR_2B34BHI3}***

# Day2
  ## Elf HR Problems

<b>Learning Objectives</b>


* Understanding the underlying technology of web servers and how the web communicates.
* Understand what cookies are and their purpose.
* Learn how to manipulate and manage cookies for malicious use.

 ## how the web communicates
 
 <img src="https://github.com/rishavmehra/Advent-of-Cyber-2021/blob/main/images/day2.png"  width="500" height="200">
 
 ## Cookies and their purpose
 HTTP is a stateless protocol. When you send requests to a web server, the server cannot distinguish your request from someone else's request.. To solve the stateless problem and identify different users and access levels, the webserver will assign cookies to create and manage a stateful session between client and server.

Cookies are tiny pieces of data (metadata) or information locally stored on your computer that are sent to the server when you make a request.

Cookies can be assigned any name and any value allowing the webserver to store any information it wants. Today we will be focusing on authentication cookies, also known as session cookies. Authentication or session cookies are used to identify you and what access level is attached to your session.

Below is a diagram describing assigning and using a cookie from the initial request to the session request.
<img src="https://github.com/rishavmehra/Advent-of-Cyber-2021/blob/main/images/64c8a1a54a0e08d9e89701307462f24b.png" >

## How to manipulate and manage cookies for malicious use

Cookie manipulation is taking a cookie and modifying it to obtain unintended behavior determined by the web developer. Cookie manipulation is possible because cookies are stored locally on your host system, meaning you have complete control over them and modify them as you please.</br>
          Cookie values may seem random at first; however, they often have an encoded value or meaning behind them that can be decoded to a non-arbitrary value such as a Javascript object.</br>

From an attacker's perspective, you can decode the cookie value to identify the underlying objects. Once you have identified the underlying objects, you can modify them to what you want. To use the cookie, you will need to encode it back to the original encoding and replace the cookie value. Below is an example of a decoded cookie value.</br>

<code>{firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"}</code>

# DAY3
## Christmas Blackout
 ### What is Content Discovery & Why is it Useful?

Before we begin looking for content, let's define what "content" actually is. Content is the assets and inner workings of the application that we are testing. Contents can be files, folders, or pathways that weren't necessarily intended to be accessed by the general public.

For example, you may have a blog, where you post about your tasty treats! You want everyone to view all of your delicious snacks, but you don't want everyone to be able to manage what delicious snacks are up for review - You may hide the administrator panel away from the public!

# Day4 
## Santa's Running Behind 
#### Learning Objectives
1. Understanding authentication and where it is used
2. Understanding what fuzzing is

<b> What is authentication, and where is it Used? </b>

Authentication is the process of verifying a user’s identity, establishing that they are who they say they are. Authentication can be proven using a variety of authentication means, including:

1. A known set of credentials to the server and user such as a username and password
2. Token authentication (these are unique pieces of encrypted text)
3.Biometric authentication (fingerprints, retina data, etc.)

<b> What is Fuzzing</b>
Put simply, fuzzing is an automated means of testing an element of a web application until the application gives a vulnerability or valuable information. When we are fuzzing, we provide information as we would typically when interacting with it, just at a much faster rate. This means that we can use extensive lists known as wordlists to test a web application’s response to various information.

For example, rather than testing a login form for a valid set of credentials one-by-one (which is exceptionally time-consuming), we can use a tool for fuzzing this login form to test hundreds of credentials at a much faster rate and more reliably.


# Day5 
## Pesky Elf Forum
### Learning Objectives
1. What is an XSS vulnerability?
2. What Types of XSS vulnerabilities are there?

<b> What is an XSS vulnerability?</b>

Cross-site scripting (also known as XSS) is a web security vulnerability that allows an attacker to compromise the interactions that users have with a vulnerable application. It allows an attacker to circumvent the same origin policy, which is designed to segregate different websites from each other. Cross-site scripting vulnerabilities normally allow an attacker to masquerade as a victim user, to carry out any actions that the user is able to perform, and to access any of the user's data. If the victim user has privileged access within the application, then the attacker might be able to gain full control over all of the application's functionality and data

<b>What Types of XSS Vulnerability are there</b>

1. Stored
2. Reflected
3. Dom 
4. Blind

***Stored:***<br>
Stored XSS generally occurs when user input is stored on the target server, such as in a database, in a message forum, visitor log, comment field, etc. And then a victim is able to retrieve the stored data from the web application without that data being made safe to render in the browser. With the advent of HTML5, and other browser technologies, we can envision the attack payload being permanently stored in the victim’s browser, such as an HTML5 database, and never being sent to the server at all.<br>

***Reflected:***<br>
Reflected XSS occurs when user input is immediately returned by a web application in an error message, search result, or any other response that includes some or all of the input provided by the user as part of the request, without that data being made safe to render in the browser, and without permanently storing the user provided data. In some cases, the user provided data may never even leave the browser (see DOM Based XSS next)<br>
***DOM:***<br>
DOM Based XSS is a form of XSS where the entire tainted data flow from source to sink takes place in the browser, i.e., the source of the data is in the DOM, the sink is also in the DOM, and the data flow never leaves the browser. For example, the source (where malicious data is read) could be the URL of the page (e.g., document.location.href), or it could be an element of the HTML, and the sink is a sensitive method call that causes the execution of the malicious data (e.g., document.write).”<br>
***Blind:***<br>
Blind XSS vulnerabilities are a variant of persistent XSS vulnerabilities. They occur when the attacker input is saved by the web server and executed as a malicious script in another part of the application or in another application.
