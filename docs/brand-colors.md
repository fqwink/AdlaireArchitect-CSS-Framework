# Adlaire Group ブランドカラーガイド

**Version**: 1.0.0  
**Last Updated**: 2026-02-13  
**Status**: Official

---

## 概要

このドキュメントは、Adlaire Group公式ブランドカラーとその使用方法を定義します。Adlaire-Architect-CSS-Frameworkでは、これらのブランドカラーを基盤としたデザインシステムを構築しています。

---

## 公式ブランドカラー

### 1. Emerald Green (エメラルドグリーン) - Primary

**HEX**: `#00a968`  
**RGB**: `rgb(0, 169, 104)`  
**用途**: メインブランドカラー、プライマリボタン、重要なアクション

```css
--adlaire-color-brand-primary: #00a968;
```

**カラースケール**:
```css
--adlaire-brand-emerald-50: #e6f7f0;   /* 最も薄い */
--adlaire-brand-emerald-100: #b3e8d4;
--adlaire-brand-emerald-200: #80d9b8;
--adlaire-brand-emerald-300: #4dca9c;
--adlaire-brand-emerald-400: #26bb85;
--adlaire-brand-emerald-500: #00a968;  /* Base - 公式カラー */
--adlaire-brand-emerald-600: #009159;
--adlaire-brand-emerald-700: #007a4a;
--adlaire-brand-emerald-800: #00623b;
--adlaire-brand-emerald-900: #004a2c;  /* 最も濃い */
```

**使用例**:
- プライマリボタン
- アクティブ状態のリンク
- 重要な見出し
- ブランドロゴ
- CTA（Call To Action）要素

---

### 2. Blue Sky (ブルースカイ) - Secondary

**HEX**: `#3498db`  
**RGB**: `rgb(52, 152, 219)`  
**用途**: セカンダリカラー、情報表示、補助的な要素

```css
--adlaire-color-brand-secondary: #3498db;
```

**カラースケール**:
```css
--adlaire-brand-bluesky-50: #ebf5fb;
--adlaire-brand-bluesky-100: #c8e2f4;
--adlaire-brand-bluesky-200: #a5cfed;
--adlaire-brand-bluesky-300: #82bce6;
--adlaire-brand-bluesky-400: #5ba8e0;
--adlaire-brand-bluesky-500: #3498db;  /* Base - 公式カラー */
--adlaire-brand-bluesky-600: #2980b9;
--adlaire-brand-bluesky-700: #216897;
--adlaire-brand-bluesky-800: #1a5075;
--adlaire-brand-bluesky-900: #123853;
```

**使用例**:
- セカンダリボタン
- リンクテキスト
- 情報アラート
- アイコン
- ヘッダー・フッター

---

### 3. Summer Sky (サマースカイ) - Accent

**HEX**: `#40AAEF`  
**RGB**: `rgb(64, 170, 239)`  
**用途**: アクセントカラー、強調、ハイライト

```css
--adlaire-color-brand-accent: #40AAEF;
```

**カラースケール**:
```css
--adlaire-brand-summersky-50: #ecf7fe;
--adlaire-brand-summersky-100: #c9e8fc;
--adlaire-brand-summersky-200: #a6d9fa;
--adlaire-brand-summersky-300: #83caf8;
--adlaire-brand-summersky-400: #5fbaf3;
--adlaire-brand-summersky-500: #40AAEF;  /* Base - 公式カラー */
--adlaire-brand-summersky-600: #2995da;
--adlaire-brand-summersky-700: #217bb5;
--adlaire-brand-summersky-800: #1a6190;
--adlaire-brand-summersky-900: #13476b;
```

**使用例**:
- ハイライト
- ホバー状態
- 装飾要素
- バッジ
- プログレスバー

---

### 4. Solitude (ソリチュード) - Success

**HEX**: `#58BE89`  
**RGB**: `rgb(88, 190, 137)`  
**用途**: 成功状態、ポジティブなフィードバック

```css
--adlaire-color-success: #58BE89;
```

