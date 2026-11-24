# Gateway service

Single entry point (port 8080).


`/api/auth/**` Auth Service \
`/api/users/**`, `/api/cards/**` User Service \
`/api/orders/**`, `/api/items/**` Order Service 

Security: `/api/auth/login`, `/api/auth/register`, `/api/auth/refresh` are open.

Everything else needs a valid JWT (checked with the public key from the Auth Service JWKS).

A valid `Authorization` header is passed on to the service unchanged.

Settings (environment variables, defaults are for running everything on localhost):
`AUTH_JWKS_URI`, `AUTH_SERVICE_URL`, `USER_SERVICE_URL`, `ORDER_SERVICE_URL`.

Docker image: `docker build -t gateway-service:latest   .` \

After build all services run general docker image `docker compose up -d`
