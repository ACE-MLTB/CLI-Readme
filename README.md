# Deploy

**Important Note**
1. Upload all of your private files here: `config.env`, `token.pickle`, `rcl.conf`, `accounts.zip`, `shorteners.txt` etc...

**Mandatory Veriables in Config**

- `UPSTREAM_REPO`: Your github repository link, if your repo is private add `https://username:{githubtoken}@github.com/{username}/{reponame}` format. Get token from [Github settings](https://github.com/settings/tokens). So you can update your bot from filled repository on each restart. `Str`.
  - **NOTE**: Any change in docker or requirements you need to deploy/build again with updated repo to take effect. DON'T delete .gitignore file. For more information read [THIS](https://github.com/Dawn-India/Z-Mirror#upstream-repo-recommended).
- `UPSTREAM_BRANCH`: Upstream branch for update. Default is `master`. `Str`

- `BOT_TOKEN`: The Telegram Bot Token that you got from [BotFather](https://t.me/BotFather). `Str`
- `OWNER_ID`: The Telegram User ID (not username) of the Owner of the bot. `Int`
- `TELEGRAM_API`: This is to authenticate your Telegram account for downloading Telegram files. You can get this from <https://my.telegram.org>. `Int`
- `TELEGRAM_HASH`: This is to authenticate your Telegram account for downloading Telegram files. You can get this from <https://my.telegram.org>. `Str`

- `BASE_URL`: Valid BASE URL where the bot is deployed to use torrent web files selection. Format of URL should be `https://app-name.herokuapp.com/`, where `app-name` is the name of your app. `Str`

------

## Deploy With CLI

- Deployment instructions uploaded [HERE](https://gist.github.com/Dawn-India/9be1ca66b392dee82bcbc8d7f7ebefe8)

## Instructions
- Install CLI using official docs: https://devcenter.heroku.com/articles/heroku-cli

- Clone this repo: git clone https://github.com/Dawn-India/Z-Mirror Z-Mirror/ && cd Z-Mirror

- Switch to deploy branch: git checkout zh_deploy

- Now add your config and all other private files.

- After adding your private files: git add . -f

- Then commit your changes: git commit -m init

- Login to heroku: heroku login

- Create heroku app: heroku create --region us YOUR-APP-NAME

- Add remote: heroku git:remote -a YOUR-APP-NAME

- Create container: heroku stack:set container

- Push to heroku: git push heroku zh_deploy:master -f


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
