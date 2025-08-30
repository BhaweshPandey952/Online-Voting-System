## Decentralized Voting System using Ethereum Blockchain

## Overview
This project is a secure and transparent Decentralized Application (DApp) built to conduct modern elections. By leveraging the power of the Ethereum blockchain, the system ensures that every vote is an immutable and auditable transaction. This eliminates the need for trusted intermediaries, preventing fraud and creating a truly transparent voting process.

The application features a hybrid architecture, combining a traditional web server for user authentication with a decentralized backend for the core voting logic, offering both efficiency and security.

## Architecture Overview
The system is designed with a separation of concerns, using the best tool for each task:

Centralized Authentication (Python + MySQL): A fast and reliable Python FastAPI server handles user login. It verifies credentials against a MySQL database and issues a JSON Web Token (JWT) to authenticate the session.

Web Server & Authorization (Node.js): A Node.js Express server serves the frontend application and acts as a gateway, verifying the JWT before granting access to the voting or admin pages.

Decentralized Voting (Solidity + Ethereum): The core of the application is a Solidity smart contract deployed on the Ethereum blockchain. This contract manages candidate registration, enforces voting rules (like preventing double-voting), and securely records every vote on the public ledger.

## Features
Secure Authentication: Implements a robust JWT-based authentication flow for role-based access control (voters and administrators).

Tamper-Proof Voting: Utilizes an Ethereum smart contract to create an immutable and publicly verifiable record of all cast votes.

Trustless Process: Removes the need for a central authority to manage the election, placing trust in the decentralized logic of the smart contract.

Administrator Dashboard: Provides a dedicated interface for admins to manage the election lifecycle, including adding candidates and setting the voting period.

Intuitive Voter UI: A clean and simple interface allows voters to easily view candidate information and cast their vote securely via MetaMask.

## Tech Stack
Blockchain: Solidity, Ethereum, Truffle Suite

Backend: Python (FastAPI), Node.js (Express)

Database: MySQL

Frontend: HTML, CSS, JavaScript (Web3.js)

Tools: Ganache, MetaMask

## Screenshots

Login Page
![Login Page](https://github.com/BhaweshPandey952/Online-Voting-System/blob/main/public/login%20ss.png)

Admin Page
![Admin Page](https://github.com/BhaweshPandey952/Online-Voting-System/blob/main/public/admin%20ss.png)

Voter Page
![Voter Page](https://github.com/BhaweshPandey952/Online-Voting-System/blob/main/public/index%20ss.png)


## Code Structure

    ├── blockchain-voting-dapp            # Root directory of the project.
        ├── build                         # Directory containing compiled contract artifacts.
        |   └── contracts                 
        |       ├── Migrations.json       
        |       └── Voting.json           
        ├── contracts                     # Directory containing smart contract source code.
        |   ├── 2_deploy_contracts.js     
        |   ├── Migrations.sol            
        |   └── Voting.sol                
        ├── Database_API                  # API code for database communication.
        |   └── main.py                   
        ├── migrations                    # Ethereum contract deployment scripts.
        |   └── 1_initial_migration.js    
        ├── node_modules                  # Node.js modules and dependencies.
        ├── public                        # Public assets like favicon.
        |   └── favicon.ico               
        ├── src                           
        |   ├── assets                    # Project images.
        |   |   └── eth5.jpg              
        |   ├── css                       # CSS stylesheets.
        |   |   ├── admin.css             
        |   |   ├── index.css             
        |   |   └── login.css             
        |   ├── dist                      # Compiled JavaScript bundles.
        |   |   ├── app.bundle.js         
        |   |   └── login.bundle.js       
        |   ├── html                      # HTML templates.
        |   |   ├── admin.html            
        |   |   ├── index.html            
        |   |   └── login.html            
        |   └── js                        # JavaScript logic files.
        |       ├── app.js                
        |       └── login.js              
        ├── index.js                      # Main entry point for Node.js application.
        ├── package.json                  # Node.js package configuration.
        ├── package-lock.json             # Lockfile for package dependencies.
        ├── README.md                     # Project documentation.
        └── truffle-config.js                    # Truffle configuration file.
