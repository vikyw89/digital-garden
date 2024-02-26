---
{"dg-publish":true,"permalink":"/authentication-and-authorization/"}
---

Authentication is about assigning role to request. 
- anonymous
	- unsigned user access
- user
	- signed in user access
- author / owner
	- signed in user access to resource they authored
- admin
	- signed in admin access

Authorization is about permission depending on the role.
- anonymous
	- probably read access to public resource only
- user
	- probably read access to public resource
	- read access to signed in user resource
	- write access to public user resource
- author / owner
	- read access to public resource
	- read access to owned resource
	- write access to public user resource
	- write access to owned resource
- admin
	- all access

Middlewares are usually used for authentication and authorization