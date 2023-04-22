# vue-cloud-functions

## Background:
There are several issues involved in a web site project with authorization.
The project consists of a Frontend and Backend and has an authorization feature for this site.
The Frontend will authorize users and generate a secret token using Firebase authorization.
This token will be passed to the Backend, which will validate the token and identify the user.

## Issues
1. **Storing the token in the browser securely**

   There are some challenges with securely storing data on the browser. 
   Developers should protect secret data from malicious attacks like XSS.

   *Reference:* [Secure token storage on browser](https://zenn.dev/peg/articles/e69de52ed12381)

2. **Transmitting the token to the Backend securely**

   If a token is stolen, an attacker can access an API requiring authorization. This can lead to personal data leakage. As a result, the transmission should be done securely, like using HTTPS.

3. **Identifying the user on the Backend side securely**

   On the backend, certain processes need to know user-specific information. This will be done by fetching the user information using the secret token. All of these processes should be carried out securely.


## About this project
This project aims to address the abovementioned issues, and the proposed technology stack includes:
- Vue for the frontend
- firebase authorization
- GCP API gateway for the authorization of API access
- GCP Cloud functions for backend processes

As an initial phase of this project, the focus is on implementing the ability to use cloud functions from Vue.

## Key features
Key features of this project include the following:
- Creating the GCP's cloud functions
- Utilizing the cloud functions feature from Vue
