# ruboty-timecard-template
A template to create and deploy your [ruboty](https://github.com/r7kamura/ruboty) to punch a timecard on slack.

* Your team owner need to enable [XMPP Gateway](https://my.slack.com/admin/settings).
* It's recommended to create a new slack account for your ruboty.

## 1. Get credentials
Fron [here](https://code.google.com/apis/console), create a client ID and a client secret.

```bash
% open "https://accounts.google.com/o/oauth2/auth\
?access_type=offline\
&client_id=${CLIENT_ID}\
&redirect_uri=${REDIRECT_URI}\
&response_type=code\
&scope=https://www.googleapis.com/auth/drive"
```

```bash
% curl \
> -d "client_id=${CLIENT_ID}" \
> -d "client_secret=${CLIENT_SECRET}" \
> -d "redirect_uri=${REDIRECT_URI}" \
> -d "grant_type=authorization_code" \
> -d "code=${CODE}" \
> "https://accounts.google.com/o/oauth2/token"
{
  "access_token" : "...",
  "token_type" : "Bearer",
  "expires_in" : 3600,
  "refresh_token" : "..."
}
```

## 2. Deploy
Press "Deploy to Heroku" button and fill in a form to deploy Ruboty to heroku.

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

![](images/deploy.gif)

## 3. Add dyno
Because Heroku doesn't create dyno by default,
you need to add 1 dyno from [dashboard](https://dashboard-next.heroku.com/apps).

![](images/add-dyno.gif)

## 4. Fork
Fork this repository if you want to add other plug-ins. :fork_and_knife:  
See https://github.com/r7kamura/ruboty for more details about ruboty and its plug-ins.
