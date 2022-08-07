# Домашнее задание к занятию "08.01 Введение в Ansible"

## Подготовка к выполнению
1. Установите ansible версии 2.10 или выше.
2. Создайте свой собственный публичный репозиторий на github с произвольным именем.
3. Скачайте [playbook](./playbook/) из репозитория с домашним заданием и перенесите его в свой репозиторий.

## Основная часть
1. Попробуйте запустить playbook на окружении из `test.yml`, зафиксируйте какое значение имеет факт `some_fact` для указанного хоста при выполнении playbook'a.

Ответ: `some fact` = 12

![Снимок экрана от 2022-08-07 11-38-06](https://user-images.githubusercontent.com/93032289/183288431-ec9e4017-ac31-4f2f-a8ba-5704bda2705e.png)

2. Найдите файл с переменными (group_vars) в котором задаётся найденное в первом пункте значение и поменяйте его на 'all default fact'.

![Снимок экрана от 2022-08-07 14-32-26](https://user-images.githubusercontent.com/93032289/183288520-9a54525d-ac05-4113-8f1a-a84971688828.png)

3. Воспользуйтесь подготовленным (используется `docker`) или создайте собственное окружение для проведения дальнейших испытаний.

![Снимок экрана от 2022-08-07 14-44-49](https://user-images.githubusercontent.com/93032289/183288970-ded992b3-09af-4c31-96c7-25d769ebef79.png)

4. Проведите запуск playbook на окружении из `prod.yml`. Зафиксируйте полученные значения `some_fact` для каждого из `managed host`.

![Снимок экрана от 2022-08-07 16-28-07](https://user-images.githubusercontent.com/93032289/183293115-154cccd1-9652-4e4f-8606-566faf58d933.png)

5. Добавьте факты в `group_vars` каждой из групп хостов так, чтобы для `some_fact` получились следующие значения: для `deb` - 'deb default fact', для `el` - 'el default fact'.

Изменил значения в файлах examp.yml директориях /group_vars/deb и /group_vars/el на `deb default fact` и 'el default fact' соответственно.

6.  Повторите запуск playbook на окружении `prod.yml`. Убедитесь, что выдаются корректные значения для всех хостов.

![Снимок экрана от 2022-08-07 16-33-00](https://user-images.githubusercontent.com/93032289/183293327-af0c3792-fc7a-4e5e-b3da-caa287eb4343.png)

7. При помощи `ansible-vault` зашифруйте факты в `group_vars/deb` и `group_vars/el` с паролем `netology`.

![Снимок экрана от 2022-08-07 16-35-36](https://user-images.githubusercontent.com/93032289/183293447-d0a6e018-9109-474c-adec-700ee8e074a1.png)

8. Запустите playbook на окружении `prod.yml`. При запуске `ansible` должен запросить у вас пароль. Убедитесь в работоспособности.

![Снимок экрана от 2022-08-07 16-37-56](https://user-images.githubusercontent.com/93032289/183293544-7089080a-49de-412c-b8a8-02cfcc4df1f8.png)

9. Посмотрите при помощи `ansible-doc` список плагинов для подключения. Выберите подходящий для работы на `control node`.

![Снимок экрана от 2022-08-07 16-42-09](https://user-images.githubusercontent.com/93032289/183293697-e91f18bc-a0df-40bb-b1bb-4fdd7b8dc086.png)

10. В `prod.yml` добавьте новую группу хостов с именем  `local`, в ней разместите localhost с необходимым типом подключения.

![Снимок экрана от 2022-08-07 16-51-06](https://user-images.githubusercontent.com/93032289/183294112-7d2d6995-b8c8-40b3-a658-c22f4f75401f.png)

11. Запустите playbook на окружении `prod.yml`. При запуске `ansible` должен запросить у вас пароль. Убедитесь что факты `some_fact` для каждого из хостов определены из верных `group_vars`.

![Снимок экрана от 2022-08-07 16-52-47](https://user-images.githubusercontent.com/93032289/183294157-8ce1c143-c3ab-4e5d-aca3-32e7e4f31b39.png)

12. Заполните `README.md` ответами на вопросы. Сделайте `git push` в ветку `master`. В ответе отправьте ссылку на ваш открытый репозиторий с изменённым `playbook` и заполненным `README.md`.
