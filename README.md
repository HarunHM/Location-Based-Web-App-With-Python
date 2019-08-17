# Location-Based-Web-App-With-Python
 A Location-Based Web App With Django, GeoDjango,spatial database (PostgreSQL and PostGIS) and Deploying it on Heroku.

# Deploying python app on Heroku

1). First install guinicorn locally. 
You can install guinicorn on your local computer using any of the following command .
        
         1. pipenv install gunicorn 
         2. pip install gunicorn
       
2). Then install  Heroku CLI   locally on your machine.     
       
After successfully installing Heroku,  Login via CLI using the following command

         heroku login
         
3). Now you can create an app and DataBase using the following commands respectively.
           
         heroku create <appname>
         heroku addons:create heroku-postgresql:hobby-dev --app <appname>    


4). Now you can Get url And make sure you add it to your app.
         
         heroku config --app <appname>
         
5). Follow the  commands  below step by step to create Procfile, requirements.txt and a runtime.txt;
         
         touch Procfile
         web: gunicorn app:app
         
         
         pip freeze > requirements.txt
         touch runtime.txt
         python-<version>
         
6). At this step we will deploy our app using Git using  the following command;
        
        
        git init
        git add . && git commit -m 'Deploy'
        heroku git:remote -a <appname>
        git push heroku master
        
        
7). Now add table to remote database using the following scripts
     
         heroku run python
         >>> from app import db
         >>> db.create_all()
         >>>exit()
          
          
    YOU CAN NOW VISIT YOU WEBSITE USING YHE FOLLOWING COMMAND
    
         heroku open.


         
         
         
                       
           
