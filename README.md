# Advent-of-Cyber-2021
  An event providing a new set of security challenges each day starting from December 1st 2021 to December 26th 2021

  Topics that will be in these challenges include: Web Exploitation, Forensics, OSINT, Scripting, Networking, and Reverse Engineering

<h2>Day1</h2><h3>Web Exploitation [Save The Gifts]:</h3> </hr>

    Learning Objectives

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
