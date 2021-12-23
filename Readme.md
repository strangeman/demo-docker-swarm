# Hexlet Swarm Demo

## Пререквизиты

- Установленный Ansible
- Установленный [Vagrant](https://www.vagrantup.com/)

## Документация

- <https://docs.docker.com/engine/swarm/>
- <https://docs.docker.com/engine/reference/commandline/stack_deploy/>
- <https://docs.docker.com/compose/compose-file/compose-file-v3/>

## Как запустить

Ставим роли и коллекции из Ansible Galaxy

```bash
cd ansible
ansible-galaxy install -r roles/requirements.yml
```

Запускаем виртуалки:

```bash
vagrant init
vagrant up
```

При необходимости сбросить состояние виртуалки - перезапускаем Vagrant

```bash
vagrant destroy -f && vagrant up
```

## Как использовать

Зайти на виртуалки можно будет с помощью команды `vagrant ssh nodeX` (где X от 1 до 3)

Также они будут доступны по IP `192.168.56.2X` (где X также от 1 до 3)

Дальше можно будет инициализировать кластер руками, как я показывал на вебинаре, либо поиграться с ansible, если есть желание
