# Oauth

reference - https://youtu.be/t18YB3xDfXI (wonderfully explained! go check it out!)

so this is my idea about Oauth -

Oauth is a way using which an external application can get permission to access resources/data on your behalf

## some important things

there are 4 people (stakeholders?) involved in Oauth -
    1) resource owner
    2) client
    3) authorization server
    4) resource server

who are these people?
    - resource owner - you!
    - client - the external application that wants to get permission to access resources/data on your behalf
    - authorization server - the entity that confirms that you are you and also gives access to the external application
    - resource server - the entity where all the resources/data reside that the external application wants to access

these are some important terms that you may want to keep in mind -

    1) redirect/callback URL
    2) response type
    3) scope
    4) consent
    5) client id
    6) client secret
    7) authorization code
    8) access token

what do the above terms mean?

    - redirect URI/callback URL - this is where the authorization server will redirect the resource owner after granting permission to the client
    - response type - type of information that the client expects to receive
    - scope - the resources/data that the client wants to access
    - consent - whether or not the resoruce owner wants to give the client access to resoruces/data mentioned in the scope
    - client id - used to identify the client with the authorization server
    - client secret - a secret password that only the client and the authorization server know
    - authorization code - short lived temporary code that the authorization server sends back to the client
    - access token - it is the key that the client can use to communicate with the resource server. obtained by the client by sending the authorization code back to the authorization server along with the client secret



## oauth2.0 flow

you (resource owner) want some third party application (client) to perform some action on your behalf.

the third party application (client) will redirect you to the authorization server and will include the client id, redirect uri, response type and one or more scopes that it needs  with its request

the authorization server will veryfi if it is you who has initiated the request and may ask you to login if your session has expired

the authorization server will then present you the consent form based on the scopes that are requested by the client

you have the opportunity to grant or deny the permission


if you grant the permission, the authorization server redirects you to the redirect URI that was sent by the client along with the authorization code

the client then contacts the authorization server directly (not from the resource owner's browser) and sends its client id, client secret and the authorization code

the authorization server verifies the data and responds with an Access Token, if all the information is correct

the access token is then used by the client to send requests to the resoruce server

the resoruces server verifies the access token and if it is valid, it responds to the client with all the resources or data that it was asking for (these resources and data must be in the scope that the client had provided)
