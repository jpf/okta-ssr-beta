# Instructions for the Okta Self Service Registration Beta

## Instructions

Below are instructions for setting up an example OIDC app that will let you test
Self-Service Registration in Okta.

![Screenshot of "logged in" view](https://user-images.githubusercontent.com/8584286/33508870-fb199e08-d6b1-11e7-8a66-e9eda4d15c55.png)

## Prerequisites

You will need the following to get this sample app working:

- Okta Org
- [Heroku account](https://signup.heroku.com/)

## In Okta

The first think you'll need to do is set up an OIDC app in Okta and enable
Registration in that app.

Create an OIDC app:

- Click the "Admin" button
- Click the "Add Applications" shortcut
- Click the "Create New App" button
- Select "Web" in the Platform dropdown
- Select "OpenID Connect" as the Sign on method
- Click the "Create" button
- Select a name for your OIDC app (e.g. "Registration Beta App")
- Add the folowing URIs as Login Redirect URIs:
  - `http://localhost:7080/oauth/callback`
  - `http://localhost:7080/widget`
- Add logout URLs to whitelist
- Click the "Save" button

Once the new App has been created:

- Click on the "Registration" tab
- Click the "Enable Registration" button
- *For now, we'll be using the defaults in the page*
- Scroll to the bottom and click the "Save" button
- Select the "General" tab
- Scroll to the bottom of the General tab, make note of the following:
  - **Client ID**
  - **Client Secret**

## Deploy this sample to Heroku

Once you've set up the OIDC app in Okta, you will need to deploy the sample app
to Heroku. Start that process by clicking the button below:

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/jpf/okta-ssr-beta)

You will be taken to Heroku and prompted for information to enter for your this
ample app, in particular you will need:

1. Your Okta org URL (e.g.: https://example.oktapreview.com)
2. The Client ID from the OIDC app you just created
3. The Client Secret from the OIDC app you just created

Once you've filled out the information above, click on the "Deploy app" button.

After clicking on the "Deploy app" button, you will see status information on
the status of the Heroku app.

Eventually you will see the words "Your app was successfully deployed"

**Important:**

When you see "Your app was successfully deployed", click on the "View" button.

NOTE:

Make sure you click on the "View" button as that will take you to a page
with important information on how to finish the deployment.

If you missed the steps above, you can visit the page with instructions
to finish your setup by adding `/welcome` to the end of the URL for the sample
app you've just deployed. For example, if your Heroku URL is
`https://example.herokuapp.com` you can see the instructions by going to
`https://example.herokuapp.com/welcome`
