# Шпаргалка по работе с Git

Это шпаргалка по основным командам и понятиям системы контроля версий Git.

## Основные Команды

### Инициализация Репозитория

bash
git init               # Создание нового локального репозитория
git clone <url>        # Клонирование удалённого репозитория

### Настройка Пользователя

bash
git config --global user.name "Ваше Имя"
git config --global user.email "ваш.email@example.com"

### Основные Операции

bash
git status             # Проверка состояния репозитория
git add <файл>         # Добавление файлов в индекс (стадию)
git commit -m "Сообщение коммита"  # Создание нового коммита

### Работа с Ветками

bash
git branch             # Список веток
git branch <имя ветки> # Создание новой ветки
git checkout <имя ветки> # Переключение на другую ветку
git merge <имя ветки>  # Слияние указанной ветки с текущей

### Удалённые Репозитории

bash
git remote add origin <url> # Добавление удалённого репозитория
git push origin <ветка>     # Отправка изменений в удалённый репозиторий
git pull                    # Получение изменений из удалённого репозитория и слияние с локальными

## Основные Понятия

- **Репозиторий**: Место для хранения кода и истории его изменений.
- **Коммит**: Сохранённое состояние проекта.
- **Ветка**: Механизм для реализации параллельных разработок.

## Регистрация на GitHub

1. Перейдите на [GitHub](https://github.com/).
2. Нажмите на `Sign up` в верхнем правом углу.
3. Следуйте инструкциям для создания нового аккаунта.

## Инициализация Проекта

1. Создайте новую директорию для вашего проекта.
2. Внутри этой директории выполните:

bash
git init

3. Добавьте файлы в репозиторий:

bash
git add .

4. Создайте коммит:

bash
git commit -m "Первый коммит"

5. Настройте удалённый репозиторий и отправьте изменения:

bash
git remote add origin https://github.com/your-username/your-repo.git
git push -u origin master

## Хеши в Git

- Git использует SHA-1 хеши для идентификации объектов.
- Хеш – это уникальный идентификатор длиной 40 символов, например e9a1d7b9725b2ae30e7b7c4bcb487b166fdaff92.
- Хеши используются для отслеживания файлов, коммитов, деревьев и других объектов.

## git log

- git log – Показывает журнал коммитов.
- Полезные опции:
  - git log --oneline – отображает каждый коммит в одной строке.
  - git log --graph – визуализирует историю коммитов в виде графа.
  - git log --stat – показывает статистику изменений в файлах.

## HEAD в Git

- HEAD – это указатель на текущую ветку или коммит.
- git checkout <ветка> – чтобы переключиться на другую ветку.
- git checkout <хеш> – чтобы переключиться на конкретный коммит.

## Статусы файлов и жизненный цикл в Git

Файлы в Git могут находиться в одном из четырех состояний:
- Untracked (Неотслеживаемый) – файл не отслеживается Git.
- Modified (Измененный) – файл изменен, но еще не добавлен в индекс.
- Staged (Проиндексированный) – файл добавлен в индекс и готов к коммиту.
- Committed (Закоммиченный) – файл зафиксирован в репозитории.

### Схема изменения статусов файлов в формате Mermaid

```
graph TD;
    A[Неотслеживаемый] -->|git add| B[Проиндексированный]
    B -->|git commit| C[Закоммиченный]
    C -->|Изменение в рабочем каталоге| D[Измененный]
    D -->|git add| B
    D -->|git restore| C
```

## Полезные Ссылки

- [Официальная документация Git](https://git-scm.com/doc)
- [Руководство по Git на русском](https://githowto.com/ru)