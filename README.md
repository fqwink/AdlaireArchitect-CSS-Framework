# Adlaire Architect CSS Framework

**Version**: 0.3.0 (Development)  
**Status**: Form Components Complete ✅  
**License**: Apache License 2.0

---

## Overview

Adlaire-Architect-CSS-Framework は、Adlaire Group DX事業セグメントグループが開発・保守・管理する、モダンで軽量なCSSフレームワークです。Adlaire GroupのWebサイト、システム開発、プロジェクト関連で使用され、オープンソースとして公開されます。

**🎉 NEW**: Adlaire Group公式ブランドカラーが完全統合されました！

### Key Features

- 🎨 **Adlaire Brand Colors** - 公式ブランドカラー完全統合（Emerald Green, Blue Sky等）
- 🚀 **Pure CSS3** - プリプロセッサ不要、CSS3のみで構成
- ⚡ **Lightweight** - コアは5KB以下、モジュラー設計
- 📦 **Container Queries First** - 最新のレスポンシブデザイン技術
- 🎯 **BEM Methodology** - 明確な命名規則とコンポーネント設計
- ♿ **Accessibility** - WCAG 2.1準拠
- 🎭 **Theme Support** - CSS Variablesによる柔軟なテーマシステム
- 🏢 **Enterprise Ready** - Adlaire Group専用デザインシステム統合

---

## Brand Colors

Adlaire Groupの公式ブランドカラーがフレームワークに統合されました：

| Color | Name | HEX | Usage |
|-------|------|-----|-------|
| 🟢 | **Emerald Green** | `#00a968` | Primary |
| 🔵 | **Blue Sky** | `#3498db` | Secondary |
| 💠 | **Summer Sky** | `#40AAEF` | Accent |
| 🌿 | **Solitude** | `#58BE89` | Success |
| ⬜ | **White Rat** | `#ecf0f1` | Light BG |
| ⬜ | **Silver Tree** | `#ECEEF1` | Subtle BG |

詳細は [Brand Color Guide](./docs/brand-colors.md) を参照してください。

---

## Project Status

### Current Phase: Core Implementation + Brand Integration ✅

このプロジェクトは、Phase 1完了、ブランドカラー統合完了の状態です。

#### Completed
- ✅ 2026年のCSSフレームワーク動向調査
- ✅ 技術スタック選定（Pure CSS3）
- ✅ プロジェクト構造の構築
- ✅ デザインシステム仕様策定
- ✅ **Adlaire Groupブランドカラー完全統合** 🎉
- ✅ コアCSS実装（Reset, Layers, Tokens）
- ✅ Container System実装
- ✅ Button Component完全実装
- ✅ デモページ作成
- ✅ Brand Color Guide作成

#### In Progress
- 🔄 追加コンポーネント開発準備

#### Upcoming
- ⏳ 命名規則の確定
- ⏳ ブラウザサポートポリシー決定
- ⏳ ライセンス選定
- ⏳ 詳細設計ドキュメント作成

---

## Architecture (Proposed)

### Hybrid Approach

Adlaire-Architect-CSS-Frameworkは、以下の3層構造を採用します：

1. **Token Layer** - デザイントークン（色、間隔、タイポグラフィ）
2. **Component Layer** - セマンティックなBEMコンポーネント
3. **Utility Layer** - 頻繁に使用するユーティリティクラス

### Technology Stack

- **CSS3** - モダンな機能を最大活用
  - CSS Custom Properties (Variables)
  - Container Queries
  - CSS Grid & Flexbox
  - CSS Subgrid
  - CSS Layers (`@layer`)
- **Naming Convention** - BEM (Block Element Modifier)
- **Build** - Buildless (optional bundling for optimization)

### Browser Support

**Modern Browsers Only**:
- Chrome/Edge: Latest 2 versions
- Firefox: Latest 2 versions
- Safari: Latest 2 versions
- ❌ IE11 not supported

---

## Planned Directory Structure

