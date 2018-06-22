# Partner Training - LATAM

This document is created to help you get everything setup on your computer to start using and demoing Kong EE. These interactive demos are designed to give you a basic idea of Kong and what it can do. It is by no means all inclusive, but will take you through the basics and show you how to quickly get up and started with Kong.


##  Initial Software Setup

### Getting Docker Setup

These sessions will all be using Docker. Docker makes doing demos quick and painless
  - [Docker for Mac](https://docs.docker.com/docker-for-mac/install/#install-and-run-docker-for-mac)
  - [Docker for Windows 10](https://store.docker.com/editions/community/docker-ce-desktop-windows)<br />
We distribute Kong and Kong's license through a third party tool called Bintray. We have created a shared account for you to use for this training. Please get in touch with your Kong contact person if you do not have access before the training starts.

Let's pull the images so we have a local copy of them for testing. First, get your datastore. For these demos, we'll be using Postgres, but Cassandra would work just as well.
``
docker pull postgres:9.6
``

Now, let's pull a copy of Kong EE. This will require your Bintray access information<br />
```
docker login -u demo-user@kong -p <API_KEY> kong-docker-kong-enterprise-edition-docker.bintray.io
docker pull kong-docker-kong-enterprise-edition-docker.bintray.io/kong-enterprise-edition:0.32-alpine
```

Great! Now we have the images you need. Let's set up a local variable for our license file. This will avoid needing to type it in every time. Simply run the following command, substituting the data from your license file
```
export KONG_LICENSE_DATA='{"license":{"signature":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx","payload":{"customer":"Example Company","license_creation_date":"2018-05-31","product_subscription":"Kong Enterprise Edition","admin_seats":"5","support_plan":"Platinum","license_expiration_date":"2018-06-14","license_key":"xxxxxxxxxxxxxxxxxx_xxxxxxxxxxxxxxxxxxx"},"version":1}}'
```
### Other Handy Tools we use Often

While cURL will work perfectly using Kong, it's not the most human friendly when doing a demo for potential customers. To get a better visual response, we will use a tool called [HTTPie]
(https://httpie.org/).
#### Installing HTTPie
```
### macOS
brew install httpie

### Debian, Ubuntu, etc.
apt-get install httpie

### CentOS, RHEL
$ yum install httpie

### Windows
## First, ensure you have an up-to-date version of pip and setuptools
pip install --upgrade pip setuptools
pip install --upgrade httpie
```

Assuming everything installed and pulled without issue, you're ready to get started.

## Next Steps

Now, you have everything installed on your local machine you will need to use Kong. I'll be back in another session to do some demos with you, but if you want to take an early look, please visit [https://github.com/john-paul-keenan/kong](https://github.com/john-paul-keenan/kong)
