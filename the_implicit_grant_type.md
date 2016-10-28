# The Implicit Grant Type

The implicit grant type is meant to be used **for client-side web applications** (like React.js or Angular.js) **that don’t have a server-side component** — or any sort of mobile application that can use a mobile web browser.

Implicit grants are ideal for client-side web applications and mobile apps because this grant type doesn’t require you to store any secret key information at all — this means you can log someone into your site / app WITHOUT knowing what your application’s client_secret is.

Here’s how it works:

1. An anonymous user visits your website or opens your mobile app.
2. They want to log into your site using a Third-Party Identity, stored somewhere else: Google, Facebook, your own OAuth service that you created, etc.
3. They click a “Log In” button on your site / app and are redirected to their identify provider’s website (eg: Google, Facebook, etc.), and are prompted to accept certain permissions.
4. If they accept these permissions, the identity provider will redirect the user BACK to your web application along with an access token.
5. You can these use this access token to actually retrieve this user’s information.

## How to Use The Implicit Grant Type
You’ll basically create a login button on your login page that contains a link that looks something like this:

    https://login.blah.com/oauth?response_type=token&client_id=xxx&redirect_uri=xxx&scope=email
 
When the user clicks this button they’ll visit **login.blah.com** where they’ll be prompted for whatever permissions you’ve requested.

After accepting the permissions, the user will be redirected to back to your site, at whichever URL you specified in the **redirect_uri** parameter, along with an **access token**. Here’s how it might look:

    https://yoursite.com/oauth/callback?token=xxx
 
You’ll then read in the **token query string value** which you can use to make real API calls to retrieve the user’s information from the identity provider.

**NOTE:** The **client_id** stuff you see in the above examples are provided by the identity provider. When you create a Facebook or Google app, for instance, they’ll give you these values.