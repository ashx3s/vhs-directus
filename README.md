# README

Instructions for configuring directus with supabase and deploying on Render. Also some notes on comparisons to a regular npm install, a docker install, and an install without supabase.

## Directus Deployed to Render

- Use default database

### Steps

---

## Supabase + Directus 

- Supabase handles client side users and is managed from directus
- Directus handles admin side users

### Env => Directus Docker Configured in Render

- **benefit** cms setup doesn't touch desktop

#### Steps

1. set up new web service deployed from docker
2. add this image `directus/directus:latest`
3. add cms environment variables
        - Admin email - default login to cms
        - Admin password -default password to login to cms
4. add database environment variables:
        - Database Host – The IP address for your database.
        - Port – Port number your database is running on.
        - Database Name – Name of your existing database.
        - Database User – Name of existing user in database.
        - Database Password – Password to enter database.


### Env => Directus NPM Project in Git Deployed to Render

- **benefit** no new tooling

- **issue** could not authenticate admin user
    - [ ] posible fix -- reproduce and verify admin envs are added

#### Steps
1. [Documented here](https://supabase.com/partners/integrations/directus)
2. Hide .env and node modules from github
3. push to github
4. deploy to render
5. add .env file to render deployment

---

## Not good ideas

### Env => Directus Docker configured on Desktop

- **benefit** no local db running
- **drawback**  new tooling
- **drawback** no real benefit to doing this step if the above one works
