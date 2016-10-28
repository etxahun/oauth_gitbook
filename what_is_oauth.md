# What is OAuth?

At a high level overview, OAuth is not an API nor a service; it is an **open standard for authorization** and any developer can implement it.

**OAuth** is a standard that applications (and the developers who love them) can use to provide client applications with “secure delegated access”. OAuth works over HTTP and authorizes Devices, APIs, Servers and Applications with access tokens rather than credentials, which we will go over in depth below.

There are two versions of OAuth: **OAuth 1.0a** and **OAuth2**. These specifications are completely different from one another, and cannot be used together: there is no backwards compatibility between them.

Which one is more popular? Nowadays (at this time of writing), OAuth2 is no doubt the most widely used form of OAuth. So from now on, whenever I write just “OAuth”, I’m actually talking about OAuth2.

# What does OAuth do?

OAuth is basically a **protocol that supports authorization workflows**. What this means is that it gives you a way to ensure that a specific user has permissions to do something.

OAuth isn’t meant to do stuff like validate a user’s identity — that’s taken care of by an Authentication service. Authentication is when you validate a user’s identity (like asking for a username / password to log in), whereas authorization is when check to see what permissions an existing user already has.

Just remember that **OAuth is a protocol for authorization**.