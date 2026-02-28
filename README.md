# flask-on-docker

This repo is a simple web app that runs inside a Docker container, Docker allows you to run programs in an environments such that it runs the same on every computer. This app is built with Flask(python framework), the data is stored in a pstgres database and we use Nginx on the production level to handle incoming web requests.this app allows you to upload images and files and view them in your browser. 

[Demo](big_data_video.gif) 

#build instructions 

1. Intsall docker on your computer 
2. run the following in your terminal:

#for devolopment and testing :
docker compose up -d --build 
docker compose exec web python manage.py create_db

then open browser and go to: http://localhost:8080
you should see {"hello":world}

#real version (production)
docker compose -f docker-compose.prod.yml up -d --build
docker compose -f docker-compose.prod.yml exec web python manage.py create_db

# How to upload a file
1. Go to http://localhost:8080/upload in your browser
2. Click "Choose File" and pick any image from your computer
3. Click "Upload"
4. View your uploaded file at http://localhost:8080/media/FILENAME
   (replace FILENAME with the actual name of your file, e.g. cat.png)

