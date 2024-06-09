# Vue 3 styleguide

Данный проект содержит базовые настройки typescript, eslint для vue 3.
За основу взят стайлгайд от airbnb https://github.com/airbnb/javascript.

## Использование

Нужно скопировать в свой проект файлы tsconfig, eslintrc и prettierrc, затем установить следующие пакеты:
- @typescript-eslint/eslint-plugin
- @typescript-eslint/parser
- eslint
- eslint-config-airbnb-base
- eslint-config-prettier
- eslint-plugin-prettier
- eslint-plugin-vue
- npm-run-all
- prettier
- eslint-import-resolver-typescript

```
npm i -D @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint eslint-config-airbnb-base eslint-config-prettier eslint-plugin-prettier eslint-plugin-vue npm-run-all prettier eslint-import-resolver-typescript 
```

Чтобы проверка отрабатывала при билде также нужно добавить в package.json следующие команды:

- "build": "npm-run-all lint typecheck build-only",
- "build-only": "vite build",
- "preview": "vite preview",
- "lint": "eslint . --ext .vue,.js,.jsx,.cjs,.mjs,.ts,.tsx,.cts,.mts",
- "lint:fix": "eslint . --ext .vue,.js,.jsx,.cjs,.mjs --fix",
- "typecheck": "vue-tsc"

Команда lint проверит код проекта на соответствие правилам eslint, lint:fix попытается устранить ошибки автоматически, typecheck проверяет ошибки typescript.

### Доработка стайлгайда

Если в процессе работы окажется, что какие-то правила скорее мешают чем помогают, можно создать пулл реквест в этот репозиторий с необходимыми исправлениями. Также стоит учесть, что в tsconfig в данном проекте выставлен strict true, ее можно по необходимости выключить (если ваш проект, скажем, мигрирует с жс на тс, или ошибок слишком много, тогда можно действовать постепенно).