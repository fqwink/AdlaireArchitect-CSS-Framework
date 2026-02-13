# Adlaire Architect CSS Framework - 仕様書 v0.1

**作成日**: 2026年2月13日  
**ステータス**: Draft  
**対象バージョン**: 1.0.0

---

## 1. プロジェクトビジョン

Adlaire-Architect-CSS-Frameworkは、**差別化要素を最重要視**した次世代CSSフレームワークです。

### 1.1 コアバリュー（差別化の4本柱）

#### 🎨 **1. Adlaire Group専用デザイントークンシステム**
**目的**: ブランドアイデンティティの一貫性と、デザインシステムの体系化

**特徴**:
- Adlaire Group固有のブランドカラーパレット
- 企業アイデンティティに基づく視覚言語
- プロジェクト間での一貫性保証
- カスタマイズ可能な設計（他企業でも利用可能）

**実装方針**:
```css
/* Adlaire Brandカラーの例（仮） */
:root {
  /* Primary Brand Colors - Adlaire Group Identity */
  --adlaire-brand-primary: #0052CC;
  --adlaire-brand-secondary: #00B8D4;
  --adlaire-brand-accent: #FF5722;
  
  /* Semantic Colors */
  --adlaire-success: #00C853;
  --adlaire-warning: #FFD600;
  --adlaire-error: #D50000;
  --adlaire-info: #2979FF;
}
```

#### 📦 **2. Container Queries First 設計**
**目的**: 2026年最新技術による真のコンポーネント駆動型開発

**特徴**:
- メディアクエリではなくContainer Queriesを優先
- コンポーネント単位でのレスポンシブ対応
- 再利用性の最大化
- コンテキストに依存しないコンポーネント

**差別化ポイント**:
- 既存フレームワーク（Bootstrap, Tailwind）はまだContainer Queries対応が不十分
- Adlaireは最初からContainer Queries Firstで設計

**実装例**:
```css
/* 従来のメディアクエリ（ビューポート依存） */
@media (min-width: 768px) {
  .card { /* ... */ }
}

/* Adlaireのアプローチ（コンテナ依存） */
.card-container {
  container-type: inline-size;
  container-name: card;
}

@container card (min-width: 400px) {
  .card {
    display: grid;
    grid-template-columns: 1fr 2fr;
  }
}
```

#### ⚡ **3. 極限の軽量性とモジュラー設計**
**目的**: パフォーマンスファースト、必要最小限の読み込み

**目標値**:
- **Core CSS**: < 8KB (gzipped)
- **Full Bundle**: < 25KB (gzipped)
- **Individual Module**: 1-3KB each

**モジュラーシステム**:
```html
<!-- 必要なモジュールのみ読み込み -->
<link rel="stylesheet" href="adlaire-architect.core.css">
<link rel="stylesheet" href="adlaire-architect.buttons.css">
<link rel="stylesheet" href="adlaire-architect.forms.css">
```

**競合比較**:
| Framework | Core Size (gzipped) | 差別化 |
|-----------|---------------------|--------|
| Bootstrap 5 | ~25KB | ❌ |
| Tailwind CSS | 可変（~10-50KB） | △ |
| Bulma | ~30KB | ❌ |
| **Adlaire** | **< 8KB** | ✅ **3倍以上軽量** |

#### ♿ **4. アクセシビリティファースト**
**目的**: WCAG 2.1 AAA準拠を標準とする

**特徴**:
- すべてのコンポーネントがアクセシビリティ標準準拠
- カラーコントラスト自動チェック機能
- スクリーンリーダー完全対応
- キーボードナビゲーション完全サポート

**差別化ポイント**:
- 多くのフレームワークはAA準拠止まり
- AdlaireはAAA準拠を標準とする

**実装基準**:
```css
/* カラーコントラスト比 7:1以上（AAA基準） */
.adlaire-button {
  background: var(--adlaire-brand-primary);
  color: #FFFFFF; /* Contrast ratio: 8.5:1 */
}

/* フォーカス状態の明確化 */
.adlaire-button:focus-visible {
  outline: 3px solid var(--adlaire-focus-color);
  outline-offset: 2px;
}
```

