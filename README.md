# etude-next-prisma

## 勉強中

```bash
npm install prisma --save-dev
npx prisma init
direnv allow
```

### .env

```.env
DATABASE_URL=******************
```

### Prisma-schemaに基づいてデータベースにテーブル作成

```bash
npx prisma db push
```

### Prisma Studio

```bash
npx prisma studio
```

### Install Prisma Client

```bash
npm install @prisma/client
```

### Edit Prisma Schema

```bash
npx prisma generate
```

```lib
mkdir lib && touch lib/prisma.ts
```

```Make prisma.ts
// lib/prisma.ts
import { PrismaClient } from '@prisma/client';

let prisma: PrismaClient;

if (process.env.NODE_ENV === 'production') {
  prisma = new PrismaClient();
} else {
  if (!global.prisma) {
    global.prisma = new PrismaClient();
  }
  prisma = global.prisma;
}

export default prisma;
```

```bash
npm install next-auth@4 @next-auth/prisma-adapter
```

```.env
DATABASE_URL=******************
GITHUB_ID=******************
GITHUB_SECRET=******************
NEXTAUTH_URL==******************
```
