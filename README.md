# ansible

Установите nginx на серверы rrobin, web1, web2. На серверах web1, web2, Nginx должен работать на порту 8080 и выдавать свою страницу, сообщающую вам, на каком сервере вы находитесь. На циклическом сервере Nginx должен загружать серверы web-1 и web-2 в циклическом режиме. Каждый сервер имеет одинаковый вес. Вся установка и настройка программного обеспечения должны выполняться с использованием сценария Ansible. Выложите все файлы для этой задачи на Github и напишите ReadMe с экранами работоспособности и инструкциями по запуску скрипта Ansible.

Простым языком:

Начало
---
Перед установкой нам нужен пользовательский образ Redos732.
При этом надо обязательно отредактировать VagrantFile, указав путь к вашей ssh-папке

ssh_pub_key = File.readlines("/home/ismail/.ssh/id_rsa.pub").first.strip

Установка
---
При запуске наших вииртуальных машин с помощью Vagrant ,необходимо убедиться что вы используете последнюю версию vagrant:

`vagrant up`

Начало действий:

`ansible-playbook nginx.yml`

После установки
---
Если в сводке нет ошибок, вы можете перейти к http://192.168.11.113 чтобы проверить, работает ли ваш балансировщик

Это должно выглядеть примерно так:
![](https://github.com/ismailtez/ansible2/blob/main/web1.jpg)


Попробуйте обновить страницу, чтобы увидеть, меняются ли цифры на странице. Если они не изменятся, попробуйте также использовать CTRL + F5 для обновления кэша

И другая страница:
![](https://github.com/ismailtez/ansible2/blob/main/web2.jpg)
