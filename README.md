# AURA Pet Salon — лендинг «Код доверия. Анатомия груминга»

Одностраничный лендинг студии бережного груминга (собаки и кошки).
Single-file build: весь CSS/JS инлайном в `index.html`. Ноль сборщиков, ноль зависимостей.

## 🚀 Публикация на GitHub Pages (3 шага)
1. Создайте репозиторий `grooming-landing`, загрузите `index.html` в корень.
2. Создайте папку `images/` и добавьте визуалы (таблица ниже).
3. Settings → Pages → Branch: `main` / root → Save. Через 1–2 мин сайт живёт на
   `https://<ваш-ник>.github.io/grooming-landing/`

## 🖼️ Манифест визуала
| Файл | Пропорции | Блок лендинга | Источник |
|---|---|---|---|
| `images/01-hero.jpg` | 16:9 | Hero-фон (fullscreen) | Визуал №1 из чата |
| `images/02-fur-macro.jpg` | 1:1 | Цитата-полоса (фон под оверлеем 78%) | Визуал №2 из чата |
| `images/03-interior.jpg` | 16:9 | Секция «Формат» (фон + параллакс) | Визуал №3 из чата |
| `images/04-cat.jpg` | 4:5 (кроп) | «Философия», правая колонка | Визуал №4 из чата |
| `images/05-expert.jpg` | 4:5 | Секция «Мастер», портрет | Промпт P1 |
| `images/06-spa.jpg` | 16:9 | Лид-магнит полоса (фон) | Промпт P2 |
| `images/07-tools.jpg` | 1:1 | «Процесс», sticky-медиа | Промпт P3 |

> Пока файла нет — автоматически подставляется тематический фото-фолбэк,
> затем брендовый SVG-градиент. Сайт не выглядит сломанным ни при каком сценарии.

## 🎨 Промпты для Nano Banana Pro (формула из инструкции)

**P1 — портрет эксперта (`05-expert.jpg`, 4:5)**
Cinematic photography, medium shot of a confident female groomer in her late 30s
with warm brown hair in a low bun, wearing a minimalist sage-green linen apron over
a cream sweater, holding professional grooming scissors at chest level, serene
thoughtful expression, subtle smile, modern minimalist pet salon with wooden shelves
blurred behind, Rembrandt lighting, earth tones, shot on Canon EOS R5 with 85mm f/1.4
lens, Kodak Portra 400 style, hyperrealistic, 8k resolution --ar 4:5

**P2 — SPA-процедура (`06-spa.jpg`, 16:9)**
Cinematic photography, medium shot of a calm golden retriever being gently washed in
a premium black stainless steel grooming tub, soft white foam on fur, groomer's hands
massaging the chest, warm golden hour volumetric light through a frosted window,
spa atmosphere, shallow depth of field, bokeh, Kodak Portra 400 style, 8k --ar 16:9

**P3 — макро-инструмент (`07-tools.jpg`, 1:1)**
Extreme close-up macro photography of professional grooming scissors cutting through
thick fluffy golden dog fur, polished steel metallic texture, single hair strands in
sharp focus, soft volumetric studio lighting, clean neutral beige background,
photorealistic, highly detailed, 8k resolution --ar 1:1

**Негативный промпт (ко всем трём):**
(deformed, distorted, disfigured:1.3), poorly drawn, bad anatomy, wrong anatomy,
extra limb, missing limb, floating limbs, (mutated hands and fingers:1.4),
disconnected limbs, mutation, ugly, blurry, grainy, watermark, text, extra objects, messy

## 🔌 Боевой запуск формы
В `index.html`, блок `8. FORM SUBMIT`, замените `console.log` на:
fetch('https://api.telegram.org/bot<TOKEN>/sendMessage', {method:'POST',
 headers:{'Content-Type':'application/json'},
 body: JSON.stringify({chat_id:<CHAT_ID>, text: JSON.stringify(payload))})});