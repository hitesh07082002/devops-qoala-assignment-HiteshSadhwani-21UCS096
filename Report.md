# DevOps Assignment Report

## Issues Identified

1. **Python Dockerfile Issues**
   - WORKDIR incorrectly set to `/appp`
   - Missing 's' in package name `netiface`
   - Port exposure written as string "eight thousand"
   - Python command misspelled as "pythn"

2. **Python Application Issues**
   - Flask variable syntax using single underscores (`_name_`)
   - Port configuration needed proper formatting

3. **Nginx Dockerfile Issues**
   - Base image tag written as "latests"
   - File paths had typos
   - Port written as "eighty"
   - Daemon directive incorrect

4. **Nginx Configuration Issues**
   - Missing semicolon after worker_processes
   - Mime types path incorrect
   - Worker connections misspelled

5. **Docker Compose Issues**
   - Port mappings using string format
   - Build contexts missing
   - Network configuration syntax errors

## Resolution Steps

1. **Python Configuration Fixes**
   - Corrected WORKDIR to `/app`
   - Fixed package name to `netifaces`
   - Changed port to numeric 8000
   - Corrected Python command spelling
   - Fixed Flask variable to `__name__`

2. **Nginx Configuration Fixes**
   - Updated base image to `nginx:latest`
   - Corrected all file paths
   - Changed port to numeric 80
   - Fixed daemon directive to `daemon off;`
   - Added missing semicolons
   - Corrected mime.types path
   - Fixed worker_connections spelling

3. **Docker Compose Fixes**
   - Standardized port mappings
   - Added proper build contexts
   - Corrected network configuration

4. **Testing and Verification**
   - Built images successfully using docker-compose
   - Verified container startup
   - Confirmed web application accessibility
   - Validated Nginx proxy functionality
   - Checked logs for successful requests

All issues have been resolved, and the application is now running successfully with proper communication between services and correct request handling.
