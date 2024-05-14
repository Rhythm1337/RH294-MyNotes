# Jinja2
## How it works
We have **ansible.builtin.template** module that reads your **jinja2** template file and processes the **jinja2** language and it renders a final product and then that final product gets installed to your inventory host.

***template.j2 < --- (1.read) --- ansible.builtin.template --- (2.render) --- > rendered file --- (3.installed) --- inventory host***

## Why should you use Jinja2
Declarative architecture, you can declare in a very dynamic way
Inside of Jinja2 you can reference variables and you can then associate values for those variables on a per inventory host basis

> Ricardo's ymls are very confusing so i am not typing it xD
