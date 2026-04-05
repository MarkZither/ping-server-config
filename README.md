# ping-server-config

A simplified PingFederate server profile repository for use with Docker Compose.
Inspired by [pingidentity-server-profiles](https://github.com/pingidentity/pingidentity-server-profiles/tree/master/baseline/pingfederate).

## Structure

```
server-profile/
  pingfederate/
    instance/
      server/
        default/
          data/
            admin-users.xml
```

## Quick Start

1. Accept the [Ping Identity DevOps agreement](https://devops.pingidentity.com/how-to/devopsRegistration/) and obtain your DevOps credentials.
2. Run the following command to start PingFederate:

```sh
docker compose up -d
```

3. Access the PingFederate admin console at https://localhost:9999/pingfederate/app
   (PingFederate uses a self-signed certificate by default — accept the browser warning for local development.)
   - Username: `administrator`
   - Password: `2FederateM0re`

## Notes

- The `server-profile/` directory is mounted into the container at `/opt/in`, which PingFederate uses to apply configuration on startup.
- This profile provides a minimal setup with a single administrator user. No clusters, hooks, or templates are included.
- **Security note:** The password in `admin-users.xml` is stored in plain text and is intended for **development/testing only**. Do not use this profile in production. For production, use encrypted passwords or an external secret management solution.