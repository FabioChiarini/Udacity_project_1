# Udacity_project_1: Log Analysis
The project let the user find on a newspaper database which are the top 3 articles, the top 3 authors and the days in which the percentage of requests that lead to errors is grater than 1%.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

First, install vagrant VM on your local machine. This will give you the environment need to run the project. Then bring *VAGRANT UP* and log into your VM with *VAGRANT SSH*. 

### Installing

Download the zip file containing the newsdata.sql database and unzip it. Move this file into your vagrant directory, in order to share it with your VM. 
To check if you did everything correctly, try connecting to the database with *psql news* and run the following queries:

```
\dt
\d articles
select * from articles
```

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project has no license
