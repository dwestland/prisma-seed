# prisma3-seed

## Notes from creating this repository

**Prisma 3 has some breaking changes for seed**

**Started with the next-typescript-prettier-eslint repository**

**Start dev:**

```
npm run dev
```

**Add dev dependencies:**

```
npm i -D prisma ts-node
```

**Add dependencies:**

```
npm i @prisma/client
```

npx prisma init

**Add files: data/links.ts, prisma/seed.ts and add schema to prisma/schema.prisma file**

**Had ESLint issue with seed.ts importing data/links.ts add the following to .eslintrc.js:**

**Added to the rules object to the .eslintrc.js file:**

```
  extends: [
    ...
    'plugin:import/typescript',
  ],
```

**Added to the rules object to the .eslintrc.js file:**

```
  rules: {
    ...
    'import/extensions': [
      'error',
      'ignorePackages',
      {
        js: 'never',
        jsx: 'never',
        ts: 'never',
        tsx: 'never',
      },
    ],
    'no-console': 'off',
  }
```

**Prisma 3 has a braking change for seed. Add to the package.json object:**

```
  "prisma": {
    "seed": "ts-node --compiler-options {\"module\":\"CommonJS\"} prisma/seed.ts"
  },
```

**Create new database named "prisma_seed"**

**Add DATABASE_URL to the .env file**

**Run migrate to create database tables:**

```
npx prisma migrate dev --name init
```

**Evoke Prisma seed:**

```
npx prisma db seed
```

### Settings are from:

**Overview of the part-2 Branch:**

https://www.youtube.com/watch?v=-x7yENX3s9M

**Use the part-2 branch:**

https://github.dev/m-abdelwahab/awesome-links
