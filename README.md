# Dynatrace-Update-Ansible

This Ansible role installs and configures a Dynatrace Update of the [Dynatrace Application Monitoring](http://www.dynatrace.com/en/products/application-monitoring.html) solution.

## Download

The role is available via:

- [Ansible Galaxy](https://galaxy.ansible.com/Dynatrace/Dynatrace-Update)
- [GitHub](https://github.com/Dynatrace/Dynatrace-Update-Ansible)

## Description

Download a Dynatrace Update from [downloads.dynatracesaas.com](downloads.dynatracesaas.com) and place the artifact as ```dynatrace-update.dtf``` in the role's ```files``` directory from where it will be picked up during the installation. Alternatively, you can make the Dynatrace Update available at an HTTP, HTTPS or FTP resource and point the installation script to the right location via the `dynatrace_update_file_url` attribute, see below.

## Role Variables

As defined in ```defaults/main.yml```:

| Name                             | Default                                         | Description |
|----------------------------------|-------------------------------------------------|-------------|
| *dynatrace_update_file_name*     | dynatrace-update.dtf                            | The file name of the Dynatrace Update in the role's ```files``` directory. |
| *dynatrace_update_file_url*      | http://localhost/dynatrace/dynatrace-update.dtf | A HTTP, HTTPS or FTP URL to the Dynatrace Update in the form (http\|https\|ftp)://[user[:pass]]@host.domain[:port]/path. |
| *dynatrace_update_user_name*     | admin                                           | The username of a Dynatrace user that has the *Manage Update* permission. |
| *dynatrace_update_user_password* | admin                                           | The password of a Dynatrace user that has the *Manage Update* permission. |
| *dynatrace_update_role_name*     | Dynatrace.Dynatrace-Update                      | The actual name of this role in an [Ansible Playbook's](http://docs.ansible.com/playbooks.html) ```roles``` directory. |

## Example Playbook

```
- hosts: all
  roles:
    - role: Dynatrace.Dynatrace-Update
```

## Testing

We use [Test Kitchen](http://kitchen.ci) to automatically test our automated deployments with [Serverspec](http://serverspec.org) and [RSpec](http://rspec.info/):

1) Install Test Kitchen and its dependencies from within the project's directory:

```
gem install bundler
bundle install
```

2) Run all tests

```
kitchen test
```

By default, we run our tests inside [Docker](https://www.docker.com/) containers as this considerably speeds up testing time (see `.kitchen.yml`).

## Additional Resources

### Blogs

- [How to Automate Enterprise Application Monitoring with Ansible](http://apmblog.dynatrace.com/2015/03/04/how-to-automate-enterprise-application-monitoring-with-ansible/)
- [How to Automate Enterprise Application Monitoring with Ansible - Part II](http://apmblog.dynatrace.com/2015/04/23/how-to-automate-enterprise-application-monitoring-with-ansible-part-ii/)

### Presentations

- [Automated Deployments (of Dynatrace) with Ansible](http://www.slideshare.net/MartinEtmajer/automated-deployments-with-ansible)
- [Test-Driven Infrastructure with Ansible, Test Kitchen, Serverspec and RSpec](http://www.slideshare.net/MartinEtmajer/testing-ansible-roles-with-test-kitchen-serverspec-and-rspec-48185017)

## Problems? Questions? Suggestions?

This offering is [Dynatrace Community Supported](https://community.dynatrace.com/community/display/DL/Support+Levels#SupportLevels-Communitysupported/NotSupportedbyDynatrace(providedbyacommunitymember)). Feel free to share any problems, questions and suggestions with your peers on the Dynatrace Community's [Application Monitoring & UEM Forum](https://answers.dynatrace.com/spaces/146/index.html).

## License

Licensed under the MIT License. See the LICENSE file for details.
[![analytics](https://www.google-analytics.com/collect?v=1&t=pageview&_s=1&dl=https%3A%2F%2Fgithub.com%2FdynaTrace&dp=%2FDynatrace-Update-Ansible&dt=Dynatrace-Update-Ansible&_u=Dynatrace~&cid=github.com%2FdynaTrace&tid=UA-54510554-5&aip=1)]()
