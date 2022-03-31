# New-Relic
New Relic Installation on Instance

https://docs.newrelic.com/docs/infrastructure/install-infrastructure-agent/linux-installation/install-infrastructure-monitoring-agent-linux/

----------------------------------
How to install New Relic Agent on instance


1> Create the configuration file and add your license key:

   #echo "license_key: YOUR_LICENSE_KEY" | sudo tee -a /etc/newrelic-infra.yml

2> Determine the distribution version number:
   
   #cat /etc/lsb-release

3> Enable New Relic's GPG key.

   #curl -s https://download.newrelic.com/infrastructure_agent/gpg/newrelic-infra.gpg | sudo apt-key add -

4> Add the infrastructure monitoring agent repository:

   #printf "deb https://download.newrelic.com/infrastructure_agent/linux/apt xenial main" | sudo tee -a /etc/apt/sources.list.d/newrelic-infra.list

5> Refresh the repositories:

   #sudo apt-get update

6> Install the newrelic-infra package in root (default), privileged user, or unprivileged user mode. For more information on each running mode, see Linux agent running modes.

   #sudo apt-get install newrelic-infra -y  or  sudo yum install newrelic-infra -y



*Done*
Check the status of new relic service
#sudo systemctl <start|stop|restart|status> newrelic-infra
