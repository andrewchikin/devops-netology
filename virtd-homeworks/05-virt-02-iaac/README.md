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


Задание 4:
Следуя командам в видеолекции на команде vagrant provision я получал ошибку:

Vagrant gathered an unknown Ansible version:
and falls back on the compatibility mode '1.8'.
Alternatively, the compatibility mode can be specified in your Vagrantfile:
https://www.vagrantup.com/docs/provisioning/ansible_common.html#compatibility_mode
Поиск по ошибке выдал https://stackoverflow.com/questions/47423488/vagrant-ansible-python3
где предлагают указать в Vagrantfile compatibility_mode = '2.0' в раздел node.vm.provision "ansible" do |setup|

При таком запуске команды vagrant provision
Я получил:
1. [WARNING]: ansible.utils.display.initialize_locale has not been called, this
may result in incorrectly calculated text widths that can cause Display to
print incorrect line lengths
2. TASK [Adding rsa-key in /root/.ssh/authorized_keys] ****************************
An exception occurred during task execution. To see the full traceback, use -vvv. The error was: If you are using a module and expect the file to exist on the remote, see the remote_src option
fatal: [server1.netology]: FAILED! => {"changed": false, "msg": "Could not find or access '~/.ssh/id_rsa.pub' on the Ansible Controller.\nIf you are using a module and expect the file to exist on the remote, see the remote_src option"}
...ignoring
Остальные команды отработали без ошибок

**r2d2@MacBook-Pro-Andrew vagrant % vagrant ssh**
Welcome to Ubuntu 20.04.6 LTS (GNU/Linux 5.4.0-144-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Wed 05 Jul 2023 07:43:03 PM UTC

  System load:  0.48               Users logged in:          0
  Usage of /:   13.9% of 30.34GB   IPv4 address for docker0: 172.17.0.1
  Memory usage: 27%                IPv4 address for eth0:    10.0.2.15
  Swap usage:   0%                 IPv4 address for eth1:    192.168.56.11
  Processes:    142

 * Introducing Expanded Security Maintenance for Applications.
   Receive updates to over 25,000 software packages with your
   Ubuntu Pro subscription. Free for personal use.

     https://ubuntu.com/pro


This system is built by the Bento project by Chef Software
More information can be found at https://github.com/chef/bento
Last login: Wed Jul  5 19:42:15 2023 from 10.0.2.2

**vagrant@server1:~$ docker ps**
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

**vagrant@server1:~$ docker version**
Client: Docker Engine - Community
 Version:           24.0.2
 API version:       1.43
 Go version:        go1.20.4
 Git commit:        cb74dfc
 Built:             Thu May 25 21:52:22 2023
 OS/Arch:           linux/amd64
 Context:           default

Server: Docker Engine - Community
 Engine:
  Version:          24.0.2
  API version:      1.43 (minimum version 1.12)
  Go version:       go1.20.4
  Git commit:       659604f
  Built:            Thu May 25 21:52:22 2023
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          1.6.21
  GitCommit:        3dce8eb055cbb6872793272b4f20ed16117344f8
 runc:
  Version:          1.1.7
  GitCommit:        v1.1.7-0-g860f061
 docker-init:
  Version:          0.19.0
  GitCommit:        de40ad0
vagrant@server1:~$ 









