# SnapCart（DevOps 期末実技）

Node.js アプリの Docker 化と GitHub Actions（lint → test → build-and-push）の課題用リポジトリです。

## 提出用スクリーンショット（課題指定の順番）

画像は **`screenshots/`** に置き、**ファイル名は課題指定どおり**（提出・採点で名前が求められるため）。この README からは次のパスで表示します。

### 1. プロジェクト構成（`project_structure.png`）

ターミナルで `ls -la` 等、必要ファイルが揃っていること。時刻・GitHub ユーザー名が分かること。

![project_structure](screenshots/project_structure.png)

### 2. ローカルテスト成功（`local_test_pass.png`）

`npm test` がローカルで成功していること。時刻が分かること。

![local_test_pass](screenshots/local_test_pass.png)

### 3. ローカル Docker（`local_docker_run.png`）

`docker run` と `curl /health` で `{"status":"ok"}` が返ること。

![local_docker_run](screenshots/local_docker_run.png)

### 4. CI 全ジョブ成功（`ci_all_green.png`）

GitHub Actions で `lint` → `test` → `build-and-push` がすべて緑であること。

![ci_all_green](screenshots/ci_all_green.png)

### 5. GHCR のイメージ（`ghcr_image.png`）

GitHub Packages（GHCR）にイメージが表示されていること。

![ghcr_image](screenshots/ghcr_image.png)

## ローカルでの動作確認

```bash
npm ci
npm run lint
npm test
npm start
# 別ターミナル: curl http://localhost:3000/health
```

## Docker（ローカル）

```bash
docker build -t snapcart-exam:local .
docker run --rm -p 3000:3000 snapcart-exam:local
# 別ターミナル: curl http://localhost:3000/health
```
