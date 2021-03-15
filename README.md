common_git-commit
=========

This role will commit modified files inside a git repo.

Requirements
------------

All dependencies will appear on requirements.yml file

Role Variables
--------------

    - name: Git commit
      include_role:
        name: common_git-commit
      vars:
        git_chdir: "/{{ host_root_dir }}/{{ repos_dir }}/{{ item.value.repo_git_name }}/{{ item.value.repo_project }}{{ item.value.repo_name }}"
        git_branch: "{{ item.value.repo_git_branch|default('master') }}"
        git_repo_name: "{{ item.value.repo_name }}"
        git_comment: "Created new kapsule cluster for int"

    true, false
    with_commits: true

Dependencies
------------

All dependencies will appear on requirements.yml file

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - common_git-commit

License
-------

BSD

Author Information
------------------
Made by @sergi-canas
