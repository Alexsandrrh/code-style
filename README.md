# Code Style

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
 * */
export interface ComponentProps {}

/**
 * @description Компонент.
 * */
export const Component: FC<ComponentProps> = () => {
  return null;
};

Component.displayName = "Component";
```