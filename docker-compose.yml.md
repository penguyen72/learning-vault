A tool used to help define and manage multi-container [[Docker]] applications.

If you have a set of services that work together such as a web application, database, etc, you can define each service in the `docker-compose.yml` file and it will run these services together.

It automatically creates a default network for your containers to communicate with each other. You don't need to manually setup networking between containers.

It also makes running scripts and commands easier.