# 50 Ansible Interview Questions & Answers

1. **What is Ansible?**
   Ansible is an open-source automation tool used for configuration management, application deployment, and task automation.

2. **What is the difference between Ansible and Puppet/ Chef?**
   Ansible is agentless, while Puppet and Chef require agents installed on managed nodes. Ansible uses SSH for communication, whereas Puppet and Chef use their own agents.

3. **What is an Ansible playbook?**
   An Ansible playbook is a YAML file that defines a series of tasks to be executed on remote hosts. It describes the desired state of the system.

4. **How do you install Ansible?**
   ```bash
   sudo apt-get install ansible # For Ubuntu/Debian
   sudo yum install ansible # For CentOS/RHEL
   ```

5. **What is an Ansible role?**
   An Ansible role is a collection of tasks, variables, files, and templates organized in a predefined structure to simplify the management of configurations and applications.

6. **How do you run an Ansible playbook?**
   ```bash
   ansible-playbook <playbook_file.yml>
   ```

7. **What is an Ansible inventory?**
   An Ansible inventory is a file that lists the managed hosts and groups them according to different criteria. It can be static or dynamic.

8. **How do you specify which hosts to run Ansible commands against?**
   You can specify hosts using the `-i` option followed by the path to the inventory file or by using the `--limit` option followed by the host or group name.

9. **What is the default location for the Ansible configuration file?**
   The default location for the Ansible configuration file is `/etc/ansible/ansible.cfg`.

10. **How do you check the syntax of an Ansible playbook without executing it?**
    ```bash
    ansible-playbook <playbook_file.yml> --syntax-check
    ```

11. **How do you install a package using Ansible?**
    ```yaml
    - name: Install package
      yum:
        name: <package_name>
        state: present # or latest, absent, etc.
    ```

12. **How do you restart a service using Ansible?**
    ```yaml
    - name: Restart service
      service:
        name: <service_name>
        state: restarted # or started, stopped, reloaded, etc.
    ```

13. **How do you copy a file to a remote host using Ansible?**
    ```yaml
    - name: Copy file
      copy:
        src: /path/to/local/file
        dest: /path/to/remote/file
    ```

14. **What is Ansible Vault used for?**
    Ansible Vault is used for encrypting sensitive data such as passwords or keys within Ansible playbooks or files.

15. **How do you encrypt a file using Ansible Vault?**
    ```bash
    ansible-vault encrypt <file_name>
    ```

16. **How do you decrypt a file encrypted with Ansible Vault?**
    ```bash
    ansible-vault decrypt <file_name>
    ```

17. **How do you pass variables to an Ansible playbook?**
    ```bash
    ansible-playbook -e "var=value" playbook.yml
    ```

18. **How do you loop over a list of items in Ansible?**
    ```yaml
    - name: Loop over items
      debug:
        msg: "Item is {{ item }}"
      loop:
        - item1
        - item2
    ```

19. **How do you define a variable in Ansible?**
    ```yaml
    vars:
      my_var: value
    ```

20. **How do you include a task file in an Ansible playbook?**
    ```yaml
    - include: tasks/main.yml
    ```

21. **How do you register the output of a command in Ansible?**
    ```yaml
    - name: Run command and register output
      shell: <command>
      register: result
    ```

22. **How do you access registered variables in Ansible?**
    ```yaml
    - debug:
        msg: "Output is {{ result.stdout }}"
    ```

23. **How do you debug in Ansible?**
    ```yaml
    - debug:
        msg: "Debug message"
    ```

24. **How do you ignore errors in Ansible?**
    ```yaml
    - command: <command_that_might_fail>
      ignore_errors: yes
    ```

25. **How do you run tasks only on specific operating systems in Ansible?**
    ```yaml
    - name: Run only on Debian-based systems
      debug:
        msg: "This task runs only on Debian-based systems"
      when: ansible_os_family == "Debian"
    ```

