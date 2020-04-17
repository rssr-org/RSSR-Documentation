RSSR includes following folders:

- [provider](#provider)
- [public](#public)
- [src](#src)

### provider
This folder is the starting point of the program, in other words, when running the program, the files in this section are read first. Requests will be sent to this section and eventually the answer will be returned in interaction with other sections.
This folder includes the following sections:

- server: Server files are in this folder
- setup: This folder contains settings and configurations
- webpack: Webpack settings saved in this folder

### public
In this folder static files like images, videos, etc will be save
### src
This folder contains web application's source code and includes following folders:
 - **render**:the starting point is the src section, the basic configs are in this section.
 - **App**: Includes standalone entities that can cover a full view of the site and connect to the site's routing.
 -  **component**: components that do not meet the app directory requirements and are shared between several containers.
 - **partial**: there are tools ,this directory contains react entities.
 - **setup**: general settings and structures include the src section.
