# Dataset to use in MongoDB loader example
---

Credits and thanks to Shivam Bansal that made this dataset available on [Kaggle](https://www.kaggle.com/datasets/shivamb/netflix-shows)

## How to Load into Mongo using `mongoimport` in 5 Steps

### 1.

Clone this repo using `git clone` or download .csv file directly.

### 2.

Create a Docker Container with a MongoDB image. Map ports if you want to connect in your local machine either.

`docker run --name mongoDocker -d -p 27017:27017 mongo`

### 3.

Access the container using:

`docker exec -it mongoDocker bash`

### 4.

Copy .csv file from your local machine to container

`docker cp netflix_titles.csv mongoDocker:tmp/`

### 5

Run `mongoimport` command

`mongoimport -d moviesDB -c movies --type csv --headerline --file tmp/netflix_titles.csv`

It's Done!
