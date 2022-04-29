# Тестовый стенд
## Подготовка
1. Установите [VirtualBox](https://www.virtualbox.org/)
2. Установите [Vagrant](https://www.vagrantup.com/)
>Если не удается скачать с официального сайта, дополнительная [ссылка](https://disk.yandex.ru/d/TEfUN1-AtoByPA)
3. Установите [Git](https://git-scm.com/)

 ## Запуск стенда
 1. Откройте терминал
 2. Скопируйте себе репозиторий
 ```shell
$ git clone https://github.com/artem-shestakov/practice.git
 ```
 3. Перейдите в директорию со скаченным репозиторием
 4. Создайте виртуальные машины(ВМ) с использованием `Vagrant`
 >Перед запуском необходимо зайти в настрйоки сетей `VirtualBox`. Открыть `Файл->Менеджер сетей хоста...` и проверить созданные сети. По умолчанию используется `vboxnet0` с адресацией `192.168.56.0/24`. Если имя или адресация отличаются,сделайте соответствующие правки в `Vagrantfile`, переменная `NODES` и/или в параметре `c.vm.network name` в настройках ВМ.
 ```shell
 # Запустить все ВМ
 $ vagrant up

# Запустить конкетную ВМ по названию
# Название ВМ можно взять из Vagranfile
$ vagrant up <название_виртуальной машины>
 ``` 

## Дополнительные команды 
* Информация по запущенным ВМ
```shell
$ vagrant status
```
* Подключение к ВМ с помощью `Vagrant`
```shell
$ vagrant ssh <название_виртуальной машины>
```
* Подключение по `SSH`
>SSH ключ `private_key` лежит в директории `.vagrant/machines/<название_виртуальной машины>/virtualbox`
```shell
$ ssh -i 
```
* Выключение ВМ
```shell
$ vagrant halt
```
* Удаление ВМ
```shell
# Удалить все ВМ
$ vagrant destroy

# Удалить конкетную ВМ по названию
# Название ВМ можно взять из Vagranfile
$ vagrant destroy <название_виртуальной машины>
 ``` 