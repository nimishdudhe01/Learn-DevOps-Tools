# Learning Docker

### So, What is Docker?
Docker is an open platform for developing, shipping, and running applications. Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. With Docker, you can manage your infrastructure in the same ways you manage your applications. By taking advantage of Docker's methodologies for shipping, testing, and deploying code, you can significantly reduce the delay between writing code and running it in production.

### What is a Container?
- A way to package applications with all necessary dependencies and configuration.
- Portable artifact, easily shared and moved around.
- Makes development and deployment more efficient.

### Where do containers live?
- Container Repository
- Private Repositories
- Public Repository for Docker (AKA Docker Hub)

## Motivation for Containers
### Development
Before Docker: "To get the development environment set up install Postgres, MongoDB, and run these 5 scripts. Oh wait, You're on Windows? Also Change These Configurations."
After Docker: "Run `docker compose up`."

### Deployment
Before Docker: "To deploy the applicaton, provision a server running Ubuntu, run this Ansible playbook to install the dependencies and configure the system, then copy the deployment binary and run it with these options."
After Docker: "Run this container image with these options."

## Evolution of Virtualization
### Bare Metal
- Hellish Dependency Conflicts.
- Low utilization efficiency.
- Large blast radius (the changes/issues of one application can direcly impace the performance of other applications)
- Slow Start Up and Shut Down Speed (minutes).
- Very slow provisioning & decommissioning (Hours to Days).

### Virtual Machines
- No Dependency Conflicts.
- Better utilization efficiency.
- Small blast radius.
- Faster startup and shutdown (minutes).
- Faster provisioning & decommissioning (minutes) (Used in Cloud Computing).

### Containers
- No Dependency Conflicts.
- Even Better Utilization efficiency.
- Small blast radius.
- Even faster startup and shutdown (seconds).
- Even faster provisioning & decommissioning (seconds).
- Lightweight enough to use in development.




