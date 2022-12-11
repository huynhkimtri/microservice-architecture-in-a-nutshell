# Microservice Architecture in a Nuttsell
The repo for the fast and easy guide to the Microservice architecture

## Some advantages:
- working with small components creates room to scale the service in separate parts
- each services has it own autonomy and provides flexibility on the technology that will be used
- productivity and velocity can increase by allowing different development teams to wokr on vairous components simltaneously without impacting each other
- development teams are focused and organized around the bussiness functionality
- developers have the freedom to work more independenlty and autonomously without having a dependencey on other teams

## Problems:
- face secutiry challenges in a distributed architecture
- microservices may expose internal API to communicate with each other -> this requires more effort and attention to secure it
- nothing is shared between them -> sharing user context is harder and must be explicitly handled from on microservice to another

## Authentication and Authorization
-> bold terms will come to mind when talking about securing applications

### Authentication -> WHO YOU ARE?

The identity of the user is checked to provide access to system
so the user needs to supply login details to authenticate

### Authorization -> WHAT YOU CAN DO?

The process of verifying if the authenticated user is authorized to access sepecific information or be allowed to execute a certain operation -> which permissions the user has.

## Authentication Strategy in a MSA

There are several approaches:
- Authentication & Authorization on each service
	- Each microservices needs to imnplement its own indepenedent security and enforce it on each entry-point

- Global Authentication & Authorization Service
	- Dedicated microservice will handle authentication and authoriztion concerns
	- Each business service must authentiacte the request before processing it by downstreaming it to the authentication service

## Authentication Types: Stateful vs. Stateless

- In Stateful, the server will creates a session for the user after successfully authenticating -> the session id is then stored as a cookie in the user's browser and the user session store in the cache or database -> when the client tries to access the server with a given session id -> the server attemps to load the user session context for the session store -> check if the session is valid, and decieds if the client has to access the desired resource or rejects the request
- In Stateless, the user session will stores on the client side -> a cryptographic algorithm signs the user session to ensure the session data integrity and authority -> each time the client requests a resource from the server -> the server is reponsible for verifying the token claims sent as a cookie
