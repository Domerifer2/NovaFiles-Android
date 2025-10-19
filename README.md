# NovaFiles-Android
A secure file explorer with its own tools for working with files.


# 🌌 NovaFiles Android  
**A secure cross-platform file explorer with its own tools, plugins, and root system.**  
Developed as part of the *Nova System Tools* project.  

---

## 🚀 Overview

NovaFiles is an advanced file manager designed for Android (and later cross-platform targets).  
It combines the simplicity of traditional explorers with modular tools, themes, and deep system integration.  
Supports sandboxed and certified root operations via **RSO** and **Dev Mode**.

---

## ⚙️ Core Features

- 📂 File operations: copy, move, delete, rename, multi-select  
- 🧩 Plugin system: modular add-ons (viewers, tools, analyzers)  
- 🧱 Local storage, SD, USB, LAN (SMB/SFTP/WebDAV planned)  
- 🧮 Archive tools (ZIP, 7z, TAR, RAR extract, AES-256 encryption)  
- 🌓 Theming: Light / Dark / AMOLED / Neon profiles  
- 💾 Internal analytics: disk usage, duplicates, permissions  
- 🛡️ RSO (Root Safety Override) certification system  
- 💻 Developer Mode for creating plugins and custom interfaces  
- 🔐 Root access with Magisk / KernelSU support  

---

## 🧭 Modes and Permissions

| Capability | Normal | Dev | Root | RSO |
|-------------|:------:|:---:|:----:|:---:|
| View system files | ❌ | ⚠️ | ✅ | ✅ |
| Modify system data | ❌ | ❌ | ⚠️ | ✅ |
| Access core (.so) | ✅ | ✅ | ✅ | ✅ |
| Load plugins | ✅ | ✅ | ✅ | ✅ |
| Remove Root limits | ❌ | ❌ | ❌ | ✅ |
| Modify certifications | ❌ | ❌ | ❌ | ❌ |

🟢 **Legend:**  
✅ — Allowed ⚠️ — Restricted / Confirmed ❌ — Not allowed  

---

## 🔧 Architecture Overview

**Frontend:** Flutter  
**Core Engine:** Rust (via FFI)  
**Security Modules:** RSO, DevCert, AdminCert  
**Cross-layer Communication:** FFI + IPC

```Structure
Flutter UI (Android)
     │
     ▼
  FFI bridge
     │
     ▼
  novafiles_core (.so)
     │
     ├─ File operations 
     ├─ Archive services
     ├─ Root interface
     └─ Certification layer (RSO / Dev / Admin)
```

---

## 🧠 Developer Mode (Dev)

Dev Mode allows advanced users and developers to:
- Customize UI components and file views  
- Write NovaScripts (NS) for automation  
- Edit local configuration overlays  
- Enable unsafe plugin execution (with warnings)  

> ⚠️ **Important:** Dev Mode cannot alter certification or RSO internals.  
> Any attempt to modify secure sections triggers local protection and log alerts.

---

## 🔒 Root & RSO Certification

**RSO** — Root Safety Override is a secure certification mechanism that:  
- Ensures only verified devices can disable root limitations  
- Uses encrypted certificates bound to Device ID  
- Prevents manual tampering or relocation  
- Allows admins and owners to manage trust lists and revocations  

---

## 🎨 Theme Profiles

| Theme | Accent | Surface | Variant |
|--------|:-------:|:--------:|:--------:|
| Light | #4F46E5 | #FFFFFF | Material 3 |
| Dark | #60A5FA | #0F172A | Material 3 |
| AMOLED | #22D3EE | #000000 | Pure black |
| Neon | #7C3AED | #0A0A0A | High contrast |

Custom `.nvt` (Nova Theme) packages can be imported/exported from Settings.

---

## 🧩 Plugins

- `viewer_pdf` — embedded PDF viewer  
- `tool_batch_rename` — mass rename tool  
- `archiver_7z` — 7-Zip compression  
- `source_smb` — SMB network access  
- `analyzer_space` — disk usage analyzer  

Plugins follow the schema:

```json
{
  "name": "tool_batch_rename",
  "version": "1.0.0",
  "api": 1,
  "entry": "libtool_batch_rename.so",
  "permissions": ["filesystem"]
}
```

---

⚠️ Root Warning

> ⚠️ Using root features may damage your system or delete critical files.
Proceed only if you understand the risks. NovaFiles developers are not responsible for any data loss.




---

🧾 License

© 2025 Nova Studios / Boreal Builder
Distributed for testing under internal RSO Dev Certification.


---


---

