# Simple Jupyterhub docker-image with admin-panel
## What's differrent:

 - Added admin-user
 - By-defaul admin-user can create system users
 - Admin user can be setup by environment-variable durring the container start
 - Root-user password can be modified by ROOTPASSWD env variable
 - Default ROOT passwd if "teashop"
 - Created new image with spark, scala, pyspark
 - Added orcale-client for using oracle-libraries


## How can i use it:
- `docker pull tesslime/jhubadm `
- `docker run -d --name my-jhubadm-name  -p 8000:8000 tesslime/jhubadm`
- Open in your browser this URL: http://<machine-host-ip/dns>:8000
- Default admin-username: `tesslime` password: `teashop`

## How can i setup my own admin-user/password:
- `docker run -d --name my-jhubadm-name  -p 8000:8000 -p 222:22 -e ADMUSER=my_custom_user -e ADMPASS=my_custom_password -e ROOTPASSWD=my_custom_root_password tesslime/jhubadm`

## What if i need to store data on my host-machine:
- In this image data stored in default users folders in "/home" directory, so you just need the command below.

- `docker run -d --name my-jhubadm-name -v /host/machine/dir:/home -p 8000:8000 tesslime/jhubadm`