---

## 2. 技術仕様

### 2.1 CSS アーキテクチャ

#### レイヤー構造（CSS @layer使用）

```css
@layer reset, tokens, layouts, components, utilities, themes;

/* 詳細度の自動管理 */
@layer reset {
  /* リセットCSS */
}

@layer tokens {
  /* デザイントークン定義 */
}

@layer components {
  /* コンポーネントスタイル */
}

@layer utilities {
  /* ユーティリティクラス */
}

@layer themes {
  /* テーマオーバーライド */
}
```

#### BEM命名規則（拡張版）

```css
/* Block */
.adlaire-[component-name] { }

/* Element */
.adlaire-[component-name]__[element] { }

/* Modifier */
.adlaire-[component-name]--[modifier] { }

/* State */
.adlaire-[component-name].is-[state] { }

/* Container Query Variant */
.adlaire-[component-name]\@[container-size] { }
```

**例**:
```css
/* Button Component */
.adlaire-button { }
.adlaire-button__icon { }
.adlaire-button--primary { }
.adlaire-button--large { }
.adlaire-button.is-loading { }
.adlaire-button\@sm { }
```

### 2.2 デザイントークン体系

#### 階層構造

```
Primitive Tokens (基本トークン)
    ↓
Semantic Tokens (意味的トークン)
    ↓
Component Tokens (コンポーネント固有トークン)
```

#### 実装例

```css
:root {
  /* ========================================
     PRIMITIVE TOKENS (基本トークン)
     ======================================== */
  
  /* Color Primitives */
  --primitive-blue-50: #E3F2FD;
  --primitive-blue-100: #BBDEFB;
  --primitive-blue-500: #2196F3;
  --primitive-blue-900: #0D47A1;
  
  /* Spacing Primitives (8pt Grid System) */
  --primitive-space-0: 0;
  --primitive-space-1: 0.25rem;   /* 4px */
  --primitive-space-2: 0.5rem;    /* 8px */
  --primitive-space-3: 0.75rem;   /* 12px */
  --primitive-space-4: 1rem;      /* 16px */
  --primitive-space-6: 1.5rem;    /* 24px */
  --primitive-space-8: 2rem;      /* 32px */
  --primitive-space-12: 3rem;     /* 48px */
  --primitive-space-16: 4rem;     /* 64px */
  
  /* ========================================
     SEMANTIC TOKENS (意味的トークン)
     ======================================== */
  
  /* Adlaire Brand Identity */
  --adlaire-color-brand-primary: var(--primitive-blue-500);
  --adlaire-color-brand-primary-hover: var(--primitive-blue-900);
  --adlaire-color-brand-primary-light: var(--primitive-blue-50);
  
  /* Semantic Colors */
  --adlaire-color-success: #00C853;
  --adlaire-color-warning: #FFD600;
  --adlaire-color-error: #D50000;
  --adlaire-color-info: #2979FF;
  
  /* Neutral Colors */
  --adlaire-color-neutral-50: #FAFAFA;
  --adlaire-color-neutral-100: #F5F5F5;
  --adlaire-color-neutral-500: #9E9E9E;
  --adlaire-color-neutral-900: #212121;
  
  /* Text Colors */
  --adlaire-color-text-primary: var(--adlaire-color-neutral-900);
  --adlaire-color-text-secondary: var(--adlaire-color-neutral-500);
  --adlaire-color-text-inverse: #FFFFFF;
  
  /* Spacing Scale */
  --adlaire-space-xs: var(--primitive-space-1);
  --adlaire-space-sm: var(--primitive-space-2);
  --adlaire-space-md: var(--primitive-space-4);
  --adlaire-space-lg: var(--primitive-space-6);
  --adlaire-space-xl: var(--primitive-space-8);
  --adlaire-space-2xl: var(--primitive-space-12);
  
  /* Typography Scale */
  --adlaire-font-size-xs: 0.75rem;    /* 12px */
  --adlaire-font-size-sm: 0.875rem;   /* 14px */
  --adlaire-font-size-base: 1rem;     /* 16px */
  --adlaire-font-size-lg: 1.125rem;   /* 18px */
  --adlaire-font-size-xl: 1.25rem;    /* 20px */
  --adlaire-font-size-2xl: 1.5rem;    /* 24px */
  --adlaire-font-size-3xl: 1.875rem;  /* 30px */
  --adlaire-font-size-4xl: 2.25rem;   /* 36px */
  
  /* Line Heights */
  --adlaire-line-height-tight: 1.25;
  --adlaire-line-height-normal: 1.5;
  --adlaire-line-height-relaxed: 1.75;
  
  /* Border Radius */
  --adlaire-radius-none: 0;
  --adlaire-radius-sm: 0.25rem;   /* 4px */
  --adlaire-radius-md: 0.5rem;    /* 8px */
  --adlaire-radius-lg: 1rem;      /* 16px */
  --adlaire-radius-full: 9999px;
  
  /* Shadows */
  --adlaire-shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
  --adlaire-shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
  --adlaire-shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
  --adlaire-shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
  
  /* Transitions */
  --adlaire-transition-fast: 150ms;
  --adlaire-transition-base: 250ms;
  --adlaire-transition-slow: 350ms;
  --adlaire-easing-default: cubic-bezier(0.4, 0, 0.2, 1);
  
  /* Z-index Scale */
  --adlaire-z-dropdown: 1000;
  --adlaire-z-sticky: 1100;
  --adlaire-z-fixed: 1200;
  --adlaire-z-modal-backdrop: 1300;
  --adlaire-z-modal: 1400;
  --adlaire-z-tooltip: 1500;
}
```

