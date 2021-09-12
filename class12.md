# Which HTTP Status Code to Use for Every CRUD App
#### The HTTP specification defines many status codes we can use when responding to our clients. Some APIs only use the most basic codes and define their own error signaling mechanisms on top of it; others want to make full use of HTTPs collection of codes to tell their clients what’s going on. If you belong to the latter, this article is for you. This guide walks through the various CRUD operations and which status codes you should be using for clean API design.

## HTTP Status Codes
#### A status code is a number higher than 100 and smaller than 600 that is part of a HTTP response. The first digit defines the class of the status. A status code comes with a reason phrase. The code is for programmatic recognition the phrase is for humans to understand what happened.

#### Every status code has to follow these two rules, even custom ones (yes the status codes are extensible).

## Status Classes
### 100 - 199
#### These are informational status codes; they usually tell the client that the header part of the request has been received and the server will try to comply with a transmission demand of the client. Like using a different protocol or telling the client that its request will fail before they start sending the body.

### 200 - 299
#### These are the success codes. They tell the client that its request was accepted. In case of asynchronous processing of a request (202), this doesn’t mean the request was successfully processed only that it met all validation requirements at the time of sending.

### 300 - 399
#### These are redirection codes. They tell the client that the resource they are requesting isn’t available at the expected location anymore. This can have multiple reasons, be temporary or permanent, but the client has to issue a request to the new location.

### 400 - 499
#### These are the client error codes. They are all about invalid requests a client sent to a server. There are several causes to this, timeouts, wrong URI, missing authentication, etc. A client is sending incorrect input and should confirm the input parameters are correct before retrying the request.

### 500 - 599Permalink
#### These are the server error codes. Often they indicate problems with overwhelmed servers or unreachable servers behind proxies, but sometimes they can be directly related to client requests that trigger error exceptions on the server. These errors can be temporary or permanent. Usually it’s best for the client to retry the same request.

### Custom ClassesPermalink
#### Custom classes, that is, classes above 599 aren’t permitted but used by some services anyway. For API designers, they are relevant as bad examples. API client creators, however, have to deal with them.

## CRUD (Create, Read, Update, Delete)
### The CRUD model defines the most basic API actions for persistent storage. Create, read, update, and delete. They make up the lions-share of API endpoints. Let’s see which status codes meet their requirements.

## CREATE
#### The create action is usually implemented via HTTPs POST method. In RESTful APIs, these endpoints are used to create new resources or access tokens.
### Status Codes

#### 200 OK - It’s the basic status code to tell the client everything went good. Since we don’t create endpoint accessible resource when creating an access token, we can use 200 as a status for that action.
#### 201 Created - The most fitting for Create operations. This code should signal backend-side resource creation and come along with a Location header that defines the most specific URL for that newly created resource. It’s also a good idea to include appropriate representation of the resource or at least one or more URLs to that resource in the response body.
#### 202 Accepted - Often used for asynchronous processing. This code tells the client that the request was valid, but its processing will finish sometime in the future. The response body should include an URL to the finished resource with some information about when it will be available, or an URL to some monitoring endpoint that tells the client when the resource is available.
#### 303 See Other - Like the 202 code but using a Location header field in response to informing the client about the location of the created resource or an endpoint that lets the client check for the status of the creation process. Some clients follow the status codes of the Redirect-class automatically. This code is usually only used for POST requests.
## READ
#### The read action gets implemented via HTTPs GET method and used to fetch resource representations. Asynchronous responses aren’t much of a thing here, because the reason for asynchronous processing is often that the resource doesn’t exist yet and has to be created, so it’s a create action anyway.
### Status Codes

#### 200 OK - Most of the read actions will be answered with a 200 OK status.
#### 206 Partial Content - This code is useful for lists of content that are too big to be delivered in one response. It has to be used with a Range header field in the request. Usually, this header field defines the byte-range the backend should send to the client, but the unit can be freely assigned as long as both sides understand it.
#### 300 Multiple Choices - This redirect is used if there are multiple representations for one resource and the client (or its user) has to choose one of them.
#### 308 Permanent Redirect - This tells the client to use another URL to access the resource and not use the current URL anymore. It’s helpful when we have multiple endpoints for one resource, but don’t want to implement reading from all of them.
#### 304 Not Modified - Is used like 200 but without a body, so the client will be redirected to its locally cached representation from a previous read.
#### 307 Temporary Redirect - When the URL to a resource could change in the future, and the client should always ask the current URL before accessing the real one.
## UPDATE
#### An update can be implemented with an HTTP PUT or PATCH method. The difference lies in the amount of data the client has to send to the backend.

#### PUT requires the client to send an entire representation of a resource to update it. (Replace the old one with the new one)

#### PATCH requires the client only send parts of the representation of the resource to update it. (Add, update or delete these parts in the old version)

### Status Codes

#### 200 OK - This is the most appropriate code for most use-cases.
#### 204 No Content - A proper code for updates that don’t return data to the client, for example when just saving a currently edited document.
#### 202 Accepted - If the update is done asynchronous, this code can be used. It should include an URL to access the updated resource or an URL to check if the update has been succeeded. It can also include an estimation of how long the update will take.

## DELETE
#### The delete action can be implemented with the HTTP DELETE method.

### Status Codes

#### 200 OK - Some people think a delete function of any kind should return the deleted element, so a representation of the deleted element can be included in the response body.
#### 204 No Content - The most fitting status code for this case. It’s better to reduce traffic and simply tell the client the deletion is complete and return no response body (as the resource has been deleted).
#### 202 Accepted - If the deletion is asynchronous and takes some time, which is the case in distributed systems, it can be appropriate to return this code with some information or URL to tell the client when it will be deleted.

# Conclusion
#### The HTTP creators thought about many status codes when designing it and even added a bunch of new ones over the years. If they’re used correctly they can help to improve developer experience greatly by leveraging automatic redirect follows of clients and explaining what happened more clearly.