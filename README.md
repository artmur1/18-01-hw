# Домашнее задание к занятию 1 «Введение в Ansible» - `Мурчин Артем`

## Подготовка к выполнению

1. Установите Ansible версии 2.10 или выше.
2. Создайте свой публичный репозиторий на GitHub с произвольным именем.
3. Скачайте [Playbook](./playbook/) из репозитория с домашним заданием и перенесите его в свой репозиторий.

## Основная часть

1. Попробуйте запустить playbook на окружении из `test.yml`, зафиксируйте значение, которое имеет факт `some_fact` для указанного хоста при выполнении playbook.

![alt text](https://github.com/artmur1/18-01-hw/blob/main/img/18-01-1.png)

2. Найдите файл с переменными (group_vars), в котором задаётся найденное в первом пункте значение, и поменяйте его на `all default fact`.

![alt text](https://github.com/artmur1/18-01-hw/blob/main/img/18-01-2.png)

3. Воспользуйтесь подготовленным (используется `docker`) или создайте собственное окружение для проведения дальнейших испытаний.

![alt text](https://github.com/artmur1/18-01-hw/blob/main/img/18-03-1.png)

4. Проведите запуск playbook на окружении из `prod.yml`. Зафиксируйте полученные значения `some_fact` для каждого из `managed host`.

![alt text](https://github.com/artmur1/18-01-hw/blob/main/img/18-04-1.png)

5. Добавьте факты в `group_vars` каждой из групп хостов так, чтобы для `some_fact` получились значения: для `deb` — `deb default fact`, для `el` — `el default fact`.

![alt text](https://github.com/artmur1/18-01-hw/blob/main/img/18-05-1.png)

6.  Повторите запуск playbook на окружении `prod.yml`. Убедитесь, что выдаются корректные значения для всех хостов.

![alt text](https://github.com/artmur1/18-01-hw/blob/main/img/18-06-1.png)

7. При помощи `ansible-vault` зашифруйте факты в `group_vars/deb` и `group_vars/el` с паролем `netology`.

![alt text](https://github.com/artmur1/18-01-hw/blob/main/img/18-07-1.png)

8. Запустите playbook на окружении `prod.yml`. При запуске `ansible` должен запросить у вас пароль. Убедитесь в работоспособности.

![alt text](https://github.com/artmur1/18-01-hw/blob/main/img/18-08-1.png)

9. Посмотрите при помощи `ansible-doc` список плагинов для подключения. Выберите подходящий для работы на `control node`.

![alt text](https://github.com/artmur1/18-01-hw/blob/main/img/18-09-1.png)

Прочитал описания плагинов, но какой подходит для работы на `control node` затрудняюсь ответить.

10. В `prod.yml` добавьте новую группу хостов с именем  `local`, в ней разместите localhost с необходимым типом подключения.

![alt text](https://github.com/artmur1/18-01-hw/blob/main/img/18-10-1.png)

11. Запустите playbook на окружении `prod.yml`. При запуске `ansible` должен запросить у вас пароль. Убедитесь, что факты `some_fact` для каждого из хостов определены из верных `group_vars`.

![alt text](https://github.com/artmur1/18-01-hw/blob/main/img/18-11-1.png)

12. Заполните `README.md` ответами на вопросы. Сделайте `git push` в ветку `master`. В ответе отправьте ссылку на ваш открытый репозиторий с изменённым `playbook` и заполненным `README.md`.

![alt text](https://github.com/artmur1/18-01-hw/blob/main/img/18-12-1.png)

13. Предоставьте скриншоты результатов запуска команд.

## Необязательная часть

1. При помощи `ansible-vault` расшифруйте все зашифрованные файлы с переменными.
2. Зашифруйте отдельное значение `PaSSw0rd` для переменной `some_fact` паролем `netology`. Добавьте полученное значение в `group_vars/all/exmp.yml`.
3. Запустите `playbook`, убедитесь, что для нужных хостов применился новый `fact`.
4. Добавьте новую группу хостов `fedora`, самостоятельно придумайте для неё переменную. В качестве образа можно использовать [этот вариант](https://hub.docker.com/r/pycontribs/fedora).
5. Напишите скрипт на bash: автоматизируйте поднятие необходимых контейнеров, запуск ansible-playbook и остановку контейнеров.
6. Все изменения должны быть зафиксированы и отправлены в ваш личный репозиторий.

---

### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.

---