### 2.3 Container Queries システム

#### Container Query Breakpoints

```css
:root {
  /* Container Query Breakpoints */
  --adlaire-container-xs: 320px;
  --adlaire-container-sm: 480px;
  --adlaire-container-md: 768px;
  --adlaire-container-lg: 1024px;
  --adlaire-container-xl: 1280px;
}

/* Container Types */
.adlaire-container {
  container-type: inline-size;
}

.adlaire-container--named {
  container-name: adlaire-main;
}
```

#### レスポンシブコンポーネントパターン

```css
/* Card Component with Container Queries */
.adlaire-card {
  display: flex;
  flex-direction: column;
  background: var(--adlaire-color-neutral-50);
  border-radius: var(--adlaire-radius-md);
  padding: var(--adlaire-space-md);
}

/* Small container: Stack vertically */
@container (min-width: 320px) {
  .adlaire-card {
    gap: var(--adlaire-space-sm);
  }
}

/* Medium container: Side by side */
@container (min-width: 480px) {
  .adlaire-card {
    flex-direction: row;
    gap: var(--adlaire-space-md);
  }
  
  .adlaire-card__image {
    flex: 0 0 40%;
  }
  
  .adlaire-card__content {
    flex: 1;
  }
}

/* Large container: Enhanced layout */
@container (min-width: 768px) {
  .adlaire-card {
    padding: var(--adlaire-space-lg);
    gap: var(--adlaire-space-lg);
  }
  
  .adlaire-card__image {
    flex: 0 0 35%;
  }
}
```

### 2.4 モジュラーシステム

#### ファイル構成（最終版）

