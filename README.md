# Выполнить для запуска проекта:

## 1. Клонируем репозиторий:
git clone https://gitlab.ru/alexandr_gogolev/ansiblehw.git

## 2. Установка дополнительных ролей ansible:
ansible-galaxy install -r requirements.yml --roles-path ./roles

## 3. Дешифруем файл с переменными:
ansible-vault decrypt ./roles/deploy-app/vars/main.yml

## 4. Запуск: 
vagrant up

### Дополнительные команды:
Удаление окружения: vagrant getroy -f