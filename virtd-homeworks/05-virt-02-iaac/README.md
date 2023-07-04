Задача 1:
Опишите основные преимущества применения на практике IaaC-паттернов.
Какой из принципов IaaC является основополагающим?

Ответ:
Скорость разворачивания инфраструктуры, автоматизация. Легкость масштабируемости, обеспечение версионности и стабильности.

Создание или настройка инфраструктуры как процесс написания кода для ПО


Задача 2:
Чем Ansible выгодно отличается от других систем управление конфигурациями?
Какой, на ваш взгляд, метод работы систем конфигурации более надёжный — push или pull?

Ответ:
Ansible использует SSH инфраструктуру, в то время как другие (Saltstack, Chef) требуют установки специального PKI-окружения

pull - нет единой точки отказа и хранения данных доступа


Задача 3
Установить на личный компьютер:
VirtualBox
Vagrant
Ansible
Приложить вывод команд установленных версий каждой из программ, оформленный в markdown.

Ответ:
r2d2@MacBook-Pro-Andrew ~ % VAGRANT version
Installed Version: 2.3.7
Latest Version: 2.3.7


r2d2@MacBook-Pro-Andrew ~ % terraform -version
Terraform v1.5.2
on darwin_amd64

r2d2@MacBook-Pro-Andrew ~ % virtualbox -help   
Oracle VM VirtualBox VM Selector v7.0.0
Copyright (C) 2005-2022 Oracle and/or its affiliates

r2d2@MacBook-Pro-Andrew ~ % ansible  --version              
ansible [core 2.15.1]
  config file = None
  configured module search path = ['/Users/r2d2/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/local/Cellar/ansible/8.1.0/libexec/lib/python3.11/site-packages/ansible
  ansible collection location = /Users/r2d2/.ansible/collections:/usr/share/ansible/collections
  executable location = /usr/local/bin/ansible
  python version = 3.11.4 (main, Jun 20 2023, 16:59:59) [Clang 14.0.3 (clang-1403.0.22.14.1)] (/usr/local/Cellar/ansible/8.1.0/libexec/bin/python3.11)
  jinja version = 3.1.2
  libyaml = True






