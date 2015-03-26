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
