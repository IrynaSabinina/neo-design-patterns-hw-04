# neo-design-patterns-hw-04

# Патерни проєктування в TypeScript: Singleton, Builder, Prototype

Цей репозиторій містить реалізацію трьох класичних патернів проєктування у мові TypeScript:

- ✅ Singleton
- ✅ Builder
- ✅ Prototype

Кожен патерн реалізовано у власній директорії під `/src`.

---

## 📦 Структура проєкту

src/
├── singleton/
│ ├── AppConfigService.ts
│ └── main.ts
├── builder/
│ ├── DocumentBuilder.ts
│ └── main.ts
└── prototype/
├── UserProfilePrototype.ts
├── UserProfile.ts
└── main.ts

---

---

## Патерн Singleton

**Ціль:** Забезпечити, щоб у системі існував лише один екземпляр класу AppConfigService.

### 📁 `/src/singleton`

- `AppConfigService.ts`: Реалізація Singleton.
- `main.ts`: Демонстрація єдиного екземпляру.

### ✅ Результат

```ts
const config1 = AppConfigService.getInstance();
const config2 = AppConfigService.getInstance();

console.log(config1 === config2); // true
```

---

## Патерн Builder

Ціль: Централізоване та контрольоване створення документів із заголовком, тілом та підписом.

📁 /src/builder
DocumentBuilder.ts: Клас із методами для додавання частин документа.

main.ts: Приклад використання.

=== ACME Corporation — Report ===

Quarterly performance increased by 12%.

--- Confidential ---

---

## Патерн Prototype

Ціль: Швидке створення нових об’єктів на основі вже наявних профілів користувачів (глибоке клонування).

📁 /src/prototype
UserProfilePrototype.ts: Інтерфейс з методом clone().

UserProfile.ts: Клас з реалізацією та глибоким копіюванням.

main.ts: Приклад клонування об’єкта.

const chief = new UserProfile(...);
const deputy = chief.clone() as UserProfile;
deputy.username = "Інший користувач";

console.log(chief); // Не змінений
console.log(deputy); // Незалежна копія

---

## Запуск

Встановити залежності:

npm install

Запустити приклади:

npx ts-node src/singleton/main.ts
npx ts-node src/builder/main.ts
npx ts-node src/prototype/main.ts
