# Практическое задание №8: MongoDB и CRUD-операции в Go
## Группа: ЭФМО-02-25
## ФИО: Евдоков Богдан Вадимович

## 🎯 Цель работы
Освоить работу с документной базой данных MongoDB из Go-приложения, реализовать CRUD-операции для сущности "заметки".

## 📋 Предварительные требования
1. **Go** (версия 1.20 или выше) - [скачать](https://go.dev/dl/)
2. **Git for Windows** - [скачать](https://git-scm.com/download/win)
3. **Docker Desktop for Windows** - [скачать](https://www.docker.com/products/docker-desktop/)

## 🚀 Инструкция по запуску на Windows

### 1. Клонирование репозитория
```powershell
git clone https://github.com/jervissss/pz8-mongo.git
cd pz8-mongo
```
### 2. Запуск MongoDB через Docker Compose
```powershell
docker compose up -d
```
### 3. Запуск Go-сервера
```powershell
go run .\cmd\api\main.go
```
### 4. Проверка работы API
**Создание заметки**
```powershell
$body = @{
    title = "Первая заметка"
    content = "Привет, MongoDB!"
} | ConvertTo-Json

Invoke-RestMethod -Uri "http://localhost:8080/api/v1/notes" `
    -Method Post `
    -ContentType "application/json" `
    -Body $body
```
**Получение списка заметок**
```powershell
Invoke-RestMethod -Uri "http://localhost:8080/api/v1/notes"
```
**Получение заметки по ID**
```powershell
Invoke-RestMethod -Uri "http://localhost:8080/api/v1/notes/<id>"
```
**Обновление заметки**
```powershell
$body = @{
    content = "Обновленный текст"
} | ConvertTo-Json

Invoke-RestMethod -Uri "http://localhost:8080/api/v1/notes/<id>" `
    -Method Patch `
    -ContentType "application/json" `
    -Body $body
```
**Удаление заметки**
```powershell
Invoke-RestMethod -Uri "http://localhost:8080/api/v1/notes/<id>" `
    -Method Delete
```
## 📁 Структура проекта
<img width="329" height="431" alt="image" src="https://github.com/user-attachments/assets/cca50b1d-eaec-4793-b866-33a1ada38a60" />

## 📸 Скриншоты работы
1. Запуск MongoDB в Docker
<img width="1919" height="1079" alt="Снимок экрана 2025-12-05 132335" src="https://github.com/user-attachments/assets/25edd4a7-fb7a-486b-b872-913b9e481e21" />

2. Запуск Go-сервера
<img width="1919" height="1079" alt="Снимок экрана 2025-12-05 132609" src="https://github.com/user-attachments/assets/83597db1-52c0-41b4-91bb-823721486630" />

3. Тестирование CRUD операций
<img width="1914" height="1079" alt="Снимок экрана 2025-12-05 132654" src="https://github.com/user-attachments/assets/09db66d9-5bfc-4fb1-ab46-34cf463b4028" />

<img width="1919" height="1079" alt="Снимок экрана 2025-12-05 132814" src="https://github.com/user-attachments/assets/35a13ece-bd3d-4dfc-93de-e0fbf4f6ae39" />

<img width="1919" height="1079" alt="Снимок экрана 2025-12-05 133108" src="https://github.com/user-attachments/assets/f2b2473c-9fb5-48da-9bd4-284bbbb945b4" />
