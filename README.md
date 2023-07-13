## Deploy With CLI

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


### Extras

- To delete the app: heroku apps:destroy YOUR-APP-NAME

- To restart dyno: heroku restart

- To turn off dyno: heroku ps:scale web=0

- To turn on dyno: heroku ps:scale web=1

- To set heroku variable: heroku config:set VARNAME=CONFIG_FILE_URL

- To get live logs: heroku logs -t


1. Opitionally you can upload your config as a secret on https://gist.github.com/

   
   - CONFIG_FILE_URL: Copy https://github.com/Dawn-India/Z-Mirror/blob/main/config_sample.env in any text editor. Remove the _____REMOVE_THIS_LINE_____=True line and fill the variables. For details about config you can see Here. Go to https://gist.github.com and paste your config data. Rename the file to config.env then create secret gist. Click on Raw, copy the link. This will be your CONFIG_FILE_URL. Refer to below images for clarity.

![Steps from 1 to 3](https://graph.org/file/2a27cf34dc0bdba885de9.jpg)

![Step 4](https://graph.org/file/fb3b92a1d2c3c1b612ad0.jpg)

![Step 5](https://graph.org/file/f0b208e4ea980b575dbe2.jpg)

3. Remove commit id from raw link to be able to change variables without updating the CONFIG_FILE_URL in secrets. Should be in this form: https://gist.githubusercontent.com/username/gist-id/raw/config.env
   - Before: https://gist.githubusercontent.com/Dawn-India/8cce4a4b4e7f4ea47e948b2d058e52ac/raw/19ba5ab5eb43016422193319f28bc3c7dfb60f25/config.env
   - After: https://gist.githubusercontent.com/Dawn-India/8cce4a4b4e7f4ea47e948b2d058e52ac/raw/config.env

4. Add all your private files in this branch.

5. In yout app settings click on reveal config vars and add `CONFIG_FILE_URL`
