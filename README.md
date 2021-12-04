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



