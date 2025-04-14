# Application Programming Interfaces (APIs)

An Application Programming Interface(API) is a set of commands, functions, protocols, and objects that programmers can use to create software or interact with an external system.

API Endpoint is the location of the data that you want to retrieve from an external system.

API Request is the request that you make to an external system to fetch the necessary data.

We have to install the `requests` package to be able to make API Requests.

We can get the data from an API using the `request.get()` function. The `request.get()` function will return a response code on execution.

Response codes -

1. 1XX - Hold On.
2. 2XX - Here You Go - Request successful.
3. 3XX - Go Away - Request denied - You don't have permission to access this data.
4. 4XX - You Screwed Up.
5. 5XX - I Screwed Up - The server you've made a request to screwed up.
6. Where X can be any number from 0 - 9.