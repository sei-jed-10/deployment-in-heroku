# Deployment in Heroku

1. **[CD to your rails project app] ** in the terminal `cd project_app`
2. **[Create a new repository]** Open your github account and create a new repository
3. **[Initialize the repository] (Follow repository steps)**

```Bash
echo "# Book_app" >> README.md
git init
git add README.md
git add .
git commit -m "first commit"
git remote add origin https://github.com/sarah/Book_app.git //your github repo link
git push -u origin master
```
4. **[Open the project_app]** In the terminal `code .`
5. **[Go to Gemfile in Rails app]** Add this in the end of the Gemfile.  

```Bash
group :production do
  gem 'pg'
end
```

6. **[Go to config/database.yml]** change the encoding to `encoding:utf8`

```bash
default: &default
  adapter: mysql2
  encoding: utf8mb4 #change utf8mb4 to encoding: utf8
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  username: root
  socket: /tmp/mysql.sock
```

7. **[For Windows User]** run `gem install bundler` and Run the bundle comman In the terminal `bundle`
7. **[For Mac user]** Run the bundle comman In the terminal `bundle --without production`
8. **[Push it in github] (Follow steps)** 

```Bash
git add . # For Windows if you get "warning LF will be replaced by CRLF in Gemfile" Rerun the command again
git commit -m "add new gem"
git push origin master 
```


9. **[Create an account in Heroku] (Follow steps)**(https://signup.heroku.com/devcenter) if you have an account in Heroku Skip this thep
10. **[Create a new app in Heroku]** In Heroku website create a new app after signing up. Make sure you to (Add an app name and choose Europe as a region)

11. **[Download and Install the Heroku CLI]**(https://devcenter.heroku.com/articles/heroku-cli#download-and-install) if you have Heroku Skip this thep
12.**[Follow Heroku steps Command] (For Windows user use Visual Studio termial)** 

```bash
heroku login
heroku git:clone -a appName # The appname you created in Heroku
heroku git:remote -a appName # The appname you created in Heroku
git add .
git commit -am "make it better" # If everything is up to date
git push heroku master
```

13. **[Open your Heroku Website]:** (https://dashboard.heroku.com/apps) go to your app name
14. **[Click thw Button More]** On your Dashboard You will find a button called "More" on the right hand side of the page next to Open app button.
15. **[Restart all dyno]** 
16. **[Run Console]** go to Run Console
17. **[In Heroku Console] (Follow this steps)** 

```bash
bundle # run bundle first
rails db:migrate 
rails db:seed
```

18. **[Open your Heroku website]** Click Open App button on the right hand side of your Dashboard.
