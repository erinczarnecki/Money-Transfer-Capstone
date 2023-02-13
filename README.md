## Money Transfer Capstone
This was a capstone project completed for [Merit America's](https://meritamerica.org/) Fullstack Java Web Developer Bootcamp - A 31-week intensive program focused on Full Stack Web Application Development, including hands-on 
coursework in Java Development, Client-Server Programming (SQL + Spring), and Frontend Development (Classic Web + React).  

Program Capstone Project 2 of 3.  

## Project Description
Peer-to-peer money transfer application allowing users to send, request, and approve money transfers. Front-end is a command-line application communicating with a RESTful API server in the back-end.


## Table of Contents
- [Money Transfer Capstone](#money-transfer-capstone)
- [Project Description](#project-description)
- [Table of Contents](#table-of-contents)
- [Project Requirements](#project-requirements)
- [Running the Application](#running-the-application)
  - [Requirements](#requirements)
  - [Getting Started](#getting-started)
  - [Database Setup](#how-to-set-up-the-database)
  - [Authentication](#authentication)
- [Team Members](#team-members)

---

## Project Requirements
1. Authenticated users need to be able to see Account Balance
2. Authenticated users can send a transfer of a specific amount of TE Bucks to a registered user
   - Can choose from a list of users to send TE Bucks to.
   - Cannot send money to myself.
   - Transfer includes the User IDs of the from and to users and the amount of TE Bucks.
   - The receiver's account balance is increased by the amount of the transfer.
   - The sender's account balance is decreased by the amount of the transfer.
   - Cannot send more TE Bucks than amount in account.
   - Cannot send a zero or negative amount.
   - Sending Transfer has an initial status of Approved.
3. Authenticated users can see Pending transfers
4. Authenticated users can approve or reject a Request Transfer
   - Cannot "Approve" a Request Transfer for more TE Bucks than available in account.
   - Request Transfer status is "Approved" if the user approves or "Rejected" if the user rejects the request.
   - If "Approved", Requester's account is increased by the request amount
   - If "Approved", Sender's account is decreased by the request amount
   - If "Rejected", no account balance changes

## Running the Application

### Requirements
- [JDK 11](https://www.oracle.com/java/technologies/javase/jdk11-archive-downloads.html)
- [Maven](https://maven.apache.org/download.cgi)
- IDE - The program built with [IntelliJ](https://www.jetbrains.com/idea/)
- [PostgreSQL](https://www.postgresql.org/)
- [pgAdmin](https://www.pgadmin.org/download/)

### Getting Started
1. Download code and open with IDE capable of running Java programs
2. Load the Maven file in the root folder
3. To begin the application, run the VendingMachineCLI.java in an IDE.
   - The program requires at least Java 10 to be run. 
   - If running in an IDE, ensure a resource folder is included with all files in the same location they are set in this zip file
4. Set up "tenmo" database

### How to set up the database

Create a new Postgres database called `tenmo`. Run the `database/tenmo.sql` script in pgAdmin to set up the database.

### Authentication

The user registration and authentication functionality for the system has already been implemented. If you review the login code, you'll notice that after successful authentication, an instance of `AuthenticatedUser` is stored in the `currentUser` member variable of `App`. The user's authorization token—meaning JWT—can be accessed from `App` as `currentUser.getToken()`.

When the use cases refer to an "authenticated user", this means a request that includes the token as a header. You can also reference other information about the current user by using the `User` object retrieved from `currentUser.getUser()`.

## Team Members 
- Erin Czarnecki - <a href="https://www.linkedin.com/in/erin-czarnecki" target="_blank">LinkedIn</a> - <a href="https://github.com/erinczarnecki" target="_blank">GitHub</a>
- Mohamed Lamhaouas - <a href="https://www.linkedin.com/in/simohamed-lamhaouas/" target="_blank">LinkedIn</a> - <a href="https://github.com/lamhaouas" target="_blank">GitHub</a>
- Cameron Hunt - <a href="https://www.linkedin.com/in/b-cameron-hunt/" target="_blank">LinkedIn</a>