🇷🇺 NovaFiles Android

Безопасный кроссплатформенный файловый менеджер со своими инструментами, плагинами и системой Root.
Разработан в рамках проекта Nova System Tools.


---

🚀 Обзор

NovaFiles — продвинутый файловый менеджер для Android и других платформ.
Объединяет простоту классических проводников с модульной системой, темами и интеграцией с ядром.
Поддерживает безопасные операции Root и сертификацию RSO с режимом Dev.


---

⚙️ Основные возможности

📂 Работа с файлами: копирование, перемещение, удаление, переименование

🧩 Модули и плагины: просмотрщики, инструменты, анализаторы

🧱 Поддержка SD, USB, LAN (SMB/SFTP/WebDAV)

🧮 Архивы: ZIP, 7z, TAR, RAR (распаковка), AES-256 шифрование

🌓 Темы: Светлая / Тёмная / AMOLED / Неон

💾 Аналитика: крупные файлы, дубликаты, использование хранилища

🛡️ Сертификация RSO (Root Safety Override)

💻 Режим разработчика (Dev Mode)

🔐 Работа с Root через Magisk / KernelSU



---

🧭 Режимы и права

### 🧱 Сравнение режимов работы NovaFiles

| 🧩 Возможность               | 🟩 Normal | 🟦 Dev | 🟥 Root | 🟨 RSO |
|------------------------------|:---------:|:------:|:-------:|:------:|
| Просмотр системных файлов     | ❌ | ⚠️ | ✅ | ✅ |
| Изменение системных данных    | ❌ | ❌ | ⚠️ | ✅ |
| Доступ к ядру (.so)           | ✅ | ✅ | ✅ | ✅ |
| Загрузка плагинов             | ✅ | ✅ | ✅ | ✅ |
| Снятие ограничений Root       | ❌ | ❌ | ❌ | ✅ |
| Изменение сертификаций        | ❌ | ❌ | ❌ | ❌ |

🟢 Легенда:
✅ — Разрешено ⚠️ — Ограничено / Подтверждается ❌ — Запрещено


---

🔧 Архитектура

Интерфейс: Flutter
Ядро: Rust (через FFI)
Сертификаты: RSO, DevCert, AdminCert
Связь слоёв: FFI + IPC
```Структура
Flutter UI (Android)
     │
     ▼
  FFI мост
     │
     ▼
  novafiles_core (.so)
     │
     ├─ Операции с файлами
     ├─ Работа с архивами
     ├─ Root-интерфейс
     └─ Сертификационный слой (RSO / Dev / Admin)
```

---

🧠 Режим разработчика (Dev Mode)

Режим разработчика позволяет:

Изменять интерфейс и функции проводника

Писать NovaScripts (NS) для автоматизации

Редактировать локальные оверлеи

Включать запуск несертифицированных плагинов


> ⚠️ Важно: Режим разработчика не может изменять RSO и систему сертификаций.
Любые попытки редактировать защищённые секции блокируются и фиксируются в журнале.




---

🔒 Root и RSO

RSO (Root Safety Override) — система сертификации, гарантирующая:

Безопасное снятие ограничений root только на доверенных устройствах

Привязку сертификата к ID устройства

Проверку подписи и целостности

Управление списком доверия и отзывов



---

🎨 Темы

| Тема | Акцент	| Поверхность	| Вариант |
|--------|:-------:|:--------:|:--------:|
Светлая	| #4F46E5	| #FFFFFF	| Material 3 |
| Тёмная | #60A5FA | #0F172A | Material 3 |
| AMOLED | #22D3EE | #000000 | Полный чёрный |
| Неон | #7C3AED | #0A0A0A | Высокий контраст |


Пользовательские темы (.nvt) можно импортировать и экспортировать из настроек.


---

🧩 Плагины

viewer_pdf — просмотр PDF

tool_batch_rename — массовое переименование

archiver_7z — архиватор 7-Zip

source_smb — доступ по SMB

analyzer_space — анализ пространства


Формат манифеста плагина:

```json
{
  "name": "tool_batch_rename",
  "version": "1.0.0",
  "api": 1,
  "entry": "libtool_batch_rename.so",
  "permissions": ["filesystem"]
}
```


---

⚠️ Root-предупреждение

> ⚠️ Использование Root может повредить систему или удалить критические данные.
Используйте только на свой страх и риск. Разработчики NovaFiles не несут ответственности за последствия.




---

🧾 Лицензия

© 2025 Nova Studios / Boreal Builder
Тестовая сборка в рамках внутренней сертификации RSO Dev.
