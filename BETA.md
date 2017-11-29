# Instructions for the Okta Self Service Registration Beta

## In Okta

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
- Click the "Save" button

Once the new App has been created:

- Click on the "Registration" tab
- Click the "Enable Registration" button
- *For now, we'll be using the defaults in the page*
- Scroll to the bottom and click the "Save" button
- Select the "General" tab
- Scroll to the bottom of the General tab, make note of the following:
  - Client ID
  - Client Secret

## On your computer

Install the example OIDC application by running the following commands from your terminal:

- $ `git clone https://github.com/jpf/okta-ssr-beta.git`
- $ `cd okta-ssr-beta/`
- $ `npm install`

  Note: For this to work, you will need to have [node.js](https://nodejs.org/en/) installed.
- $ `node server.js --iss https://example.okta.com --cid 0abc12d3e4FGHijkL5m6 --cs a0bCDEFGh1IJKlmNO23PQRSTUVwXyZ4aBc5-defG`

  Note: You **MUST** replace the values of `iss`, `cid`, and `cs` with the values for your own Okta org!
- In a browser, open this link: http://localhost:7080/widget

You should now see an example app running, with the Okta Sign-In Widget loaded:
- Look for th text that says "Don't have an account?" and click the "Sign up" link
- Fill out the fields with test values
- Click the "Register" button
- Answer any setup questions you might need to answer, then click "Create My Account"

You should be redirected to the example OIDC application and see the value of the "Claims" associated with the user you just created.
