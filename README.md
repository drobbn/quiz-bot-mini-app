# Telegram Mini App для авторизации через TON Connect

Этот Mini App позволяет пользователям авторизоваться через кошелек Tonkeeper прямо в Telegram боте.

## Установка и настройка

### 1. Разместите файлы на веб-сервере

Скопируйте все файлы из папки `mini_app/` на ваш веб-сервер (например, на GitHub Pages, Vercel, или любой другой хостинг).

### 2. Обновите манифест

Отредактируйте файл `tonconnect-manifest.json` и укажите правильные URL:

```json
{
  "url": "https://your-domain.com/mini_app/",
  "name": "Quiz Bot - Викторина с наградами",
  "iconUrl": "https://your-domain.com/mini_app/icon.png",
  "termsOfUseUrl": "https://your-domain.com/mini_app/terms.txt",
  "privacyPolicyUrl": "https://your-domain.com/mini_app/privacy.txt"
}
```

### 3. Настройте переменную окружения

В файле `.env` добавьте:

```
MINI_APP_URL=https://your-domain.com/mini_app/
```

### 4. Настройте бота

Используйте команду `/setmenubutton` в @BotFather для настройки кнопки меню (опционально).

## Как это работает

1. Пользователь нажимает кнопку "Авторизоваться через Tonkeeper" в боте
2. Открывается Mini App с интерфейсом TON Connect
3. Пользователь подключает кошелек через Tonkeeper
4. Mini App отправляет данные кошелька в бота через `tg.sendData()`
5. Бот получает данные и сохраняет адрес кошелька

## Структура файлов

- `index.html` - основной файл Mini App с интерфейсом авторизации
- `tonconnect-manifest.json` - манифест для TON Connect
- `README.md` - этот файл

## Дополнительные файлы (опционально)

Вы можете добавить:
- `icon.png` - иконка приложения (48x48 или больше)
- `terms.txt` - условия использования
- `privacy.txt` - политика конфиденциальности