```
/src
  /core
    - layers.css              # @layer 定義
    - reset.css               # モダンリセット
    - root.css                # :root トークン定義
  
  /tokens
    - primitives.css          # 基本トークン
    - semantic.css            # 意味的トークン
    - adlaire-brand.css       # Adlaireブランド固有
    
  /layouts
    - container.css           # Container Query対応コンテナ
    - grid.css                # CSS Grid システム
    - flexbox.css             # Flexbox ユーティリティ
    - stack.css               # Vertical/Horizontal Stack
    
  /components
    - buttons.css             # ボタンコンポーネント
    - forms.css               # フォーム要素
    - cards.css               # カードコンポーネント
    - navigation.css          # ナビゲーション
    - alerts.css              # アラート/通知
    - modals.css              # モーダル
    - tabs.css                # タブ
    - accordion.css           # アコーディオン
    - badges.css              # バッジ
    - breadcrumbs.css         # パンくずリスト
    - pagination.css          # ページネーション
    - tables.css              # テーブル
    
  /utilities
    - spacing.css             # margin, padding
    - colors.css              # color, background
    - typography.css          # font, text utilities
    - display.css             # display, visibility
    - flexbox-utils.css       # flex utilities
    - grid-utils.css          # grid utilities
    - borders.css             # border utilities
    - shadows.css             # shadow utilities
    - transitions.css         # transition utilities
    
  /themes
    - default.css             # デフォルトテーマ
    - dark.css                # ダークモード
    - high-contrast.css       # 高コントラスト（アクセシビリティ）
    - adlaire-brand-light.css # Adlaireブランド（ライト）
    - adlaire-brand-dark.css  # Adlaireブランド（ダーク）
```

#### ビルドバリエーション

```
/dist
  - adlaire-architect.css              # フルバンドル
  - adlaire-architect.min.css          # 最小化版
  
  - adlaire-architect.core.css         # コアのみ（tokens + reset）
  - adlaire-architect.core.min.css
  
  - adlaire-architect.components.css   # コンポーネントのみ
  - adlaire-architect.components.min.css
  
  - adlaire-architect.utilities.css    # ユーティリティのみ
  - adlaire-architect.utilities.min.css
  
  /modules                             # 個別モジュール
    - buttons.css
    - forms.css
    - cards.css
    ... (各コンポーネント)
```

---

## 3. コンポーネント仕様

### 3.1 Button Component（詳細仕様）

#### バリエーション

```css
/* Base Button */
.adlaire-button {
  /* Container Query対応 */
  container-type: inline-size;
  
  /* Base Styles */
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: var(--adlaire-space-sm);
  
  padding: var(--adlaire-space-sm) var(--adlaire-space-md);
  
  font-family: inherit;
  font-size: var(--adlaire-font-size-base);
  font-weight: 500;
  line-height: var(--adlaire-line-height-normal);
  text-decoration: none;
  white-space: nowrap;
  
  background: var(--adlaire-color-brand-primary);
  color: var(--adlaire-color-text-inverse);
  
  border: 2px solid transparent;
  border-radius: var(--adlaire-radius-md);
  
  cursor: pointer;
  user-select: none;
  
  transition: all var(--adlaire-transition-base) var(--adlaire-easing-default);
  
  /* Accessibility */
  outline: none;
}

/* Focus State (Accessibility First) */
.adlaire-button:focus-visible {
  outline: 3px solid var(--adlaire-color-brand-primary);
  outline-offset: 2px;
  box-shadow: 0 0 0 4px rgba(33, 150, 243, 0.2);
}

/* Hover State */
.adlaire-button:hover:not(:disabled) {
  background: var(--adlaire-color-brand-primary-hover);
  transform: translateY(-1px);
  box-shadow: var(--adlaire-shadow-md);
}

/* Active State */
.adlaire-button:active:not(:disabled) {
  transform: translateY(0);
  box-shadow: var(--adlaire-shadow-sm);
}

/* Disabled State */
.adlaire-button:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

/* ========================================
   SIZE VARIANTS
   ======================================== */

.adlaire-button--small {
  padding: var(--adlaire-space-xs) var(--adlaire-space-sm);
  font-size: var(--adlaire-font-size-sm);
  gap: var(--adlaire-space-xs);
}

.adlaire-button--large {
  padding: var(--adlaire-space-md) var(--adlaire-space-lg);
  font-size: var(--adlaire-font-size-lg);
  gap: var(--adlaire-space-md);
}

/* ========================================
   COLOR VARIANTS
   ======================================== */

.adlaire-button--secondary {
  background: var(--adlaire-color-neutral-500);
  color: var(--adlaire-color-text-inverse);
}

.adlaire-button--secondary:hover:not(:disabled) {
  background: var(--adlaire-color-neutral-900);
}

.adlaire-button--success {
  background: var(--adlaire-color-success);
}

.adlaire-button--warning {
  background: var(--adlaire-color-warning);
  color: var(--adlaire-color-text-primary);
}

.adlaire-button--error {
  background: var(--adlaire-color-error);
}

/* ========================================
   STYLE VARIANTS
   ======================================== */

/* Outline Button */
.adlaire-button--outline {
  background: transparent;
  color: var(--adlaire-color-brand-primary);
  border-color: currentColor;
}

.adlaire-button--outline:hover:not(:disabled) {
  background: var(--adlaire-color-brand-primary);
  color: var(--adlaire-color-text-inverse);
}

/* Ghost Button */
.adlaire-button--ghost {
  background: transparent;
  color: var(--adlaire-color-brand-primary);
  border-color: transparent;
}

.adlaire-button--ghost:hover:not(:disabled) {
  background: var(--adlaire-color-brand-primary-light);
}

/* ========================================
   STATE MODIFIERS
   ======================================== */

.adlaire-button.is-loading {
  position: relative;
  color: transparent;
  pointer-events: none;
}

.adlaire-button.is-loading::after {
  content: "";
  position: absolute;
  width: 1em;
  height: 1em;
  border: 2px solid currentColor;
  border-right-color: transparent;
  border-radius: 50%;
  animation: adlaire-spin 0.6s linear infinite;
}

@keyframes adlaire-spin {
  to { transform: rotate(360deg); }
}

/* Full Width */
.adlaire-button--block {
  width: 100%;
}

/* Icon Button */
.adlaire-button--icon-only {
  padding: var(--adlaire-space-sm);
  aspect-ratio: 1;
}
```

