# Teams

## Managing Webhooks : For managing Teams with webhooks, we need to do the following steps;

-Steps
1. Open Teams application
1. Select the desired channel that we need to connect
1. Once done, there will be three horizontal dots when clicked leads to three drop down options
1. In that, Select "Connectors" option
1. This will leads to a new window, In that select incoming webhooks
1. On the right side of that, we can see a configure button. Click that.
1. After clicking, Fill up the name of the webhook and upload an image related to the topic.
1. And then click, "Create"
1. Copy the generated URL and paste it on to the desired destination inorder to connect Teams via webhook.


# Nagios

# Grafana

-Steps
1. Download the rpm file from -  wget https://dl.grafana.com/oss/release/grafana-5.4.3-1.x86_64.rpm . Cross check if this is the latest version
1. Install the rpm via yum-  sudo yum localinstall grafana-5.4.3-1.x86_64.rpm 
1. Start the service - sudo service grafana-server start
1. Reload the daemon - systemctl daemon-reload
1. Check the status and see whether its on active state - systemctl status grafana-server
1. Enable the grafana service - sudo service grafana-server enable

# MS Teams Webhook Notifications
