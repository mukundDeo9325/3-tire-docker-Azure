#### Edit index.html file and add backend URL

#### Create Docker Image
````
docker build -t apache .
````

#### Create Docker COntainer
````
docker run -itd --name apache-fe -p 80:80 apache
````
#### Go to browser add public ip of instance you will see following UI

#### Click on ***Enter to Student Application*** it will redirect you to backend page

#### Student Data is saved into Database
