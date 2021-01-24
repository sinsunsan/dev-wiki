# Scaleway

{% embed url="https://www.scaleway.com/en/docs/activate-rescue-mode-on-my-server/" %}

{% embed url="https://askubuntu.com/questions/91286/how-to-see-log-to-find-a-boot-problem" %}

[https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-18-04-source](https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-18-04-source)  
  
restart mongo db

```text
sudo systemctl start mongod.service
```

The order of volume matter : the first volume is by default the startup volume 

### How to know if a DB is empty 

* Conect to mongo using `mongo`
* Type `show dbs;`
* It will output all dbs and  their space on disk

### Start Mongodb from default location 

```text
mongod --dbpath=/var/lib/mongodb
```

>

