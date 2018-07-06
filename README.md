# Ansible Automated Testing Demo
This is a sample project to demonstrate different technologies and best practices relating to automating testing in Ansible


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


