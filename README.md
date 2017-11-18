# gce_hosts
Ansible module to retrieve all hosts for a project

## Usage:
+ Place module in the /library folder of your project
+ Add a task:
```
- name: get hosts
  gce_hosts:
    instance_pattern: "web-severs-.*"
    service_account_email: "dev@null.com"
    credentials_file: "my_creds.json"
    project_id: "my_project"
    zone: "europe-west1-d"
  register: gce_host_instances
  
- debug: msg={{gce_host_instances}}
```
instance_pattern is optional - without it, all hosts are returned.
