# The Password Credentials Grant Type

The password credentials grant type is meant to be used for first class web applications OR mobile applications. This is ideal for official web and mobile apps for your project because you can simplify the authorization workflow by ONLY asking a user for their username and password, as opposed to redirecting them to your site, etc.

What this means is that if you have built your own OAuth service (login.yoursite.com), and then created your own OAuth client application, you could use this grant type to authenticate users for your native Android, iPhone, and web apps.

But here’s the catch: ONLY YOUR native web / mobile applications can use this method! Let’s say you are Google. It would be OK for you to use this method to authenticate users in the official Google Android and iPhone apps, but NOT OK for some other site that uses Google login to authenticate people.

The reason here is this: by using the password credentials grant type, you’ll essentially be collecting a username and password from your user directly. If you allow a third-party vendor to do this, you run the risk that they’ll store this information and use it for bad purposes (nasty!).

Here’s how it works:

1. An anonymous user visits your website or opens your mobile app.
2. They want to log into your site / app using their identity (stored in the OAuth service that you created).
3. They input their username and password into your site / app, and you then validate this information via an API call and receive an access token.
4. You can these use this access token to actually retrieve this user’s information.

## How to Use The Password Credentials Gran Type
You’ll basically create an HTML form of some sort on your login page that accepts the user’s credentials — typically username and password.

You’ll then accept the user’s credentials, and POST them to your identity service using the following request format:

    POST https://login.blah.com/oauth/token?grant_type=password&username=xxx&password=xxx&client_id=xxx
 
You’ll then receive an access token in the response which you can use to make real API calls to retrieve the user’s information from your OAuth service.