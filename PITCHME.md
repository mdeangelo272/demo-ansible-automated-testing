## Introduction


---

## Contact Me

* email: iam@mdeangelo272.me
* Website: https://mdeangelo272.me/
* LinkedIn: https://www.linkedin.com/in/mdeangelo272/
* GitHub: https://github.com/mdeangelo272

---

## Raw Notes
* Testing Methods
  * Using Ansible `assert` and `fail` modules
    * register variables
      * logic to capture data should **not** change state of system
      * use `changed_when: false` to avoid erroneous changed count
    * `assert` or `fail` based on registered data
      * Continuing on failed asserts/tests to execute all tests
      * use `ignore_errors: yes`
      * #todo: mkd - settle on yes/no vs true/false

  * Other Frameworks (As time permits)
    * Inspec - ruby
    * ServerSpec - ruby
    * Testinfra - python

* Where to test
  * Vagrant and Kitchen
  * Docker
  * Public Cloud
  * Actual infrastructure
    

* Best Practices
  * How to lay out the tests
    * tasks vs playbooks
    * targeting servers
    * why testing multi-role projects can be hard
    * activating tests via tags, environment variables, etc
  * Test should not alter the state of the system in most cases
* 
* Gotchas
  * include versus import and tags in the current version of Ansible
* Refs
  * [Ansible's Docs on Testing](https://docs.ansible.com/ansible/latest/reference_appendices/test_strategies.html)
  * Look at Ansible's Source Code tests
    * [Ansible Core Testing docs](https://docs.ansible.com/ansible/latest/dev_guide/testing.html)
* Misc
  * Testing custom modules is more important
  * code hardening vs automated tests
    * `wait_for` is a example of hardening


## Presentation Summary
An overview of how to implement automated tests to validate the state of systems provisioned using Ansible including best practices, common pitfalls, and various framework options.


# Setup
ansible-galaxy install -r requirements.yml

## Raw
* form data
```
db_type=MySQL&db_host=127.0.0.1%3A3306&db_user=gogs_db&db_passwd=gogs_db&db_name=gogs&ssl_mode=disable&db_path=data%2Fgogs.db&app_name=Gogs%3A+Go+Git+Service&repo_root_path=%2Fhome%2Fgit%2Fgogs-repositories&run_user=git&domain=localhost&ssh_port=22&http_port=3000&app_url=http%3A%2F%2Flocalhost%3A3000%2F&log_root_path=%2Fhome%2Fgit%2Fgogs%2Flog&smtp_host=&smtp_from=&smtp_email=&smtp_passwd=&enable_captcha=on&admin_name=&admin_passwd=&admin_confirm_passwd=&admin_email=

```

* Molecule
  * docker python lib changes with ansible version at 2.6
  * see molecule config file

