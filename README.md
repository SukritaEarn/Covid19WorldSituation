# Covid-19 Around The World

![Asia](https://www.phocuswire.com/uploadedImages/Articles/Opinion/2020/May/womens-leadership-coronavirus.jpg?origwidth=800&origheight=400&origmode=crop&Anchor=MiddleCenter&width=800&height=400&scale=both&mode=crop)

Our group will analyze the covid-19 situation around the world including the total Covid-19 cases, new cases, death cases and recovered cases and the impact of Covid-19 to the economic situation by comparing the currency rate with the new Covid-19 cases that occurred in each countries from the time Covid-19 start until now.

## Team members

| Name | ID |
|-----|-------|
| Kritpawit Soongswang | 6110545414 |
| Vichyawat Nakrugsa | 6110545635 |
| Tiranan Emson | 6110546003 |
| Sukrita Kittipitayakorn | 6110546062 |
| Kasidis Luangwutiwong | 6110546364 |

## Project Documents

* [Iteration Plan](https://docs.google.com/document/d/17CdvZp6VYVfGaNv4XVd__rAw1pbZXyCVpwmc6K35UfE/edit#)
* [Task Board](https://github.com/SukritaEarn/Covid19WorldSituation/projects/1)

## Datasource
- The first source will provide the covid-19 cases around  the world including the total covid-19 cases, new cases, death cases.
- The second source will provide the recovered cases.
- The third source will provide the country detail around the world. 
- The last source will provide the currency rate in each country.

## Installation
- If you want to run on provided environment you can use only Docker. You can follow these steps: [Installation using Docker](#option-1-installation-using-docker)
- However, if you want to run on your own environment you will need
    - Python version 3.6 or greater
    - Node.js
    - Java
  Then follow these steps: [Installation using your own environment](#option-2-installation-using-your-own-environment)

## Option 1: Installation using Docker
1. Clone or download the project to your machine.
2. Access to project directory. For example,
    ```
    YOUR_DIRECTORY/Covid19AroundAsia/ $
   ```
3. You need to have Docker installed on your local machine. Make sure that you can call `docker` command via your command tool.
4. Generate openapi with covid-api.yaml
   ```
   java -jar openapi-generator-cli-4.3.1.jar generate -i openapi/covid-api.yaml -o autogen -g python-flask
   ```
5. Run
    ```
    docker-compose up
    ```
## Option 2: Installation using your own environment
1. Clone or download the project to your machine.
2. Install Flask framework. Use command line tools.

    For Unix:
    ```
    pip3 install Flask
   ```
   
    For Windows:
    ```
    pip install Flask
   ```
3. Install openapi-to-graphql. Using this command.
    ```
    npm i openapi-to-graphql
    ```
   Then install for command line interface.
   ```
   npm i -g openapi-to-graphql-cli
   ```
3. Access to project directory. For example,
    ```
    YOUR_DIRECTORY/Covid19AroundAsia/ $
   ```
4. Generate models by this command.
    ```
    java -jar openapi-generator-cli-4.3.1.jar generate -i openapi/covid-api.yaml -o autogen -g python-flask
   ```
5. Install all requirements.
   ```
   pip install -r requirements.txt
   ```
6. Run a local server on your machine by this command.
   
   For Unix:
    ```
   python3 app.py
   ```
   
   For Windows:
   ```
   py app.py
   ```
   .
7. Open second window command line. Open GraphQL accessible by this command.
    ```
   openapi-to-graphql --cors -u http://localhost:9000/covid-api/v1/ openapi/covid-api.yaml
   ```
   Default port is 8080. You can change to your port that you open python local server.
8. Install node package to access front-end at localhost.
    ```
    npm install
    npm start
    ```
    - The server will run on default configuration on http://localhost:9090/
   - Enjoy using web-app


## Pages
All pages provide in this project including
- [Application Interface](#access-api-page)
- [Covid-19 Web App](#access-covid-19-web-app)
- [Database Service using MySQL](#access-database-service)
- [Jenkins](#access-jenkins)
- [Node-RED](#access-node-red)

## Access API page
1. Start the REST API server and Optionally test the API at
   ```
   http://localhost:8080/covid-api/v1/ui/
   ```
2. We can see information about covid-19 API by seeing the documentation. All method provide by GET request.
   - /countries
   - /countries/{countryName}
   - /covid19Situation/newCases/allCountry
   - /covid19Situation/newCases/world
   - /covid19Situation/newCases/{countryName}
   - /covid19Situation/summary/allCountry
   - /covid19Situation/summary/world
   - /currencyRates/unit/{countryName}
   - /currencyRates/{countryName}
## Access Jenkins
Prerequiste: jdk version 1.8
```
java -jar jenkins.war
```
- Then go to http://localhost:8080/ and add new jenkins pipeline then click build now.