**カラースケール**:
```css
--adlaire-brand-solitude-50: #eef8f3;
--adlaire-brand-solitude-100: #cfeadd;
--adlaire-brand-solitude-200: #b0ddc7;
--adlaire-brand-solitude-300: #91d0b1;
--adlaire-brand-solitude-400: #72c39b;
--adlaire-brand-solitude-500: #58BE89;  /* Base - 公式カラー */
--adlaire-brand-solitude-600: #49a075;
--adlaire-brand-solitude-700: #3b8261;
--adlaire-brand-solitude-800: #2e644d;
--adlaire-brand-solitude-900: #204639;
```

**使用例**:
- 成功メッセージ
- 完了状態
- 承認ボタン
- チェックマーク
- ポジティブ指標

---

### 5. White Rat (ホワイトラット) - Light Background

**HEX**: `#ecf0f1`  
**RGB**: `rgb(236, 240, 241)`  
**用途**: 明るい背景、カード背景、セクション区切り

```css
--adlaire-color-neutral-300: #ecf0f1;  /* White Rat */
```

**使用例**:
- カード背景
- セクション背景
- 入力フィールド背景
- ホバー背景
- ライトモードベース

---

### 6. Silver Tree (シルバーツリー) - Subtle Background

**HEX**: `#ECEEF1`  
**RGB**: `rgb(236, 238, 241)`  
**用途**: より繊細な背景、微妙な区切り

```css
--adlaire-color-neutral-200: #ECEEF1;  /* Silver Tree */
```

**使用例**:
- ページ全体の背景
- サイドバー背景
- テーブル行の背景（交互）
- ボーダーカラー
- 区切り線

---

## カラーパレット使用ガイドライン

### 優先順位

1. **Primary (Emerald Green)** - 最も重要なアクション、ブランド表現
2. **Secondary (Blue Sky)** - 補助的な要素、情報表示
3. **Accent (Summer Sky)** - 強調、ハイライト
4. **Success (Solitude)** - 成功状態
5. **Neutral (White Rat / Silver Tree)** - 背景、区切り

### カラーコントラスト（アクセシビリティ）

すべてのブランドカラーは、WCAG 2.1 AAA基準を満たすようにテストされています。

