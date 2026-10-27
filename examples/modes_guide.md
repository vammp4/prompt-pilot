# Приклади роботи Prompt-Pilot

Нижче наведено, як Prompt-Pilot адаптується під різні типи запитів, уникаючи бюрократії, де вона не потрібна.

---

## Приклад 1: Режим ⚡ Quick Spark (Швидкий буст)

### Вхід від користувача:
> "напиши скрипт на пайтоні який парсить курс долара з сайту нбу і шле мені в телеграм якщо він піднявся більше ніж на 50 копійок"

### Результат Prompt-Pilot (Лаконічно, без зайвих XML-простирадл):
```markdown
# ЗАДАЧА: Моніторинг курсу USD (НБУ) з алертом у Telegram

<SPECS>
- Джерело даних: Офіційний API НБУ (JSON endpoint: https://bank.gov.ua/NBUStatService/v1/statdirectory/exchange?valcode=USD&json)
- Збереження стану: локальний файл `last_rate.json` (попередній зафіксований курс)
- Умова тригера: `current_rate - previous_rate >= 0.50` UAH
- Канал сповіщення: Telegram Bot API (`requests.post` на `sendMessage`)
</SPECS>

<REQUIREMENTS>
1. Чистий Python 3.10+ без важких залежностей (`requests` достатньо).
2. Обробка помилок мережі та таймаутів (try/except з виводом у консоль).
3. Токени та Chat ID передаються через змінні оточення `os.getenv` (`TG_BOT_TOKEN`, `TG_CHAT_ID`).
4. Надай готову команду для запуску та тестовий запуск із моковими даними.
</REQUIREMENTS>
```

---

## Приклад 2: Режим 🧭 Strategic Roadmap (Фіча / Архітектура)

### Вхід від користувача:
> "хочу додати темну тему на мій Next.js сайт щоб зберігалась в куках і не мигала білим при завантаженні"

### Результат Prompt-Pilot:
```markdown
# РОЛЬ: Senior Frontend Engineer (Next.js / Tailwind CSS)

<OBJECTIVE>
Реалізувати повноцінну підтримку Dark/Light/System теми в Next.js (App Router) без ефекту FOUC (Flash of Unstyled Content) із збереженням стану в cookie/localStorage.
</OBJECTIVE>

<MILESTONES>
1. **Інфраструктура теми:** Інтеграція `next-themes` або легкої inline-ініціалізації теми в `<head>`.
2. **Tailwind конфігурація:** Налаштування селекторного режиму `darkMode: 'class'`.
3. **Компонент ThemeToggle:** Адаптивний перемикач із плавним UI та підтримкою іконок Sun/Moon.
4. **Валідація відсутності FOUC:** Перевірка поведінки при hard-refresh (Ctrl+Shift+R) та повільному 3G.
</MILESTONES>

<ACCEPTANCE_CRITERIA>
- Жодного білого мерехтіння при переході між сторінками.
- Робота як на клієнті, так і під час SSR.
- Покриття edge cases: користувач вперше зайшов (дефолт із системи `prefers-color-scheme`).
</ACCEPTANCE_CRITERIA>
```

---

## Приклад 3: Режим 🔄 Autonomous Loop Engine (Автономний агент / Loop-coding)

### Вхід від користувача:
> "зроби мені повний рефакторинг моєї бази даних в проекті, переведи з sqlite на postgres, онови всі моделі prisma і міграції, і прожени тести"

### Результат Prompt-Pilot:
```markdown
# ROLE: Lead Database & Backend Engineer (Antigravity Autonomous Loop)

<CONTEXT>
Поточний стек: Node.js, Prisma ORM, SQLite
Цільовий стек: PostgreSQL 16+
Локальні файли: prisma/schema.prisma, tests/*, .env
</CONTEXT>

<MASTER_GOAL>
Безшовний перехід з SQLite на PostgreSQL зі збереженням цілісності зв'язків моделей, генерацією чистих міграцій та 100% успішним проходженням існуючого набору тестів.
</MASTER_GOAL>

<EXECUTION_PLAN>
<STEP index="1">
  <ACTION>Зчитати поточний prisma/schema.prisma та виявити несумісні типи (enums, DateTime, BigInt)</ACTION>
  <VERIFICATION_GATE>Скласти список змін типів у tasks/todo.md</VERIFICATION_GATE>
</STEP>
<STEP index="2">
  <ACTION>Оновити datasource в schema.prisma на postgresql та скоригувати змінні в .env</ACTION>
  <VERIFICATION_GATE>Запустити `npx prisma validate` (exit code 0)</VERIFICATION_GATE>
</STEP>
<STEP index="3">
  <ACTION>Згенерувати початкову міграцію для PostgreSQL</ACTION>
  <VERIFICATION_GATE>Запустити `npx prisma migrate dev --name init_pg --create-only`</VERIFICATION_GATE>
</STEP>
<STEP index="4">
  <ACTION>Запустити повний тестовий набір сервісу</ACTION>
  <VERIFICATION_GATE>Виконати `npm test`</VERIFICATION_GATE>
  <CRITICAL_RULE>Якщо тести падають: проаналізувати помилку, не чіпати бізнес-логіку без крайньої потреби. Ліміт 3 спроби.</CRITICAL_RULE>
</STEP>
</EXECUTION_PLAN>

<LOOP_CONTROLS>
- State File: `tasks/todo.md`
- Circuit Breaker: Максимум 3 ітерації на виправлення однієї помилки.
- Stop Condition: Всі тести зелені, Prisma клієнт згенеровано.
</LOOP_CONTROLS>
```
