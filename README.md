# MPInstanceViewMiddleware: A middleware for EFB 

## Notice

**Middleware ID**: `catbaron.mp_instanceview`

**MPInstanceViewMiddleware** is a middleware of EFB enable instance view for articles of official accounts.

## How it works
This middleware generates a telegraph page for links sent by official accounts of wechat, which will enable the instance view. Thus you need a `access_token` (introduced later).

## Dependense
* Python >= 3.6
* EFB >= 2.0.0
* PyYaml
* bs4
* urllib3

## Install and configuration

### Install
```
git clone https://github.com/catbaron0/efb-mp-instanceview-middleware
cd efb-mp-instanceview-middleware
sudo python setup.py install
```

### Enable

Register to EFB
Following [this document](https://ehforwarderbot.readthedocs.io/en/latest/getting-started.html) to edit the config file. The config file by default is `$HOME/.ehforwarderbot/profiles/default`. It should look like:

```yaml
master_channel: foo.demo_master
slave_channels:
- foo.demo_slave
- bar.dummy
middlewares:
- foo.other_middlewares
- catbaron.mp_instanceview
```

You only need to add the last line to your config file.

### Configure the middleware

The config file by default is `$HOME/.ehforwarderbot/profiles/default/catbaron.mp_instanceview`.
Please create the config file if thers is not one. You need to have a telegraph token and save it here. You can get a token following [the document](https://telegra.ph/api#createAccount). The `access_token` is what you need.

```yaml
telegraph_token: TOKEN
```

### Restart EFB.
