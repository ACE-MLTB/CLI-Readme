# Deploy to Heroku

- Install Heroku CLI
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/SKGHD/Termux-heroku-cli/master/install.sh)"
```

- Clone Repo
```
git clone https://<username>:<token>@github.com/<username>/<repo>
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

# Deploy to Railway

- Install Railway CLI
```
npm i -g @railway/cli
```
```
sudo -s
```
```
curl -fsSL https://railway.app/install.sh | sh
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
