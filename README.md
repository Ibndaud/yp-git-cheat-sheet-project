# 🧠 Шпаргалка по **Git** и **GitHub**

## 📁 Инициализация и базовые команды

- **Инициализация репозитория:**
  ```bash
  git init
  ```

- **Проверка статуса изменений:**
  ```bash
  git status
  ```

- **Удаление репозитория (если инициализация была в неверной папке):**
  ```bash
  rm -rf .git
  ```
  ⚠️ Удаление `.git` удаляет всю историю проекта.

---

## 🔄 Добавление файлов

- **Добавить конкретный файл:**
  ```bash
  git add <имя_файла>
  ```

- **Добавить все изменённые файлы:**
  ```bash
  git add --all
  ```

- **Добавить все файлы в текущей директории:**
  ```bash
  git add .
  ```

📌 `git add` подготавливает файлы к коммиту, но *не сохраняет* их в репозитории.

---

## 💾 Создание коммитов

- **Базовая команда коммита:**
  ```bash
  git commit -m "Информативное сообщение"
  ```

- **Коммит сохраняет текущее состояние файлов.**

- **В коммит попадают только файлы, добавленные через `git add`.**

- **Коммит = сохранение состояния + возможность отката.**

- **Вывод информации об истории коммитов:**
  ```bash
  git log
  ```
  Показывает список коммитов в обратном хронологическом порядке.

🧠 **Разница между `git add` и `git commit`:**
- `git add` — подготовка файлов к коммиту.
- `git commit` — сохранение изменений и добавление их в историю.

---

## 🌱 Ветки и история

- **Основная ветка:** `main` или `master` (создаётся при инициализации).
- **Коммиты хранятся в ветках.**
- Историю можно изучать через `git log`.

---

## 🧭 Работа с GitHub и удалёнными репозиториями

### 🌍 Git и GitHub - в чём разница?

| Git                     | GitHub                          |
|-------------------------|----------------------------------|
| Консольный инструмент   | Платформа для командной работы  |
| Работает локально/удалённо | Хостинг репозиториев         |
| Развивается независимо  | Принадлежит Microsoft           |
| Открытый исходный код   | Веб-интерфейс, сервис           |

Также существуют альтернативы GitHub: **GitLab**, **Bitbucket** и др.

---

## 🧑‍💻 Регистрация на GitHub

1. Перейдите на [GitHub](https://github.com)
2. Нажмите **Sign up**
3. Введите:
   - Email
   - Пароль
   - Имя пользователя
4. Выберите рассылку, пройдите капчу
5. Нажмите **Create account**
6. Введите код из email
7. ✔️ Готово — вы зарегистрированы!

---

## 🔐 SSH и безопасное соединение

### Что такое SSH и SSH-ключи:

- SSH — протокол безопасного обмена данными.
- SSH-ключ — виртуальный идентификатор (как "ключ от квартиры").

💡 Состоит из:
- **Публичного ключа** (шифрует данные)
- **Приватного ключа** (расшифровывает — **нельзя никому показывать!**)

### Генерация SSH-ключей

После генерации ключи сохраняются в `~/.ssh` как:

- `id_ed25519` (приватный)
- `id_ed25519.pub` (публичный)

#### Скопировать публичный ключ:
- **macOS:**
  ```
  pbcopy < ~/.ssh/id_ed25519.pub
  или
  cat ~/.ssh/id_ed25519.pub
  ```

- **Windows:**
  ```
  clip < ~/.ssh/id_ed25519.pub
  ```

### Добавление SSH-ключа в GitHub:

1. Перейдите в **Settings → SSH and GPG keys**
2. Нажмите **New SSH key**
3. Вставьте содержимое публичного ключа
4. Назовите ключ (например, "My Laptop SSH")
5. Нажмите **Add SSH Key**

🔧 **Проверка подключения:**
```bash
ssh -T git@github.com
```

---

## 🔗 Связываем локальный и удалённый репозиторий

1. На GitHub:
   - Откройте страницу репозитория
   - Выберите **SSH**
   - Скопируйте URL вида:
     ```
     git@github.com:ваш_логин/имя_репозитория.git
     ```

2. В терминале:
   ```bash
   git remote add origin <URL>
   ```

3. Проверка связи:
   ```bash
   git remote -v
   ```

---

## 🚀 Отправка изменений в удалённый репозиторий

```bash
git push origin main
```

📌 Отправка осуществляется на ветку `main` (`master`).

GitHub визуально показывает все коммиты и список изменений.

---

## 📄 README.md и Markdown

### Что такое README.md:

- Файл описания проекта
- Обычно включает:
  - название
  - описание
  - используемые технологии
  - инструкции по запуску
  - контакты и планы развития

### Как создать:
```bash
touch README.md
```

### Что такое Markdown:

- Язык разметки для форматирования текста
- Примеры:
  - **Курсив**: `*текст*` → *текст*
  - **Жирный шрифт**: `**текст**` → **текст**
  - ~~Зачёркнутый~~: `~~текст~~`
  - `Код`: оборачивается в обратные кавычки (`)

- Блок кода:
  ````markdown
  ```python
  print("Hello, world!")
  ```
  ````

---

## ✅ Полезные команды Git (итог)

| Команда                         | Назначение                                           |
|---------------------------------|-------------------------------------------------------|
| `git init`                      | Инициализация репозитория                            |
| `git status`                    | Проверка текущего состояния репозитория              |
| `git add .`                     | Добавить все изменения в текущей папке               |
| `git add --all`                | Добавить все изменения в проекте                     |
| `git commit -m "message"`       | Сохраняет изменения с сообщением                    |
| `git log`                       | Показывает историю коммитов                         |
| `git remote add origin <URL>`   | Связать с удаленным репозиторием                    |
| `git push origin main`          | Отправить изменения на GitHub                       |
| `git remote -v`                 | Проверить связанные удалённые репозитории           |

---
