## [`Turborepo`](https://turbo.build/repo/docs)

<br />

## 子工程构建步骤

### 一、使用 `cli` 构建模版

<br />

### 二、【可选】项目配置 `eslint`

#### 2.1 安装 `eslint` `@lousanpang/eslint-config`

```bash
cd apps/web/[projectName]
pnpm add eslint -D
pnpm add @lousanpang/eslint-config -D --workspace
```

#### 2.2 创建 `eslint.config.mjs` 配置文件

```js
// eslint.config.mjs
import antfu from '@lousanpang/eslint-config'

export default antfu
```

#### 2.3 `package.json` 配置

```json
// package.json
{
  "scripts": {
    "lint": "eslint .",
    "lint:fix": "eslint . --fix"
  },
  "devDependencies": {
    "@lousanpang/eslint-config": "workspace:*",
    "eslint": "^9.9.1"
  }
}
```

#### 2.4 使用

```bash
pnpm lint:fix
```

<br />

### 三、【可选】项目配置 `typescript`

#### 3.1 安装 `typescript` `@lousanpang/typescript-config`

```bash
cd apps/web/[projectName]
pnpm add typescript -D
pnpm add @lousanpang/typescript-config -D --workspace
```

#### 3.2 添加 `tsconfig.json`

```json
// tsconfig.json
{
  "extends": "@lousanpang/typescript-config/base.json",
  "compilerOptions": {
    "outDir": "dist",
    "rootDir": "src"
  },
  "include": [
    "src"
  ],
  "exclude": [
    "node_modules",
    "dist"
  ]
}
```

<br />

### 四、【可选】项目配置 `UI` 组件库

```js
import Counter from '@lousanpang/ui/counter'

<Counter />
```

<br />

### 五、【可选】项目配置 `request` 请求拦截库

<br />

### 六、【可选】项目配置 `utils` 工具库

#### 6.1 安装 `@lousanpang/utils`

```bash
cd apps/web/[projectName]
pnpm add @lousanpang/utils -D --workspace
```

#### 6.2 使用 `@lousanpang/utils` 工具库

```js
import { add } from '@lousanpang/utils/add'

add(1, 2)
```
