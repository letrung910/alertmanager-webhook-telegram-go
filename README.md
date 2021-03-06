# Alertmanager webhook for Telegram (GO Version)

![Go](https://github.com/nopp/alertmanager-webhook-telegram-go/workflows/Go/badge.svg)
![Docker Image CI](https://github.com/nopp/alertmanager-webhook-telegram-go/workflows/Docker%20Image%20CI/badge.svg)
![Code scanning - action](https://github.com/nopp/alertmanager-webhook-telegram-go/workflows/Code%20scanning%20-%20action/badge.svg)

Python Version (https://github.com/nopp/alertmanager-webhook-telegram-python) 

Go version 1.13.9

## INSTALL

* go get -d .

Alertmanager configuration example
==================================

	receivers:
	- name: 'telegram-webhook'
	  webhook_configs:
	  - url: http://ipGoAlert:9229/alert
	    send_resolved: true

Running on docker
=================
    git clone https://github.com/nopp/alertmanager-webhook-telegram-go.git
    cd alertmanager-webhook-telegram-go/docker/
    docker build -t awt-go:0.1 .

    docker run -d --name awt-go-bot \
    	-e "bottoken=telegramBotToken" \
    	-e "chatid=telegramChatID" \
    	-p 9229:9229 awt-go:0.1
