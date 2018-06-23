# TapNews
A News Scraping and Recommendation System using React, Node.js, MongoDB, and TensorFlow.

If you like this project. Please give it a star. If you have any interesting idea about further development, just let me know!

## Run the job:
#!/bin/bash 
fuser -k 3000/tcp 
fuser -k 4040/tcp 
fuser -k 5050/tcp 

service redis_6379 start 
service mongod start 

pip install -r requirements.txt 

cd ./web_server/client 
npm install 

npm run build 
npm run-script build 
cd ../server 
npm install 
nodemon ./bin/www & 
cd ../../backend_server 
python service.py & 
cd ../news_recommendation_service 
python recommendation_service.py & 
python click_log_processor.py & 

## Stop the jobs:
fuser -k 3000/tcp 
service redis_6379 stop 
service mongod stop 
