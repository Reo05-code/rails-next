# Rails Next.js Zenn Clone

Docker を使わない Rails API + Next.js の開発環境

## プロジェクト構成

```
rails-next-zenn-clone/
├── backend/     # Rails API (ポート: 3000)
└── frontend/    # Next.js (ポート: 3001)
```

## 必要な環境

- Ruby 3.1.3
- Rails 7.2.3
- Node.js 24.11.0
- MySQL 8.0

## セットアップ

### 1. Rails API (backend)

```bash
cd backend
bundle install
bin/rails db:create
bin/rails db:migrate
```

### 2. Next.js (frontend)

```bash
cd frontend
npm install
```

## 起動方法

### Rails API サーバーを起動 (ターミナル1)

```bash
cd backend
bin/rails server
```

Rails API は `http://localhost:3000` で起動します。

### Next.js 開発サーバーを起動 (ターミナル2)

```bash
cd frontend
npm run dev
```

Next.js は `http://localhost:3001` で起動します。

## データベース設定

- ホスト: localhost
- ポート: 3306
- ユーザー: root
- パスワード: password
- 開発用DB: zenn_clone_development
- テスト用DB: zenn_clone_test

## CORS設定

Rails API は `http://localhost:3001` (Next.js) からのリクエストを許可するように設定されています。

## 環境変数

### frontend/.env.local

```
NEXT_PUBLIC_API_URL=http://localhost:3000
```
# rails-next
