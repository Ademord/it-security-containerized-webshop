# IT Security - Marketplace Lab
ZHAW - IT Security Lab - Application Containerized using Maven's spotify docker plugin.

## Setup
To spin up the project, run:
``` 
  docker-compose up 
```

or, build the images yourself with your own username prefix, which currently are: 
1. database: ademord/webshop_db
2. glassfish: ademord/glassfish
3. project image built with maven: ademord/webshop
``` 
mvn clean package docker:build
``` 

Be careful with the prefixes! Remember to update the project image, since it uses the glassfish image as base.
Look at the [3rd commit](https://github.com/Ademord/it-security-containerized-webshop/commit/3b0e3c7904f1b462b2667704fc6d65952d3de279) of the project to see what was done to containerize it.
