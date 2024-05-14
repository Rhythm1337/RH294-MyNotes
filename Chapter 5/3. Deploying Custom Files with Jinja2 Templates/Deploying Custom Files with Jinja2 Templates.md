# Jinja2
## What is Jinja2 
It is a modern day templating language for Python developers.
## How it works
We have **ansible.builtin.template** module that reads your **jinja2** template file, processes the **jinja2** language and renders the final product. This final product is then installed to your inventory host.

***template.j2 < --- (1.read) --- ansible.builtin.template --- (2.render) --- > rendered file --- (3.installed) --- inventory host***

## Why should you use Jinja2
Declarative architecture, you can declare in a very dynamic way, Inside of Jinja2 you can reference variables and you can then associate values for those variables on a per inventory host basis.

## Simple Example
### Make a file named hello.j2 
hello.j2
```
1. # {{ ansible_managed }} 
2. {# this is a comment #}
3.
4. Hello, I am {{ inventory_hostname }}
```
### Explanation per line
1. **ansible_managed** is a special variable and we use # in at the start so its interpreted as a literal
2. this is how you comment a line
3. empty line
4. variable **inventory_hostname** will be replaced/rendered by the **ansible.builtin.template** module with the actual value associated by the inventory host.

### Making the playbook
playbook.yml
```
---
- name: Play to demonstrate the basics of jinja2
  hosts: servera.lab.example.com
  become: false

  tasks:

    - name: Ensure j2 is rendered and installed
      ansible.builtin.template:
        src: hello.j2
        dest: /var/tmp/hello
```


