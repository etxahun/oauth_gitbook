# The Authorization Code Grant Type
The **authorization code OAuth grant type** is meant to be used on **web servers**. You’ll want to use the authorization code grant type if you are building a web application with server-side code that is NOT public. **If you want to implement an OAuth flow in a server-side web framework like Express.js, Flask, Django, Ruby on Rails, an Authorization Code is the way to go**.

Here’s how it works:

1. An anonymous user visits your website.
2. They want to log into your site using a Third-Party Identity, stored somewhere else: Google, Facebook, your own OAuth service that you created, etc.
3. They click a “Log In” button on your site and are redirected to their identify provider’s website (eg: Google, Facebook, etc.), and are prompted to accept certain permissions.
4. If they accept these permissions, the identity provider will redirect the user BACK to your web application along with an authorization code.
5. Your web server will then make a request to the identity provider’s API with the authorization code you were just given, and you’ll then be given an access token you can use to actually retrieve this user’s information.

## How to Use The Authorization Code Grant Types
You’ll basically create a login button on your login page with a link that looks something like this:

    https://login.blah.com/oauth?response_type=code&client_id=xxx&redirect_uri=xxx&scope=email

When the user clicks this button they’ll visit **login.blah.com** where they’ll be prompted for whatever permissions you’ve requested.

After accepting the permissions, the user will be redirected to back to your site, at whichever URL you specified in the **redirect_uri** parameter, along with an **authorization code**. Here’s how it might look:

    https://yoursite.com/oauth/callback?code=xxx

You’ll then read in the **code query string value**, and exchange that for an access token using the provider’s API:

    POST https://api.blah.com/oauth/token?grant_type=authorization_code&code=xxx&redirect_uri=xxx&client_id=xxx&client_secret=xxx
 
**NOTE:** The **client_id** and **client_secret** stuff you see in the above examples are provided by the identity provider. When you create a Fac  ebook or Google app, for instance, they’ll give you these values.

Once that POST request has successfully completed, you’ll then receive an **access token** which you can use to make real API calls to retrieve the user’s information from the identity provider.