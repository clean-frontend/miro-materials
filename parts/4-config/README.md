**1 Добавляем типы переменных окружения**

Переименумем `src/shared/vite-env.d.ts` -> `src/shared/env.d.ts`

И отредактируем содержимое
`shared/env.d.ts`

```tsx
/// <reference types="vite/client" />

interface ImportMetaEnv {
  readonly VITE_API_BASE_URL: string;
}

interface ImportMeta {
  readonly env: ImportMetaEnv;
}
```

**2 Добавляем фасад над переменными окружения**

`src/shared/model/config.ts`

```ts
export const CONFIG = {
  API_BASE_URL: import.meta.env.VITE_API_BASE_URL,
};
```

**3 Добавляем переменные окружения для разработки**

`.env.development`

```
VITE_API_BASE_URL=http://localhost:3000
```

**4 Тестируем `CONFIG.API_BASE_URL`**