#### HTML使用例

```html
<!-- Primary Button -->
<button class="adlaire-button">
  Click Me
</button>

<!-- Button with Icon -->
<button class="adlaire-button adlaire-button--large">
  <svg class="adlaire-button__icon">...</svg>
  <span>Download</span>
</button>

<!-- Loading State -->
<button class="adlaire-button adlaire-button--success is-loading">
  Saving...
</button>

<!-- Outline Button -->
<button class="adlaire-button adlaire-button--outline adlaire-button--small">
  Cancel
</button>

<!-- Ghost Button -->
<a href="#" class="adlaire-button adlaire-button--ghost">
  Learn More
</a>
```

---

## 4. アクセシビリティ仕様

### 4.1 カラーコントラスト基準

**WCAG 2.1 AAA準拠**:
- 通常テキスト: 7:1以上
- 大きいテキスト: 4.5:1以上
- UIコンポーネント: 3:1以上

### 4.2 フォーカス管理

```css
/* グローバルフォーカススタイル */
:focus-visible {
  outline: 3px solid var(--adlaire-color-brand-primary);
  outline-offset: 2px;
}

/* キーボードナビゲーション強化 */
.adlaire-button:focus-visible,
.adlaire-input:focus-visible,
.adlaire-link:focus-visible {
  box-shadow: 0 0 0 4px rgba(33, 150, 243, 0.2);
}
```

### 4.3 スクリーンリーダー対応

```css
/* Visually Hidden（スクリーンリーダーのみ） */
.adlaire-sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

/* Focus時に表示 */
.adlaire-sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  overflow: visible;
  clip: auto;
  white-space: normal;
}
```

---

## 5. パフォーマンス目標

### 5.1 ファイルサイズ目標

| Bundle | Target Size (gzipped) | Status |
|--------|----------------------|--------|
| Core | < 8KB | 🎯 Critical |
| Core + Components | < 20KB | 🎯 Target |
| Full Bundle | < 25KB | ⚠️ Maximum |
| Individual Component | < 2KB | 🎯 Target |

