# Deploy to Heroku

- Install Heroku CLI
```
curl https://cli-assets.heroku.com/install-ubuntu.sh | sh
```

- Clone Repo
```
git clone https://ACE-MLTB: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@github.com/ACE-MLTB/repo
```
```
cd repo
```

- Switch to deploy branch
```
git checkout zh_deploy
```

- Login to heroku (Using Email & API Key)
```
heroku login -i
```

- Create Heroku App
```
heroku create --region eu app
```

- Add remote
```
heroku git:remote -a app
```

- Create container
```
heroku stack:set container
```

- Push to heroku
```
git push heroku zh_deploy:master -f
```


## Extras

- To delete the app: heroku apps:destroy YOUR-APP-NAME

- To restart dyno: heroku restart

- To turn off dyno: heroku ps:scale web=0

- To turn on dyno: heroku ps:scale web=1

- To set heroku variable: heroku config:set VARNAME=CONFIG_FILE_URL

- To get live logs: heroku logs -t


# Deploy to Railway

- Install Railway CLI
```
npm i -g @railway/cli
```

- Clone Repo
```
https://<deploy_token>:<empty_password>@gitlab.com/<your_username>/<repository_name>
```

```
cd repo
```

- Login
```
railway login --browserless
```

- Create Project
```
railway init
```

- Link Project to Repo
```
railway link <project_id>
```

- Deploy
```
railway up
```
