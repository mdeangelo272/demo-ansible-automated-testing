## Introduction

* Automated testing has been a pattern in software development for decades
* With Infrastructure as Code and Configuration Management, the need has arisen for Automated tests of server configurations
* There are many frameworks available to help implement automated tests

---

## Why Implement Automated Tests

* Automated tests help increase the robustness of your solutions
* They reduce human error and increase repeatability
* They decrease the time to validate system configurations
* They ensure compliance across all nodes and workloads

---

## Robust Playbook Primer

* Use check mode as a sanity check
* Use Block/Rescue statements for exception handling
* Use the `wait_for` module to ensure that a port is active
* Use the `meta` module to flush handlers when needed

---

## Automated Tests Using Ansible
* Ansible playbooks represent a declarative desired state, thus the successful execution of a task is a great indication of the state of the system
* Use the `assert` module to ensure the state of the system
* Use the `fail` module with a `when` condition to assert the state of a module

---

## Common Pattern
* register a variable that represents state
    * Should **NOT** change the state of the system
    * if you use `command` or `shell`, use `change_when: false` to ensure proper report
* Validate state using the test module (`assert` or `fail`)
  * it is recommend to use the `ignore_errors: yes` so that the entire test suite runs

---

## Other Frameworks and Tools
* Testing Frameworks
    * Testinfra - Python
    * goss - YAML
    * InSpec - Ruby
    * ServerSpec - Ruby
* Orchestration Frameworks
    * Molecule - Python 
    * Kitchen - Ruby

---

## Contact Me

* email: iam@mdeangelo272.me
* Website: https://mdeangelo272.me/
* GitHub: https://github.com/mdeangelo272
* LinkedIn: https://www.linkedin.com/in/mdeangelo272/

---

* MISC Topics
  * How to lay out the tests
    * tasks vs playbooks
    * targeting servers
    * why testing multi-role projects can be hard
    * activating tests via tags, environment variables, etc
  * Test should not alter the state of the system in most cases
* 
