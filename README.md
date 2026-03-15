Задание 1
Установите eCryptfs.
Добавьте пользователя cryptouser.
Зашифруйте домашний каталог пользователя с помощью eCryptfs.
В качестве ответа пришлите снимки экрана домашнего каталога пользователя с исходными и зашифрованными данными.
# Решение
# Установка eCryptfs
sudo apt install ecryptfs-utils
Создание пользователя cryptouser
https://sun9-17.userapi.com/s/v1/ig2/Q8XLrm5UbnhhtwPAXbWUwFq4fzxlJDqlfeSCASJ_9UIZ816Ss_gKs5u5jGmgx6L2h3m_YDZnHMLC-q8PXjqZ1I26.jpg?quality=95&as=32x23,48x34,72x52,108x77,160x115,240x172,360x258,480x344,540x387,640x458,720x516,828x593&from=bu&cs=828x0
sudo adduser --encrypt-home   cryptouser
Задание 2
Установите поддержку LUKS.
Создайте небольшой раздел, например, 100 Мб.
Зашифруйте созданный раздел с помощью LUKS.
В качестве ответа пришлите снимки экрана с поэтапным выполнением задания.
