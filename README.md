# Smokeping Configures

This is some my collected configures for smokeping.

## Run

```
git clone git@github.com:peihsinsu/smokeping-configd.git config.d
```

The you can use docker for run these config...

```
docker run -d -p 80:80 -v $PATH-TO-CONFIG/config.d:/etc/smokeping/config.d peihsinsu/smokeping
```

## Note

As your running server changed, the configured server ip need to change. Please change the "General" file ip setting...

```
$ vi config.d/General
.... (skip)
cgiurl   = http://your-ip-address/smokeping/smokeping.cgi
... (skip)

```

If you want to keep the data that can be used next container start, you can mount the "/var/lib/smokeping" path from your persistance disk.

```
mkdir ~/dockerws/smokeping/data
chmod -R 777 ~/dockerws/smokeping/data

docker run -d -p 80:80 \
  -v ~/dockerws/smokeping/config.d:/etc/smokeping/config.d \
  -v ~/dockerws/smokeping/data:/var/lib/smokeping \
  peihsinsu/smokeping
```
