# The Client Credentials Grant Type

The client credentials grant type is meant to be used for application code.

You’ll want to use the client credentials grant type if you are building an application that needs to perform non-user related tasks. For instance, you might want to update your application’s metadata — read in application metrics (how many users have logged into your service?) — etc.

What this means is that if you’re building an application (like a background process that doesn’t interact with a user in a web browser), this is the grant type for you!

Here’s how it works:

1. Your application makes a request to the identity provider’s API service using it’s application credentials.
2. It receives an access token back, which can be used to make API requests.

## How to Use The Client Credentials Gran Type
You’ll fire off a single API request to the identity provider that looks something like this:

    POST https://login.blah.com/oauth/token?grant_type=client_credentials&client_id=xxx&client_secret=xxx
 
You’ll then receive an access token in the response which you can use to make real API calls to retrieve information from the identity provider’s API service.

**NOTE:** The **client_id** and **client_secret** stuff you see in the above examples are provided by the identity provider. When you create a Facebook or Google app, for instance, they’ll give you these values.