# Гайд по установке Node.js, настройке VS Code с Prettier и Git

## 1️⃣ Установка Node.js и npm

1. Перейдите на [официальный сайт Node.js](https://nodejs.org/).
2. Скачайте **LTS-версию** (рекомендуется для большинства пользователей).
3. Запустите установщик и следуйте инструкциям.
4. Проверьте установку в терминале:

   ```bash
   node -v    # версия Node.js
   npm -v     # версия npm (менеджер пакетов)
   ```

> 💡 Если используете macOS/Linux — можно установить через [nvm](https://github.com/nvm-sh/nvm), чтобы легко управлять версиями Node.js.

---

## 2️⃣ Настройка VS Code и Prettier

1. Скачайте и установите [Visual Studio Code](https://code.visualstudio.com/).
2. Запустите VS Code → откройте панель **Extensions** (Ctrl+Shift+X / Cmd+Shift+X).
3. Найдите и установите расширение **Prettier – Code formatter**.
4. В настройках VS Code:
   - Откройте `File → Preferences → Settings` (или `Cmd+,` на macOS).
   - Найдите «Format On Save» и активируйте ✅.
   - Введите «Default Formatter» и выберите `esbenp.prettier-vscode`.
5. Создайте в корне проекта файл `.prettierrc` для кастомных правил:

   ```json
   {
     "semi": true,
     "singleQuote": true,
     "tabWidth": 2,
     "trailingComma": "es5"
   }
   ```

6. Проверьте работу:
   - Создайте JS-файл с кодом без форматирования.
   - Сохраните — код автоматически отформатируется.

---

## 3️⃣ Настройка Git

1. Установите [Git](https://git-scm.com/downloads).
2. Проверьте версию:

   ```bash
   git --version
   ```

3. Настройте имя и email (используются для коммитов):

   ```bash
   git config --global user.name "Ваше имя"
   git config --global user.email "you@example.com"
   ```

4. Рекомендуется активировать цветной вывод:

   ```bash
   git config --global color.ui auto
   ```

5. Создайте SSH-ключ (для работы с GitHub/GitLab):

   ```bash
   ssh-keygen -t ed25519 -C "you@example.com"
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519
   ```

6. Скопируйте ключ:

   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

   → Добавьте его в настройках своего аккаунта на GitHub/GitLab.

7. Инициализация репозитория в проекте:

   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin git@github.com:USERNAME/REPO.git
   git push -u origin main
   ```

---

## ✅ Результат

- Node.js и npm установлены.
- VS Code автоматически форматирует код с помощью Prettier.
- Git готов для работы с вашими проектами.

> Теперь можно начинать писать код и вести его в системе контроля версий!
