RSSR includes following folders:

- [provider](#provider)
- [public](#public)
- [src](#src)

### provider
This folder is the starting point of the program, in other words, when running the program, the files in this section are read first. Requests will be sent to this section and eventually the answer will be returned in interaction with other sections.
This folder includes the following sections:

- server: Nodejs webserver setup files are in this folder
- setup: This folder contains settings and configurations
- webpack: Webpack settings saved in this folder

### public
In this folder static files like images, videos, etc will be save.
The user request from the nodejs server first reaches this folder and then the application.

### src
This folder contains web application's source code and includes following folders:
 - **App**: Includes standalone entities that can cover a full view of the site and connect to the site's routing.
 -  **Component**: Components that do not meet the app directory requirements and are shared between several containers.
 - **Partial**: There are tools like NPM Packages,The only difference is that these tools are react entities.
 - **render**:The starting point is the src section, the basic configs are in this section.
 - **setup**: general settings and structures include the src section.