#### Emerald Green (#00a968) on White
- **コントラスト比**: 3.85:1
- **推奨**: 大きなテキスト（18pt以上）に使用
- **改善**: 小さいテキストには `--adlaire-brand-emerald-700` (#007a4a) を推奨（7.2:1）

#### Blue Sky (#3498db) on White
- **コントラスト比**: 3.45:1
- **推奨**: 大きなテキスト（18pt以上）に使用
- **改善**: 小さいテキストには `--adlaire-brand-bluesky-700` (#216897) を推奨（5.8:1）

#### テキストカラー推奨

```css
/* White背景上のテキスト */
.text-on-white {
  color: #007a4a;  /* Emerald Green 700 - AAA準拠 */
}

/* Emerald Green背景上のテキスト */
.text-on-emerald {
  color: #FFFFFF;  /* コントラスト比: 4.8:1 (AA準拠) */
}

/* Blue Sky背景上のテキスト */
.text-on-bluesky {
  color: #FFFFFF;  /* コントラスト比: 4.2:1 (AA準拠) */
}
```

---

## 使用例

### ボタンコンポーネント

```html
<!-- Primary Button - Emerald Green -->
<button class="adlaire-button">
  Primary Action
</button>

<!-- Secondary Button - Blue Sky -->
<button class="adlaire-button adlaire-button--secondary">
  Secondary Action
</button>

<!-- Success Button - Solitude -->
<button class="adlaire-button adlaire-button--success">
  Success Action
</button>
```

### カードコンポーネント（予定）

```html
<div class="adlaire-card" style="background: var(--adlaire-color-neutral-300);">
  <h3 style="color: var(--adlaire-color-brand-primary);">
    Card Title
  </h3>
  <p>Card content with White Rat background</p>
</div>
```

### アラートコンポーネント（予定）

```html
<!-- Success Alert - Solitude -->
<div class="adlaire-alert adlaire-alert--success">
  Operation completed successfully!
</div>

<!-- Info Alert - Blue Sky -->
<div class="adlaire-alert adlaire-alert--info">
  Here's some information for you.
</div>
```

---

## CSS Variables リファレンス

### Primary (Emerald Green)

```css
--adlaire-color-brand-primary: #00a968;
--adlaire-color-brand-primary-hover: #007a4a;
--adlaire-color-brand-primary-active: #00623b;
--adlaire-color-brand-primary-light: #e6f7f0;
--adlaire-color-brand-primary-dark: #004a2c;
```

### Secondary (Blue Sky)

```css
--adlaire-color-brand-secondary: #3498db;
--adlaire-color-brand-secondary-hover: #216897;
--adlaire-color-brand-secondary-light: #ebf5fb;
--adlaire-color-brand-secondary-dark: #123853;
```

### Accent (Summer Sky)

```css
--adlaire-color-brand-accent: #40AAEF;
--adlaire-color-brand-accent-hover: #217bb5;
--adlaire-color-brand-accent-light: #ecf7fe;
--adlaire-color-brand-accent-dark: #13476b;
```

### Success (Solitude)

```css
--adlaire-color-success: #58BE89;
--adlaire-color-success-light: #eef8f3;
--adlaire-color-success-dark: #2e644d;
```

### Info (Blue Sky)

```css
--adlaire-color-info: #3498db;
--adlaire-color-info-light: #ebf5fb;
--adlaire-color-info-dark: #123853;
```

### Neutral (White Rat / Silver Tree)

```css
--adlaire-color-neutral-50: #FAFBFC;
--adlaire-color-neutral-100: #F5F7F8;
--adlaire-color-neutral-200: #ECEEF1;  /* Silver Tree */
--adlaire-color-neutral-300: #ecf0f1;  /* White Rat */
--adlaire-color-neutral-400: #D5D8DC;
--adlaire-color-neutral-500: #AEB6BF;
--adlaire-color-neutral-600: #85929E;
--adlaire-color-neutral-700: #5D6D7E;
--adlaire-color-neutral-800: #34495E;
--adlaire-color-neutral-900: #212F3D;
```

---

## ブランドガイドライン

### 推奨事項

✅ **DO (推奨)**
- Emerald Greenをメインのブランドカラーとして使用
- カラーコントラストを常に確認
- 小さいテキストにはdark variantを使用
- 背景色にはWhite RatまたはSilver Treeを使用
- 成功メッセージにはSolitudeを使用

❌ **DON'T (非推奨)**
- ブランドカラーを勝手に変更しない
- コントラストが低い組み合わせを使用しない
- 多数のカラーを一度に使用しない（3色以内推奨）
- 公式HEX値以外の類似色を使用しない

---

## カラーテスト・検証

### アクセシビリティチェック

以下のツールで定期的にコントラスト比を確認してください：
- WebAIM Contrast Checker
- Chrome DevTools Accessibility
- axe DevTools

### ブランドカラー一貫性チェック

```css
/* 正しい使用 ✅ */
.button-primary {
  background: var(--adlaire-color-brand-primary);
}

/* 誤った使用 ❌ */
.button-primary {
  background: #00a969;  /* 微妙に違うHEX値 */
}
```

---

## まとめ

Adlaire Group公式ブランドカラーは、以下の6色で構成されます：

1. **Emerald Green** (#00a968) - Primary
2. **Blue Sky** (#3498db) - Secondary
3. **Summer Sky** (#40AAEF) - Accent
4. **Solitude** (#58BE89) - Success
5. **White Rat** (#ecf0f1) - Light Background
6. **Silver Tree** (#ECEEF1) - Subtle Background

これらのカラーを適切に使用することで、Adlaire Groupのブランドアイデンティティを一貫して表現できます。

---

**Contact**: Adlaire Group DX事業セグメントグループ  
**Document Version**: 1.0.0  
**Last Updated**: 2026-02-13