```
adlaire-architect-css/
├── src/
│   ├── base/              # Reset & base styles
│   │   ├── reset.css
│   │   └── typography.css
│   ├── tokens/            # Design tokens
│   │   ├── colors.css
│   │   ├── spacing.css
│   │   ├── shadows.css
│   │   └── typography-tokens.css
│   ├── layouts/           # Layout systems
│   │   ├── grid.css
│   │   ├── container.css
│   │   └── flexbox-utilities.css
│   ├── components/        # UI components
│   │   ├── buttons.css
│   │   ├── forms.css
│   │   ├── cards.css
│   │   ├── navigation.css
│   │   └── alerts.css
│   ├── utilities/         # Utility classes
│   │   ├── spacing.css
│   │   ├── colors.css
│   │   ├── typography.css
│   │   └── display.css
│   └── themes/            # Theme variations
│       ├── default.css
│       ├── dark.css
│       └── high-contrast.css
├── dist/                  # Compiled/optimized files
├── docs/                  # Documentation
├── examples/              # Usage examples
├── research/              # Research & planning documents
└── tests/                 # Test files
```

---

## Development Roadmap

### Phase 1: Specification (2-3 weeks)
- [ ] Design system specification document
- [ ] Adlaire Group brand color system definition
- [ ] Component inventory
- [ ] Naming convention finalization
- [ ] Browser support policy
- [ ] License selection

### Phase 2: Core Development (4-6 weeks)
- [ ] Design token implementation
- [ ] Grid system
- [ ] Typography system
- [ ] Base components
- [ ] Utility classes

### Phase 3: Extension & Testing (3-4 weeks)
- [ ] Additional components
- [ ] Theme system
- [ ] Accessibility audit
- [ ] Browser testing
- [ ] Performance optimization

### Phase 4: Documentation & Release (2-3 weeks)
- [ ] Official documentation
- [ ] Demo site
- [ ] GitHub repository public release
- [ ] npm package publication
- [ ] Community building

---

## Research Documents

プロジェクトの技術選定と方向性に関する詳細な調査資料は、`/research` ディレクトリを参照してください：

- [CSSフレームワーク動向調査レポート 2026](./research/css-framework-trends-2026.md)

---

## Contributing

このプロジェクトは現在、Adlaire Group内部で仕様策定中です。将来的にオープンソースとして公開される予定です。

---

## License

TBD - ライセンスは仕様策定フェーズで決定されます。

候補：
- MIT License (推奨)
- Apache 2.0
- BSD 3-Clause

---

## Team

**Developer**: Adlaire Group DX事業セグメントグループ  
**Maintainer**: TBD

---

## Quick Start

### Installation (Coming Soon)

```bash
# npm (planned)
npm install adlaire-architect-css

# CDN (planned)
<link rel="stylesheet" href="https://cdn.adlaire.com/architect-css/0.1.0/adlaire-architect.min.css">
```

### Current Development Usage

```bash
# Clone repository
git clone https://github.com/adlaire-group/adlaire-architect-css.git
cd adlaire-architect-css

# View demo
# Open examples/demo.html in your browser
# Or run a local server:
python3 -m http.server 8000
# Then visit: http://localhost:8000/examples/demo.html
```

### Basic Usage Example

```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <link rel="stylesheet" href="path/to/adlaire-architect.css">
</head>
<body>
  <div class="adlaire-container-3xl">
    <button class="adlaire-button">Primary Button</button>
    <button class="adlaire-button adlaire-button--outline">Outline Button</button>
  </div>
</body>
</html>
```

---

## Documentation

- [ブランドカラーガイド (Brand Colors)](./docs/brand-colors.md) - 🎉 NEW! Adlaire公式カラーパレット
- [仕様書 (Specification)](./docs/specification.md) - 詳細な技術仕様とアーキテクチャ
- [調査レポート (Research)](./research/css-framework-trends-2026.md) - 2026年のCSSフレームワーク動向
- [CHANGELOG](./CHANGELOG.md) - 変更履歴

---

## Next Steps

1. ✅ ~~**ブランドカラー体系の定義**~~ - **完了！**
2. **Form Components実装** - Input, Textarea, Select等
3. **Card Component実装** - Container Query対応
4. **Typography System実装**
5. **ライセンス選定** - MIT License推奨

---

**Last Updated**: 2026-02-13
