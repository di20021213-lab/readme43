### Задание 1

1. Установите **eCryptfs**.
2. Добавьте пользователя cryptouser.
3. Зашифруйте домашний каталог пользователя с помощью eCryptfs.


*В качестве ответа  пришлите снимки экрана домашнего каталога пользователя с исходными и зашифрованными данными.*

#### Решение
Установка eCryptfs
```
sudo apt install ecryptfs-utils
```

Создание пользователя cryptouser
```
sudo adduser --encrypt-home   cryptouser
```
!https://ibb.co/JFkbvgZd)

!https://ibb.co/B2yq2Tcq)


### Задание 2

1. Установите поддержку **LUKS**.
2. Создайте небольшой раздел, например, 100 Мб.
3. Зашифруйте созданный раздел с помощью LUKS.

*В качестве ответа пришлите снимки экрана с поэтапным выполнением задания.*

#### Решение
Устанавливаем gparted cryptsetup (LUKS)
```
apt install gparted cryptsetup
```
![https://ibb.co/LhpWpzDr)

Добавляем через Virtual Box диск на 100 MiB

Подготавливаем раздел (тип luks2)
```
sudo cryptsetup -y -v --type luks2 luksFormat /dev/sdb
```

!https://ibb.co/NMdV2GG)

Открываем устройство /dev/sdb и задаем ему имя cryptodisk
```
sudo cryptsetup luksOpen /dev/sdb cryptodisk
```



Форматируем раздел
```
sudo dd if=/dev/zero of=/dev/mapper/cryptodisk
```

```
sudo mkfs.ext4 /dev/mapper/cryptodisk
```



Монтируем открытый раздел
```
mkdir .secret
```

```
sudo mount /dev/mapper/cryptodisk .secret/
```

Завершение работы
```
sudo umount .secret
```

```
sudo cryptsetup luksClose cryptodisk
```
