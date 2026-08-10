# SINGLE SIGN-ON (SSO) — SAML AND OIDC
========================================

## 1. SSO FUNDAMENTALS
-------------------
Single Sign-On (SSO) is an authentication approach that allows a user to
authenticate with a central Identity Provider (IdP) and then access multiple
trusted applications without entering credentials separately for each one.

Key components:
- User: The person trying to access an application.
- Identity Provider (IdP): Manages digital identities and authenticates users.
  Examples: Okta, Microsoft Entra ID, OneLogin, Google.
- Service Provider (SP): The application/service the user wants to access.
  In modern OIDC terminology, this is often called the Relying Party (RP).
- Protocol: Defines how authentication/identity information is exchanged.

Important distinction:
- Authentication = "Who are you?"
- Authorization = "What are you allowed to do?"

SSO mainly addresses authentication. Authorization is then determined by
the application using trusted identity information, roles, groups, scopes,
and its own access-control policies.


## 2. SAML
--------
SAML = Security Assertion Markup Language.

SAML is an XML-based standard commonly used for enterprise SSO. The IdP
authenticates the user and sends a SAML assertion to the Service Provider.

Typical SAML flow:

    User
      |
      | 1. Requests application
      v
    Service Provider (SP)
      |
      | 2. Redirects/requires authentication
      v
    Identity Provider (IdP)
      |
      | 3. User authenticates
      |
      | 4. IdP creates SAML assertion
      v
    Service Provider (SP)
      |
      | 5. SP validates assertion
      v
    User gets access

What is the SAML assertion?
- An XML-based security statement issued by the IdP.
- It can contain identity/authentication-related information and attributes.
- The SP validates the assertion before establishing the user's application
  session.

Simple memory:
SAML -> XML -> SAML assertion -> enterprise SSO


## 3. OIDC
--------
OIDC = OpenID Connect.

OIDC is an authentication protocol/layer built on top of OAuth 2.0.
It is commonly used for modern web applications, mobile applications,
single-page applications, and APIs.

OIDC answers:
"Who is the authenticated user?"

OIDC commonly uses an ID token, which is usually a JWT.

Typical OIDC flow:

    User
      |
      | 1. Opens application
      v
    Client / Relying Party (RP)
      |
      | 2. Redirects user to IdP
      v
    Identity Provider (IdP)
      |
      | 3. User authenticates
      |
      | 4. Authorization/OIDC response
      |    including an ID token
      v
    Client / RP
      |
      | 5. Validates the ID token
      v
    User gets access

The ID token:
- Is commonly a JWT.
- Contains identity-related claims.
- Can include claims such as subject/user ID, issuer, audience,
  expiration, name, or email, depending on the provider and scopes.
- Is intended to tell the client about the authenticated user.

Simple memory:
OIDC -> authentication -> ID token -> commonly JWT


## 4. OAUTH 2.0
------------
OAuth 2.0 is an authorization framework.

Its main question is:
"What is this application allowed to access?"

OAuth is NOT the same as authentication.

Example:
A user authorizes an application to access certain Google Drive data
without giving the application the user's Google password.

OAuth commonly uses access tokens.

Important relationship:

    OAuth 2.0 = authorization framework
             |
             v
    OIDC = authentication layer built on OAuth 2.0

Therefore:
- OAuth -> authorization
- OIDC -> authentication using OAuth 2.0
- OIDC commonly uses a JWT-formatted ID token


## 5. SAML VS OIDC
---------------
SAML:
- XML-based
- SAML assertion
- Common in enterprise SSO
- Identity Provider -> Service Provider
- Often used for enterprise SaaS and established business applications

OIDC:
- Built on OAuth 2.0
- JSON/HTTP based
- ID token commonly formatted as JWT
- Common in modern web/mobile applications and APIs
- Identity Provider -> Relying Party/client


## 6. IMPORTANT: SAML AND JWT
-------------------------------------------------------
 remember:

    SAML-based SSO:
    IdP -> SAML assertion -> SP

    OIDC-based authentication:
    IdP -> ID token (commonly JWT) -> Client/RP

An Identity Provider can support multiple protocols. For example, the
same IdP may use SAML for one application and OIDC for another.

JWT is independent of SAML. However, an IdP can issue JWTs when an OIDC
flow is used.


## 7. ID TOKEN VS ACCESS TOKEN
---------------------------
ID token:
- Used by OIDC for authentication.
- Tells the client about the authenticated user.
- Commonly a JWT.

Access token:
- Used to access protected resources/APIs.
- Associated with OAuth 2.0 authorization.
- Its exact format is not required to be JWT.

Do not say:
"JWT is always an access token."

A JWT is a token FORMAT. It can be used for different purposes depending
on the protocol and system design.


## 8. EXAMPLE: CONTINUE WITH GOOGLE
--------------------------------
When a modern application offers "Continue with Google", OIDC is commonly
used for authentication.

Conceptually:

    User
      |
      v
    Application
      |
      v
    Google (IdP)
      |
      | authenticate
      v
    OIDC ID token (commonly JWT)
      |
      v
    Application
      |
      v
    User authenticated

This is different from an organization configuring enterprise SAML SSO
between its IdP and an application.


## 9. INTERVIEW-READY DEFINITIONS
------------------------------
SSO:
"Single Sign-On is an authentication approach that allows a user to
authenticate with a central Identity Provider and access multiple trusted
applications without logging in separately to each application."

Identity Provider:
"An Identity Provider is a system that manages digital identities and
performs authentication."

SAML:
"SAML, or Security Assertion Markup Language, is an XML-based standard
commonly used for enterprise SSO. The IdP authenticates the user and sends
a SAML assertion to the Service Provider, which validates it and grants
access."

OIDC:
"OpenID Connect is an authentication protocol built on OAuth 2.0. It is
commonly used by modern web and mobile applications and uses an ID token,
commonly formatted as a JWT, to provide identity information to the client."

OAuth 2.0:
"OAuth 2.0 is an authorization framework that allows an application to
obtain limited access to protected resources without requiring the user
to share their password with that application."


10. EASY MEMORY MAP
-------------------

    SSO
     |
     +--------------------+
     |                    |
    SAML                 OIDC
     |                    |
   XML                 OAuth 2.0
   Assertion              |
     |                    |
    SP                ID Token
                          |
                        JWT


## 11. KEY POINTS TO REMEMBER
---------------------------
1. IdP authenticates the user.
2. SP/RP is the application the user wants to access.
3. SAML commonly uses XML-based assertions.
4. OIDC is built on OAuth 2.0.
5. OIDC uses an ID token, commonly a JWT.
6. OAuth 2.0 is mainly about authorization.
7. Authentication asks "Who are you?"
8. Authorization asks "What can you access/do?"
9. SAML does not automatically produce a JWT.
10. JWT is a token format, not a replacement name for OIDC.
11. The same IdP can support both SAML and OIDC for different applications.
