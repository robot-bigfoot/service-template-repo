# service-template-repo
Template repo for services

## Setup

* Create a repo from this template
* Populate the `service` file with the appropriate details (see `{replace}` regions) or modify to your needs (see other examples below)
* Update `run.sh` to do what you want
* `chmod +x run.sh` to make it executable
* `sudo ln -s {path}/service /lib/systemd/system/{service_name}.service`
* `sudo systemctl enable {service_name}.service` to enable

## Sample `service` file for one-hit command

    [Unit]
    Description={desc}
    After=multi-user.target

    [Service]
    Type=idle
    ExecStart=sh {path}/run.sh

    [Install]
    WantedBy=multi-user.target
