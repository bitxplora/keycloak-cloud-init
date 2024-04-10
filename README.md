# keycloak-cloud-init
A cloud-init yaml file that enables boostraping of LXD vm with Keycloak server instance for development and testing

---

## Get Started
To launch a LXD vm with an instance of Keycloak server to enable you to develop and test application integration with Keycloak Authentication and
Authorization server.

- `lxc launch ubuntu:jammy keycloak-vm --config=user.user-data="$(cat ./keycloak.yaml)" --vm`


### Things to note or adjust to your need:
- IP or fqhn of the PostgreSQL database to use
- The database should be in a different vm, this preserves data. So you can throw keycloak-vm away for a new one.
- The database name in this config is keycloakdb, ensure it is created.
- The database user, the owner of keycloakdb is keycloak
- The database password in this config is "password", ensure it matchs that of "keycloak" user above.
