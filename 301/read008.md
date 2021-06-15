# Read: Class 08 Readings: APIs

## [API Design Best Practices](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design)

1. What does REST stand for?

   - Representational State Transfer

1. REST APIs are designed around a.

   - resources, which are any kind of object, data, or service that can be accessed by the client.

1. What is an identifer of a resource? Give an example.

   - which is a URI that uniquely identifies that resource. For example, the URI for a particular customer order might be: https://adventure-works.com/orders/1

1. What are the most common HTTP verbs?

   - he most common operations are GET, POST, PUT, PATCH, and DELETE.

1. What should the URIs be based on?

   - should be based on nouns (the resource) and not verbs (the operations on the resource).
   - https://adventure-works.com/orders // Good
   - https://adventure-works.com/create-order // Avoid

1. Give an example of a good URI.

   - https://adventure-works.com/orders // Good

1. What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?

   - sending a lot of small requests
   - It is a bad thing that exposes a large number of small resources.

1. What status code does a successful GET request return?

   - HTTP status code 200 (OK).

1. What status code does an unsuccessful GET request return?

   - 404 (Not Found).

1. What status code does a successful POST request return?

   - HTTP status code 201 (Created).

1. What status code does a successful DELETE request return?
   - HTTP status code 204

## [API Design Best Practices](https://regexr.com/)

1. How would you match your name using RegEx?
   - /mahmoud\b/g

## Things I want to know more about

- RegEx
