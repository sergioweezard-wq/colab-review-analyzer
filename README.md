# Аналізатор відгуків (Google Colab + Hugging Face)

Вебзастосунок для визначення тональності відгуків (позитивна / нейтральна / негативна).
Модель `cardiffnlp/twitter-xlm-roberta-base-sentiment` (Hugging Face) запускається прямо в Google Colab, інтерфейс — Gradio.
Результати: таблиця, діаграма (matplotlib) і текстовий звіт.

## Запуск

1. Відкрийте `review_analyzer.ipynb` у Google Colab (кнопка нижче або через сторінку GitHub Pages).
2. *Runtime → Run all*.
3. В останній комірці з'явиться публічне посилання `https://....gradio.live` — це і є вебзастосунок (діє, поки працює сесія Colab).

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USER/YOUR_REPO/blob/main/review_analyzer.ipynb)

> Замініть `YOUR_USER/YOUR_REPO` на свої дані.

## Командна робота

- `main` — стабільна гілка.
- `feature/<назва>` — гілки для нових змін; у `main` потрапляють лише через Pull Request з рев'ю.
- Повідомлення комітів: короткий опис змін у наказовій формі.

## CI/CD

Workflow `.github/workflows/deploy.yml`:
- на кожен push і Pull Request у `main` перевіряє коректність ноутбука (`nbformat`);
- на push у `main` публікує сторінку з кнопкою «Відкрити в Colab» на GitHub Pages
  (Settings → Pages → Source: GitHub Actions).

## Структура

```
review_analyzer.ipynb          – ноутбук: модель, аналіз, візуалізація, Gradio-застосунок
.github/workflows/deploy.yml   – CI/CD
README.md                      – документація
```
