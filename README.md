---

# 4people
Тестовое задание для 4people

Есть условный свежеустановленный сервер с убунту 20.04 на борту.
Там 2 сетевых интерфейса (на одном белый ip, на другом серый).
Есть ssh доступ по белому ip по логину (root) + паролю.
Серый ip не известен.
Написать сценарий автоматизации, который сделает следующее:
Добавит несколько (больше 2х) пользователей на сервер с их ключами
Даст всем новым пользователям возможность повышения прав до root
Добавит несколько стандартных пакетов в систему (vim, iotop, tcpdump)
Отключит в ssh доступ по паролю (оставит доступ только по ключам)
Сменит стандартный порт ssh
Установит redis и запустит его на сером интерфейсе
Настроит доступ на сервер и в редис только по серой сети
Запретит любой доступ на сервер по белой сети, кроме ответов на ping

people_sshport: 2222                                                                                                                    # Defailt ssh port
people_userpassword: $6$rounds=656000$DocDoc$C5UtYBsBJEPyjx6H0SgFn8.x2UEZnKXByEEsXq3VCP9AyTPu5xWVB7BuJFUSvnBPI/8FCsnnIXrqZx4MPUzSv0     # Default user password Qwe12345
people_userpath: /etc/ansible/4people/roles/4people/files                                                                               # Default user names/user keys directory
                                                                                                                                        # Создание пользователей управляется файлами в директории people_userpath,
                                                                                                                                        # имена файлов - имена пользователей
                                                                                                                                        # открытые ключи пользователй - внутри файлов соответственно
                                                                                                                                        # сколько файлов - столько пользователей
people_utils:                                                                                                                           # Default applications for install
  - vim
  - iotop
  - tcpdump
