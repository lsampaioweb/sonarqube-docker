# SonarQube Docker Compose

You can access the project through the following link: https://sonarqube.homelab.

## Config Files:

We added a help file with the default configuration to connect SonarQube and the OpenLDAP. Check the [ldap.txt](init/ldap.txt "ldap.txt") file.

If you want, you can create a [sonar.properties](init/sonar.properties "sonar.properties") file and set some default configurations.

## Folders:

1. Default folder.

``` bash
# Configuration files, such as sonar.properties.
sonarqube-conf:/opt/sonarqube/conf:

# Data files, such as the embedded H2 database and Elasticsearch indexes.
sonarqube-data:/opt/sonarqube/data:

# Log files.
sonarqube-logs:/opt/sonarqube/logs

# Plugins, such as language analyzer.
sonarqube-extensions:/opt/sonarqube/extensions:
```

## Commands:

1. Enter the container.

``` bash
docker exec -it sonarqube bash
```

2. Enter the container as root.

``` bash
docker exec -u root -it sonarqube bash
```

3. Configuration to send emails.

``` bash
Secure connection : starttls
SMTP host         : smtp.gmail.com
Password          : <password>
Porta             : 587
Username          : <email>
```

## Backup:

``` bash
The "." means the default folder.
docker cp sonarqube:/opt/sonarqube/conf .
docker cp sonarqube:/opt/sonarqube/extensions .
docker cp sonarqube:/opt/sonarqube/logs .
docker cp sonarqube:/opt/sonarqube/data .
```

## Restore:

``` bash
The "." means the default folder.
docker cp conf sonarqube:/opt/sonarqube/conf
docker cp extensions sonarqube:/opt/sonarqube/extensions
docker cp logs sonarqube:/opt/sonarqube/logs
docker cp data sonarqube:/opt/sonarqube/data
```

## References:

1. [SonarQube Integration with Jenkins for Code analysis.](https://www.youtube.com/watch?v=jh7utASgKj4 "SonarQube Integration with Jenkins for Code analysis")

1. [Docker Hub.](https://hub.docker.com/_/sonarqube/ "Docker Hub")

1. [Documentação de como administrar.](https://docs.sonarqube.org/latest "Documentação de como administrar")

1. [Setup Docker Sonarqube on local - Analyst Java code.](https://www.youtube.com/watch?v=Y4yM6Xarb8E "Setup Docker Sonarqube on local - Analyst Java code")

1. [How I configured SonarQube for Python code analysis with Jenkins and Docker.](https://blog.mphomphego.co.za/blog/2018/09/14/How-I-configured-SonarQube-for-Python-code-analysis.html "How I configured SonarQube for Python code analysis with Jenkins and Docker")

1. [Code Analysis Part 2: Analyzing Code with SonarQube.](https://dzone.com/articles/code-analysis-part-2-analyzing-code-with-sonarqube "Code Analysis Part 2: Analyzing Code with SonarQube")

1. [SonarQube on Windows and MS SQL.](http://blog.majcica.com/2016/04/28/sonarqube-on-windows-and-ms-sql "SonarQube on Windows and MS SQL")

1. [SonarLint.](https://www.sonarlint.org "SonarLint")

### License:

[MIT](LICENSE "MIT License")

### Created by:

1. Luciano Sampaio.
