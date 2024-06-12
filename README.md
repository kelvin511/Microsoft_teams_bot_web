# Steps For Setting the project


- Register the app in Microsoft Entra Admin 
Visit the officail link [Visit Here](https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-single-page-app-react-register-app "Visit Here")

- .env 
clone or extract the code and in the root of the project make a new .env file with the following content 
OAUTH_CLIENT_ID= clinet id of the app registered in Azure(see below to register)
OAUTH_CLIENT_SECRET= app client secret 
OAUTH_REDIRECT_URI= redirect url where the azure atuh will send the auth token (configure durig app registration)
OAUTH_SCOPES='user.read,calendars.readwrite,mailboxsettings.read,onlinemeetings.readwrite'
OAUTH_AUTHORITY=https://login.microsoftonline.com/common/
TENANT_ID= tenant id of the app 

- Navigate to BotFile.ts in the project inside Bot folder
Now according to you system change the following :
1. executablePath: `/bin/google-chrome` path for the browser (this is for ubuntu)
1. userDataDir: `/.config/google-chrome/default`  user profile data for browser (if you will not provide this then the bot will join as a guest and you may need to put the name when screen pops up for the meet to join and make sure you are looged in with you Microsoft Account in the browser. Initially it may ask to enter the password of MS Account)

- Set Up for notifcation URL
Navigate to graph.ts file in the root of the project. Then in the createSubscription function replace 
notificationUrl:
        "your-url/notifications
with the url you want to receive the notification (for development use ngrok)
make sure you add /notifications endpoint after the url to receive the notificaiton