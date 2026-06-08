# elit-web · Маркетинг-хаб

Інтерактивний маркетинговий дешборд для elit-web.ua з усіма тижневими та помісячними звітами за травень-червень 2026.

## Дані з джерел

HubSpot CRM (ліди, MQL, SQL, угоди) · Meta Ads (Facebook + Instagram) · Google Ads · GA4 · Google Search Console · Windsor.ai

## Що всередині

`index.html` — головна сторінка-хаб: пікер періодів, порівняння двох тижнів/місяців, швидкі лінки на тижневі звіти, підсумкова таблиця.

### Помісячні звіти

- `dashboard_may_apr.html` — квітень + травень: ліди, MQL, SQL, витрати, плани, метрики по кампаніям

### Тижневі звіти

- `dashboard_1_4may.html` — 1-4 травня
- `dashboard_5_11may.html` — 5-11 травня
- `dashboard_12_18may.html` — 12-18 травня
- `dashboard_19_25may.html` — 19-25 травня
- `dashboard_26may_1jun.html` — 26 травня - 1 червня
- `dashboard_2_8jun.html` — 2-8 червня (включає вкладки по каналах: SEO, Target, Контекст, DRP)

Усі тижневі звіти мають свою навігацію назад на хаб і між тижнями.

## Локальний запуск

```bash
npm install
npm start
```

Сторінка буде доступна на http://localhost:3000.

## Деплой на Railway

1. Запуш цей репозиторій на GitHub.
2. Зайди на [railway.com](https://railway.com), створи новий проект → **Deploy from GitHub repo** → обери цей репозиторій.
3. Railway автоматично визначить Node.js, виконає `npm install` і запустить `npm start`.
4. У налаштуваннях проекту → Settings → Networking → **Generate Domain** — отримаєш публічну URL.

### Захист від публічного індексування

В `index.html` додано `<meta name="robots" content="noindex,nofollow">`. Якщо хочеш ще додатково закрити від чужих очей — у Railway:
- **Settings → Environment → Add Variable**: можна додати простий Basic Auth через `serve` або налаштувати custom proxy.
- Або обмежити доступ через Railway's project access (приватний проект, тільки members твого workspace).

## Структура

- `index.html` — хаб (головна сторінка)
- `dashboard_*.html` — тижневі та помісячні звіти (8 файлів)
- `package.json` — мінімальний Node-сервер
- `railway.toml` — конфіг Railway
- `.gitignore` — виключає node_modules

## Технології

- HTML5 + CSS3 (Mulish font, Elit-web style)
- Chart.js 4.5.0 (через CDN)
- Vanilla JavaScript (без фреймворків)
- Node.js + serve (для прод-роздачі)
