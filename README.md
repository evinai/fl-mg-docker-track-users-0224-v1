## UD-Tim Flask Project 1 track users ref temp 0224-v1
['Tutorial']('https://www.udemy.com/course/python-rest-apis-with-flask-docker-mongodb-and-aws-devops/learn/lecture/10730602#overview')


- use mongodb database
1. Add image name to db/Dockerfile mongo:6.0.6
2. add to docker-compose.yaml
   ```yaml
      depends_on:
      - db

    db:
        build: ./db
   ```
   
3. ```bash
   docker-compose build

4.  Update app.y 
5.  
   ```python
   from pymongo import MongoClient

   <!-- app = Flask(__name__)
   api = Api(app) -->

   client = MongoClient("mongodb://db:27017")
   db = client.aNewDB
   UserNum = db["UserNum"]

   UserNum.insert_one({
      'num_of_users':0
   })

   class Visit(Resource):
      def get(self):
         prev_num = UserNum.find({})[0]['num_of_users']
         new_num = prev_num + 1
         UserNum.update_one({}, {"$set":{"num_of_users":new_num}})
         return str("Hello user " + str(new_num))

6. ```bash
   docker-compose build

7. ```bash
   docker-compose run