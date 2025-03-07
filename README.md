# victorialogs_ansible_playbook
Playbook для автоматической standalone-установки VictoriaLogs

# Перед запуском
Перед запуском данного playbook вам необходимо выполнить следующие шаги:
1. Скачать актуальную версию VictoriaLogs с официального репозитория [GitHub](https://github.com/VictoriaMetrics/VictoriaMetrics/releases). Данный playbook расчитан на версию VictoriaMetrics с суфиксом "-cluster";
2. После скачивания актуальной версии вам необходимо актуализировать переменную "victorialogs_version" указанную в файле **group_vars/all**;
3. Если ваше ssh подключение требует авторизации с использованием сертификата, добавьте сертификат в директорию **ssh_key/victoriametrics**;
4. Актуализировать инвентаризационный файл **hosts** указав в нём актуальные: 
    - Dns имена;
    - Ip адреса;
    - Пользователей;
    - Ssh ключи.

# Запуск playbook
После проведения шагов указанных выше, вы можете запустить playbook, находясь в корневой директории проекта, с использованием команды:

```
ansible-playbook -i hosts main.yml --tags "all"
```