### 5.2 読み込みパフォーマンス

- Critical CSS の inline化対応
- 非同期読み込み対応
- HTTP/2 Server Push対応

```html
<!-- Critical CSS Inline -->
<style>
  /* Core tokens and critical components */
</style>

<!-- 非同期読み込み -->
<link rel="preload" href="adlaire-architect.css" as="style">
<link rel="stylesheet" href="adlaire-architect.css" media="print" onload="this.media='all'">
```

---

## 6. ブラウザサポート

### 6.1 サポートブラウザ

**Tier 1 (Full Support)**:
- Chrome/Edge: Latest 2 versions
- Firefox: Latest 2 versions
- Safari: Latest 2 versions

**Tier 2 (Graceful Degradation)**:
- Chrome/Edge: Latest 5 versions
- Firefox: Latest 5 versions
- Safari: Latest 3 versions

**Not Supported**:
- IE11 and below
- Opera Mini

### 6.2 Progressive Enhancement

```css
/* Container Queries with fallback */
.adlaire-card {
  /* Fallback: Mobile-first layout */
  display: flex;
  flex-direction: column;
}

/* Modern browsers with Container Query support */
@supports (container-type: inline-size) {
  .adlaire-card-container {
    container-type: inline-size;
  }
  
  @container (min-width: 480px) {
    .adlaire-card {
      flex-direction: row;
    }
  }
}
```

---

## 7. ライセンス選定

### 7.1 推奨ライセンス: **MIT License**

**理由**:
- ✅ 最も広く使われているオープンソースライセンス
- ✅ 商用利用可能
- ✅ 改変・再配布自由
- ✅ 企業での採用ハードルが低い
- ✅ 他のCSSフレームワークと同様

**代替案**:
- Apache 2.0: より詳細な特許条項（大規模企業向け）
- BSD 3-Clause: MIT類似、商標保護強化

---

## 8. 開発ロードマップ（詳細版）

### Phase 1: 基盤構築（Week 1-2）
- [x] 仕様策定完了
- [ ] Adlaireブランドカラー確定
- [ ] デザイントークン実装
- [ ] リセットCSS作成
- [ ] @layer構造実装

### Phase 2: コアコンポーネント（Week 3-5）
- [ ] Container Query システム
- [ ] Grid & Flexbox レイアウト
- [ ] Button コンポーネント
- [ ] Form コンポーネント
- [ ] Card コンポーネント
- [ ] Typography システム

### Phase 3: 拡張コンポーネント（Week 6-8）
- [ ] Navigation コンポーネント
- [ ] Modal コンポーネント
- [ ] Alert/Toast コンポーネント
- [ ] Tabs/Accordion
- [ ] Table コンポーネント
- [ ] ユーティリティクラス完成

### Phase 4: テーマ&最適化（Week 9-10）
- [ ] ダークモードテーマ
- [ ] 高コントラストテーマ
- [ ] パフォーマンス最適化
- [ ] アクセシビリティ監査
- [ ] ブラウザテスト

### Phase 5: ドキュメント&公開（Week 11-12）
- [ ] 公式ドキュメントサイト
- [ ] コンポーネントデモ
- [ ] Getting Started ガイド
- [ ] API リファレンス
- [ ] GitHubリポジトリ公開
- [ ] npm パッケージ公開

---

## 9. 次のアクション

### 即座に必要な情報

1. **Adlaire Groupブランドカラー**
   - プライマリカラー（HEX値）
   - セカンダリカラー
   - アクセントカラー
   - ニュートラルカラー
   - 既存のカラーパレット

2. **ライセンス承認**
   - MIT License で進めてよいか確認
   - 法務部門の承認が必要か

3. **優先コンポーネント**
   - 最初に実装すべきコンポーネントの優先順位

### プロトタイプ開発開始の準備完了

この仕様書に基づき、すぐに実装を開始できます。

---

**承認者**: _______________  
**承認日**: _______________
