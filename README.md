# movie-api
ChessMate is a web-based Chess platform with focus on personal improvement. Some of the features are online ranked games, playing against various AIs and much more.  

## Table of contents

- [Project Title](#project-title)
  - [Table of Contents](#table-of-contents)
  - [About the Project](#about-the-project)
    - [Built With](#built-with)
  - [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
  - [Usage](#usage)
  - [Roadmap](#roadmap)
  - [Contributing](#contributing)
  - [License](#license)
  - [Contact](#contact)
  - [Acknowledgements](#acknowledgements)

## About the Project

We plan to build a web platform for people pationate interested in Chess to have fun and become better. We have ranking online system, friendly communication and challenges, puzzles, ability to play against different levels of AI (from a begginner to a above-pro) and much more.

### Built With

- [Stockfish](https://stockfishchess.org/)

## Getting Started

### Prerequisites

We plan to make our platform available from any device that can open web-pages, but it is in progress, you might need a couple of things to install locally:

- [Xampp](https://www.apachefriends.org/download.html) version 8.0.5 or higher
- [Stockfish](https://stockfishchess.org/download/) version 15.1 or higher
- [IntelliJ](https://www.jetbrains.com/idea/download/#section=windows) version 2023.1 or higher (we are working on at least making an .exe file instead, so keep in touch with our updates)


### Installation

Step-by-step instructions on how to install the project.

### Usage

This section should provide examples or instructions on how to use the project. Provide any information that the user may need to know before getting started, such as expected inputs and outputs, important features or limitations, and so on.

### Roadmap

1. Make a cluster on mongodb atlas
2. connect to the clutser using mongodb compass, a GUI  for the database
3. Use spring initialzer to make a zip spring boot application
4. Open the project in an IDE
5. Configure the database in src/main/resources/application.properties to connect to the mongodb cluster
6. Make a .env file to store sensitive properties for the database, so  that the information is not available to the world
7. Spring does not support reading .env files out of the box, so we need to install a maven dependnecy
8. spring-dotenv by paulschwarz is added to the pom.xml file as a new dependency
9. Now go bck  to application.properties file and replace the hardcoded database name and uri components with ${MONGO_THING}
10. If Main runs, that means the .env file was read successfully
11. Now we need to create two classes for two entities: movies and reviews, add annotations and such
12. Create a java class called MovieController, our first RestAPI controller
13. Check that the HTTP request returns 200 by inputting the command "curl -i http://localhost:8080/api/v1/movies" into cmd
14. Create a service class and a repository class to  use the Movie class model and pull data from the database
15. Make Repository an interface because repositories are of type interface
16. In RestAPI there are multiple layers
17. The API layer, which is our MovieController, concerns itself about the task of getting a request from the user and returning a response
18. The MovieController class uses the MovieService class by calling allMovies() from MovieService which returns the list of all the movies and a HTTPStatus of OK (200)
19. MovieController does not actually know what happens in the MovieService class, separation of concerns
20. The MovieService is where the business logic goes, uses the MovieRepository class and  talks to the database and gets the list of the movies then returns to the API layer, the Movie Controller class
21. The MovieRepository class is the Data Access Layer (DAL) of our API that does the ctual job of talking to the database and bringing back the data
22. Use Postman to test the API

### Contributing

Here you should provide instructions on how other developers can contribute to the project. This should include guidelines for submitting pull requests, coding conventions, and any other relevant information.

### License

This project is licensed under the MIT License - see the LICENSE file for details.

### Contact

Here you can provide information on how to contact you or the project team. This can include email addresses, social media handles, or a link to a website.

### Acknowledgements

Here you can give credit to any individuals or organizations that have contributed to the project or provided support.
https://www.youtube.com/watch?v=5PdEmeopJVQ&ab_channel=freeCodeCamp.org