26. **How do you install multiple packages in Ansible?**
    ```yaml
    - name: Install multiple packages
      yum:
        name:
          - package1
          - package2
        state: present
    ```

27. **How do you create a directory using Ansible?**
    ```yaml
    - name: Create directory
      file:
        path: /path/to/directory
        state: directory
    ```

28. **How do you set up passwordless SSH for Ansible?**
    ```bash
    ssh-keygen -t rsa
    ssh-copy-id <user>@<host>
    ```

29. **How do you check if a file exists using Ansible?**
    ```yaml
    - name: Check if file exists
      stat:
        path: /path/to/file
      register: file_info
    ```

30. **How do you conditionally execute tasks based on file existence in Ansible?**
    ```yaml
    - name: Task executes only if file exists
      debug:
        msg: "File exists"
      when: file_info.stat.exists
    ```

31. **How do you perform a rolling update with Ansible?**
    ```yaml
    - name: Rolling update
      hosts: all
      serial: 1
    ```

32. **How do you set up a cron job using Ansible?**
    ```yaml
    - name: Set up cron job
      cron:
        name: "My cron job"
        minute: "0"
        hour: "*/2"
        job: "some_command"
    ```

33. **How do you manage users and groups using Ansible?**
    ```yaml
    - name: Add user
      user:
        name: username
        state: present
    ```

34. **How do you manage file permissions using Ansible?**
    ```yaml
    - name: Set file permissions
      file:
        path: /path/to/file
        mode: 0644
    ```

35. **How do you manage SELinux using Ansible?**
    ```yaml
    - name: Set SELinux mode
      selinux:
        policy: targeted
        state: enforcing
    ```

36. **How do you manage firewalls using Ansible?**
    ```yaml
    - name

: Open port in firewalld
      firewalld:
        port: 80/tcp
        state: enabled
    ```

37. **How do you perform a dry run of an Ansible playbook?**
    ```yaml
    - name: Dry run
      debug:
        msg: "This is a dry run"
      check_mode: yes
    ```

38. **How do you manage Docker containers using Ansible?**
    ```yaml
    - name: Manage Docker container
      docker_container:
        name: my_container
        image: nginx
        state: started
    ```

39. **How do you manage AWS resources using Ansible?**
    ```yaml
    - name: Provision EC2 instance
      ec2:
        key_name: my_key
        instance_type: t2.micro
        image: ami-12345678
        state: present
    ```

40. **How do you manage Azure resources using Ansible?**
    ```yaml
    - name: Provision Azure VM
      azure_rm_virtualmachine:
        resource_group: my_rg
        name: my_vm
        vm_size: Standard_DS1_v2
        image: UbuntuLTS
        admin_username: azureuser
        admin_password: Password123!
        state: present
    ```

41. **How do you manage variables in Ansible Tower?**
    You can define variables in inventories, projects, or job templates.

42. **How do you schedule jobs in Ansible Tower?**
    You can schedule jobs using job templates in Ansible Tower's web interface.

43. **How do you scale Ansible Tower?**
    You can add more Tower nodes to an existing cluster or set up a load balancer in front of multiple Tower instances.

44. **How do you manage secrets in Ansible Tower?**
    You can use Ansible Vault or integrate Tower with external secret management systems like HashiCorp Vault.

45. **How do you monitor Ansible Tower?**
    You can monitor Tower using its built-in dashboard or integrate it with external monitoring tools.

46. **How do you configure custom credentials in Ansible Tower?**
    You can define custom credential types and add them to job templates.

47. **How do you handle errors in Ansible Tower job runs?**
    You can set up notifications for failed jobs or configure retry and failure policies.

48. **How do you integrate Ansible with version control systems?**
    You can use Git to manage Ansible playbooks and roles.

49. **How do you manage secrets in Ansible Tower?**
    You can use Ansible Vault to encrypt sensitive data in Tower.

50. **How do you troubleshoot Ansible playbooks?**
    You can use the `-vvv` option to enable verbose output or review logs in Tower for failed jobs.