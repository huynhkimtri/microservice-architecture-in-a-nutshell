# Microservice Architecture in a Nuttsell
The repo for the fast and easy guide to the Microservice architecture

Some advantages:
- working with small components creates room to scale the service in separate parts
- each services has it own autonomy and provides flexibility on the technology that will be used
- productivity and velocity can increase by allowing different development teams to wokr on vairous components simltaneously without impacting each other
- development teams are focused and organized around the bussiness functionality
- developers have the freedom to work more independenlty and autonomously without having a dependencey on other teams

Problems:
- face secutiry challenges in a distributed architecture
- microservices may expose internal API to communicate with each other -> this requires more effort and attention to secure it
- nothing is shared between them -> sharing user context is harder and must be explicitly handled from on microservice to another

Authentication and Authorization
-> bold terms will come to mind when talking about securing applications
	Authentication -> WHO YOU ARE?
	the identity of the user is checked to provide access to system
	so the user needs to supply login details to authenticate

	Authorization -> WHAT YOU CAN DO?
