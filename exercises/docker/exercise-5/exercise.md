### Docker Workshop

#### **Exercises**

**Exercise 5: HDP Server** (15 minutes)
   - **Objective:** Run a HDP Server Docker container
   - **Steps:**
     - Pull the `hdp-docker-4.6.1` image: `docker pull nc-vra-008830.americas.progress.com:5000/hdp-docker-4.6.1:2057`
     - Run the container: `docker run -dt -p 9001:9001 -p 8080:8080 -p 8443:8443 -p 11443:11443 -p 8190:8190 -p 40501:40501 -p 11280:11280 -p 8282:8282 -e "ACCEPT_EULA=true" -e "HDP_EVAL=true" -e "HDP_ADMIN_PASSWORD=d2cadmin" -e "HDP_USER_PASSWORD=d2cuser" -v c:/docker/hdpshare:/hdpshare --hostname <your_host_name_or_ip_address> --name hdp-server hdp-docker-4.6.1:2057`
   - **Discussion Points:**
     - Explain the output
     - Concept of pulling images from private registry
     - Understand the environment variables, ports, volume mounts requirements of HDP Server