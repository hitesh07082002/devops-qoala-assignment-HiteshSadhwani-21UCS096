# DevOps Assignment Report

## Issues Identified

During the setup and configuration of this multi-service application, several issues were encountered across various components. Here’s a summary of the key issues identified:

1. **Python Dockerfile Issues**
   - Incorrect **working directory**: Set to `/appp` instead of `/app`.
   - **Package name typo**: Misspelled as `netiface` instead of `netifaces`.
   - **Port exposure**: Written in string format as `"eight thousand"` instead of a numeric format (`8000`).
   - **Python command typo**: Written as `"pythn"` instead of `"python"`.

2. **Python Application Issues**
   - Flask initialization used an incorrect syntax (`_name_` instead of `__name__`).
   - Port configuration syntax required adjustments to ensure proper formatting.

3. **Nginx Dockerfile Issues**
   - **Base image tag typo**: Written as `"latests"` instead of `"latest"`.
   - Incorrect **file paths** due to typos.
   - Port configuration written as `"eighty"` instead of `80`.
   - **Daemon directive** error: Needed `"daemon off;"` to run in the foreground.

4. **Nginx Configuration Issues**
   - Missing semicolon after `worker_processes`, which led to syntax errors.
   - Incorrect path for `mime.types` file.
   - **Worker connections** setting misspelled as `worker_conections`.

5. **Docker Compose Issues**
   - Port mappings in string format caused deployment issues.
   - Missing build contexts prevented the services from building correctly.
   - Syntax errors in network configuration led to connectivity problems between services.

## Resolution Steps

Each of these issues was resolved through careful debugging and corrections. Here’s a breakdown of the steps taken:

1. **Python Dockerfile and Application Fixes**
   - Set `WORKDIR` to the correct directory: `/app`.
   - Fixed package name typo to `netifaces` for proper dependency installation.
   - Changed port exposure to the numeric format `8000`.
   - Corrected the `python` command spelling and replaced `_name_` with `__name__` in Flask initialization.

2. **Nginx Dockerfile and Configuration Fixes**
   - Updated base image to `nginx:latest` for stability.
   - Corrected all file path typos.
   - Standardized port to numeric `80` for compatibility.
   - Fixed the daemon directive to `"daemon off;"` for correct foreground operation.
   - Added missing semicolons and corrected `mime.types` path.
   - Corrected `worker_connections` spelling to avoid syntax errors.

3. **Docker Compose Fixes**
   - Updated port mappings to use numeric format for consistency.
   - Added missing build contexts to ensure services were built from the correct Dockerfiles.
   - Resolved syntax errors in network configuration to enable proper communication between `nginx` and `python-app`.

4. **Testing and Verification**
   - Successfully built the Docker images using `docker-compose` with the corrected configurations.
   - Verified that all containers started up without issues and that the web application was accessible.
   - Confirmed Nginx proxy functionality by checking request routing and responses.
   - Monitored logs to verify successful handling of requests and error-free operation.

Through these adjustments, all issues were resolved, and the application is now running smoothly with correct service communication and request handling.

## Cloud Deployment

As an additional step, I deployed the application to a cloud server to make it accessible externally. The deployment is live and can be accessed using the following IP address:

- **Endpoint**: [http://13.61.11.104](http://13.61.11.104)

This setup has been tested for accessibility and functionality, providing a complete verification of the deployment.
