[[Automate development (DevOps)]]

Install on Ubuntu
```
curl https://cli-assets.heroku.com/install-ubuntu.sh | sh
```

Install [[PostgreSQL]] on Linux then run
```term
export DATABASE_URL=postgres://$(whoami)
```

Enter heroku dyno
```
heroku ps:exec --app APP_NAME
```

Use vim to edit files inside a Heroku Dyno [code](https://github.com/jasonheecs/heroku-vim)