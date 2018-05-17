# concourse-launch

Running concourse containers into an ubuntu vm

## Install and start

```
$ vgrant up
```

## Concourse Webui

AfterWhile go to http://192.168.97.10:8080/

## Fly

You must download and install fly binary in your workstation (go to the concourse webui).
After that, you can login to the concourse runned with (default user and password !)
```
fly -l lite login -u concourse -p changeme -c http://192.168.97.10:8080
```
