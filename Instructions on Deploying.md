# Project-Honeybadger
In order to POST request with a JSON payload you can use any tool like curl, http, or Postman. I used curl Here's the code using curl: 
curl -X POST \
  -H "Content-Type: application/json" \
  -d '{"RecordType": "Bounce", "Type": "SpamNotification", "TypeCode": 512, "Name": "Spam notification", "Tag": "", "MessageStream": "outbound", "Description": "The message was delivered, but was either blocked by the user, or classified as spam, bulk mail, or had rejected content.", "Email": "zaphod@example.com", "From": "notifications@honeybadger.io", "BouncedAt": "2023-02-27T21:41:30Z"}' \
  http://localhost:5000/process_payload

This command sends a POST request to the /process_payload endpoint with the JSON payload in the -d option. You'll need to replace the URL with the URL for your app's endpoint.

When you run this command, it should send a request to your app and trigger the process_payload function. If the payload is a spam notification, the app should send an alert to your Slack channel.



Steps to create a new slack app in order to run it to verify the post on the channel.

Go to https://api.slack.com/apps and click the "Create New App" button.
Enter a name and select the workspace where you want to install the app, then click "Create App".
On the "Add features and functionality" page, choose the features you want to add to your app. For this project, you don't need to add any features, so you can skip this step.
On the "Install App" page, click the "Install App to Workspace" button to install the app in your selected workspace.
On the "OAuth & Permissions" page, add the necessary scopes to your app. For this project, you need the chat:write scope, which allows your app to send messages to a Slack channel. Click the "Add an OAuth Scope" button and select the chat:write scope, then click "Save Changes".
On the same page, click the "Install App to Workspace" button to reinstall the app with the new scope.
Create a new channel where alerts will be sent, if you haven't already. You can do this by clicking the "+" button next to "Channels" in the Slack sidebar, then entering a name and clicking "Create".
Finally, copy the webhook URL for the channel you created. You can do this by going to the channel settings and scrolling down to the "Webhooks" section. Click the "Add a webhook" button, then copy the URL that appears. This URL will be used to send messages to the channel.
