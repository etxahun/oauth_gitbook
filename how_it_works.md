# How it Works

There are **4** separate **modes of OAuth**, which are called **grant types**. Each mode serves a different purpose, and is used in a different way. Depending on what type of service you are building, you might need to use one or more of these grant types to make stuff work.
1. The Authorization Code Grant Type
2. The Implicit Grant Type
3. The Password Credentials Grant Type
4. The Client Credentials Grant Type

## Know What Grant Type to Use
If you’re building an application that integrates with another provider’s login stuff (Google, Facebook, etc.) — be sure to use the correct grant type for your situation.

If you’re building….

* A server-side web app: use authorization code.
* A client-side web app (or mobile app): use implicit.
* An integration with an OAuth service you built yourself, use password credentials.
* An application that doesn’t interact with user data: use client credentials.

## Don’t Use OAuth2 for Sensitive Data
If you’re building an application that holds sensitive data (like social security numbers, etc.) — consider using OAuth 1.0a instead of OAuth2 — it’s much more secure.

## When to Use OAuth
You should only use OAuth if you actually need it. If you are building a service where you need to use a user’s private data that is stored on another system — use OAuth. If not — you might want to rethink your approach!

There are other forms of authentication for both websites and API services that don’t require as much complexity, and can offer similar levels of protection in certain cases.

Namely: HTTP Basic Authentication and HTTP Digest Authentication.

