План такой:

- Установить Ansible на Debian.

- Настроить SSH-доступ к самому себе (localhost).

- Проверить, что Ansible видит хост.

- Написать первый playbook.

1. Обновить систему
```sudo apt update && sudo apt upgrade -y```

2. Установить Python и pip - Ansible написан на Python. На Debian 12 и новее есть нюанс — система защищает свой Python от установки пакетов через pip (PEP 668). Есть два пути: через apt (проще) и через pip в venv (гибче).
    - проверить версию Debian.
   Debian 11 (Bullseye): В репозитории доступен Ansible 2.10.7. Эта версия полностью совместима с Python 3.8.
   Debian 12 (Bookworm): Здесь доступна более новая версия — Ansible 7.7.0. Она также будет работать на Python 3.8, так как Ansible 5/6/7 требуют как минимум Python 3.8:<br>
   ```cat /etc/debian_version```
    - проверить Python:<br>
      ```python3 --version```

3. Установка Ansible
   1.  установка через apt:<br>
      ```sudo apt install -y ansible```
   2. через pip:<br>
   ```sudo apt install -y python3-pip python3-venv
   python3 -m venv ~/ansible-venv
   source ~/ansible-venv/bin/activate
   pip install --upgrade pip
   pip install ansible
   ``` 
   Каждый раз перед работой в Ansible нужно запускать venv:<br>
   ```source ~/ansible-venv/bin/activate```

4. Проверка версии:<br>
 ```ansible --version```

