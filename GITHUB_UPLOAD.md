# GitHub リポジトリへのアップロード手順

**プロジェクト**: Adlaire-Architect-CSS-Framework  
**バージョン**: 0.2.0  
**日付**: 2026年2月13日  
**リポジトリ**: https://github.com/fqwink/AdlaireArchitect-CSS-Framework

---

## 📦 現在の状況

### Git履歴
```
b34945f feat: Implement Typography System component
58f7b85 feat: Integrate official Adlaire Group brand colors
439e445 docs: Add comprehensive project summary report
c813d94 feat: Implement core CSS framework with differentiation features
b10374d docs: Add CSS framework trend research and initial project documentation
```

**Total Commits**: 5  
**Branch**: main

---

## 🚀 Method 1: GitHub CLIを使用（推奨）

### 前提条件
GitHub CLIがインストールされている必要があります。

### 手順

```bash
# 1. GitHub CLIで認証
gh auth login

# 2. リポジトリに移動
cd /home/user/webapp

# 3. リモートリポジトリを確認
git remote -v

# 4. Push
git push -u origin main
```

---

## 🚀 Method 2: Personal Access Token (PAT)を使用

### 手順

#### 1. GitHub Personal Access Tokenを生成

1. GitHubにログイン
2. Settings → Developer settings → Personal access tokens → Tokens (classic)
3. "Generate new token (classic)" をクリック
4. 以下を設定：
   - Note: `Adlaire-Architect-CSS-Framework`
   - Expiration: 任意（90 days推奨）
   - Scopes: ✅ `repo` (すべて選択)
5. "Generate token" をクリック
6. **トークンをコピー**（表示は1回のみ）

#### 2. Git認証情報を設定

```bash
cd /home/user/webapp

# リモートURLを更新（PATを使用）
git remote set-url origin https://<YOUR_PAT>@github.com/fqwink/AdlaireArchitect-CSS-Framework.git

# Push
git push -u origin main
```

**注意**: `<YOUR_PAT>` を生成したトークンに置き換えてください。

---

## 🚀 Method 3: SSH Keyを使用

### 手順

#### 1. SSH Keyを生成

```bash
# SSH Key生成
ssh-keygen -t ed25519 -C "your_email@example.com"

# SSH Agent起動
eval "$(ssh-agent -s)"

# SSH Keyを追加
ssh-add ~/.ssh/id_ed25519

# 公開鍵を表示
cat ~/.ssh/id_ed25519.pub
```

#### 2. GitHubにSSH Keyを追加

1. GitHubにログイン
2. Settings → SSH and GPG keys
3. "New SSH key" をクリック
4. Title: `Adlaire Dev Environment`
5. Key: 公開鍵の内容を貼り付け
6. "Add SSH key" をクリック

#### 3. リモートURLを変更してPush

```bash
cd /home/user/webapp

# リモートURLをSSHに変更
git remote set-url origin git@github.com:fqwink/AdlaireArchitect-CSS-Framework.git

# 接続テスト
ssh -T git@github.com

# Push
git push -u origin main
```

---

## 🚀 Method 4: 手動アップロード（最終手段）

### バックアップファイル

作成済みのバックアップ:
```
/home/user/adlaire-architect-css-framework-v0.2.0.tar.gz (136KB)
```

### 手順

#### 1. ローカルにバックアップをダウンロード

サンドボックスからバックアップファイルをダウンロード

#### 2. ローカルで展開

```bash
# ローカル環境で
tar -xzf adlaire-architect-css-framework-v0.2.0.tar.gz
cd webapp
```

#### 3. Gitリポジトリとして初期化（必要に応じて）

```bash
# 既存のリポジトリをクローン
git clone https://github.com/fqwink/AdlaireArchitect-CSS-Framework.git
cd AdlaireArchitect-CSS-Framework

# ファイルをコピー
cp -r ../webapp/* .

# Add & Commit
git add .
git commit -m "feat: Complete implementation of brand colors and typography system

- Integrate Adlaire Group official brand colors
- Implement complete Typography System
- Add component priority documentation
- Update all documentation and demos"

# Push
git push origin main
```

---

## 📝 Push後の確認事項

### リポジトリ確認
✅ すべてのファイルがアップロードされているか  
✅ コミット履歴が正しいか  
✅ ブランチがmainになっているか

### ファイル確認（18ファイル）
```
✅ README.md
✅ CHANGELOG.md
✅ PROJECT_SUMMARY.md
✅ package.json
✅ .gitignore
✅ docs/specification.md
✅ docs/brand-colors.md
✅ docs/component-priority.md
✅ research/css-framework-trends-2026.md
✅ examples/demo.html
✅ src/adlaire-architect.css
✅ src/core/layers.css
✅ src/core/reset.css
✅ src/tokens/adlaire-brand.css
✅ src/tokens/root.css
✅ src/layouts/container.css
✅ src/components/buttons.css
✅ src/components/typography.css
```

---

## 🎯 Push成功後のタスク

### 1. GitHubリポジトリの設定

#### About セクション
- Description: `Modern, lightweight CSS framework with Adlaire Group brand colors - Container Queries First, Pure CSS3, Accessibility First`
- Website: デモサイトURL（デプロイ後）
- Topics: `css`, `css-framework`, `container-queries`, `pure-css`, `accessibility`, `design-system`, `adlaire`

#### README バッジの追加
```markdown
![Version](https://img.shields.io/badge/version-0.2.0-green)
![License](https://img.shields.io/badge/license-TBD-blue)
![CSS3](https://img.shields.io/badge/CSS3-Pure-1572B6?logo=css3)
```

### 2. GitHub Pages設定（オプション）

1. Settings → Pages
2. Source: `main` branch, `/docs` または `/examples` folder
3. デモサイトを公開

### 3. GitHub Releases

1. Releases → Create a new release
2. Tag: `v0.2.0`
3. Title: `v0.2.0 - Brand Colors & Typography System`
4. Description: CHANGELOGから内容をコピー
5. Attach: バックアップアーカイブ

---

## ❌ トラブルシューティング

### エラー: "Authentication failed"
→ Personal Access Tokenを使用（Method 2）

### エラー: "remote rejected"
→ force pushを試す: `git push -f origin main`

### エラー: "Permission denied"
→ SSH Keyを確認（Method 3）

### エラー: "Repository not found"
→ リポジトリURLを確認: `git remote -v`

---

## 📞 サポート

問題が発生した場合：
1. Git状態を確認: `git status`
2. リモート確認: `git remote -v`
3. 認証確認: Personal Access Tokenが正しいか
4. 最終手段: Method 4（手動アップロード）

---

## ✅ 完了チェックリスト

- [ ] GitHubに正常にPush完了
- [ ] すべてのファイル確認
- [ ] コミット履歴確認
- [ ] README適切に表示
- [ ] デモページ動作確認（GitHub Pagesの場合）
- [ ] Aboutセクション設定
- [ ] Releasesタグ作成
- [ ] Topicsタグ追加

---

**最終更新**: 2026年2月13日  
**プロジェクトステータス**: Ready for Production (Phase 2.2 完了)
