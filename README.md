# Code Style

## Именование файлов и папок

- Все директории и файлы именуйте в `kebab-case`, чтобы соблюдать единый стиль (`my-component`, `my-component/button.tsx`).
- Не используйте файлы `index.tsx` или `index.jsx` для компонентов — делайте явные имена; исключение допускается только для роутинга.
- Исключения допускаются лишь для файлов, предписанных внешними инструментами или стандартами (например, `package.json`).

Пример структуры:

```text
src/
├── components/
│   └── user-card/
│       ├── user-card.tsx
│       ├── user-card.module.css
│       └── user-card.test.tsx
└── pages/
    └── dashboard/
        ├── index.tsx
        └── dashboard.tsx
```

## Как писать React-компонент

- Описывайте публичный контракт компонента через `interface` с префиксом `Props`, чтобы типизация была очевидна.
- Сам компонент объявляйте как `const` c типом `FC<ComponentProps>`, чтобы сразу задать сигнатуру `children` и подсказки IDE.
- Возвращайте `null`, если на момент объявления компонент выступает заглушкой, и постепенно заменяйте на реальную разметку.
- Присваивайте `displayName`, чтобы упростить отладку и работу React DevTools.
- Сопровождайте интерфейс и компонент JSDoc-комментариями на русском или английском языке — они участвуют в генерации документации и облегчают навигацию по коду.

```typescript
import type { FC } from "react";

/**
 * @description Свойства "Компонента".
 */
export interface ComponentProps {}

/**
 * @description Компонент.
 */
export const Component: FC<ComponentProps> = () => null;

Component.displayName = "Component";
```
