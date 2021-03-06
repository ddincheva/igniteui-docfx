﻿---
title: グリッドの並べ替え
_description: Ignite UI for Angular Data Grid コントロールは、タッチ レスポンシブなデータ グリッドです。階層およびリスト ビューなどの機能があります。
_keywords: Ignite UI for Angular, UI コントロール, Angular ウィジェット, web ウィジェット, UI ウィジェット, Angular, ネイティブ Angular コンポーネント スィート, ネイティブ Angular コントロール, ネイティブ Angular コンポーネント ライブラリ, Angular Data Grid コンポーネント, Angular Data Grid コントロール, Angular Grid コンポーネント, Angular Grid コントロール, Angular 高いパフォーマンス Grid, 並べ替え機能, 並べ替え
_language: ja
---

### グリッドの並べ替え

> [!NOTE]
> 並べ替え操作では、グリッドにバインドされているデータ ソースは変更**されません**。

**並べ替え**も列ごとのレベルで有効化されます。つまり、**igx-grid** に並べ替え可能な列および並べ替え可能ではない列の両方を含むことが可能です。`sortable` 入力によって実行できます。グリッド フィルターと同じように、`sortingIgnoreCase` プロパティを設定すると、大文字と小文字を区別する並べ替えを実行できます。

#### API での並べ替え

グリッドの `sort` メソッドを使用すると、列または複数の列をグリッド API で並べ替えできます。

```typescript
import { SortingDirection } from 'igniteui-angular/main';

// Perform a case insensitive ascending sort on the ProductName column.
this.grid.sort('ProductName', SortingDirection.Asc, true);

// Perform sorting on both the ProductName and Price columns.
this.grid.sort([
    { fieldName: 'ProductName' dir: SortingDirection.Asc, true },
    { fieldName: 'Price', dir: SortingDirection.Desc }
]);
```

フィルター動作と同様に、並べ替え状態をクリアするには `clearSort` メソッドを使用します。

```typescript
// Removes the sorting state from the ProductName column
this.grid.clearSort('ProductName');

// Removes the sorting state from every column in the grid
this.grid.clearSort();
```

#### 初期の並べ替え状態

グリッドの初期の並べ替え状態を設定するには、並べ替え式の配列をグリッドの `sortingExpressions` プロパティに渡します。

```typescript
public ngOnInit() {
    this.grid.sortingExpressions = [
        { fieldName: 'ProductName' dir: SortingDirection.Asc, true },
        { fieldName: 'Price', dir: SortingDirection.Desc }
    ];
}
```

<div class="divider--half"></div>

### 追加のリソース
<div class="divider--half"></div>

* [グリッドの概要](grid.html)
* [仮想化とパフォーマンス](grid_virtualization.html)
* [ページング](grid_paging.html)
* [フィルタリング](grid_filtering.html)
* [集計](grid_summaries.html)
* [列のピン固定](grid_column_pinning.html)

<div class="divider--half"></div>
是非コミュニティに参加してください。

* [Ignite UI for Angular **フォーラム** (英語)](https://www.infragistics.com/community/forums/f/ignite-ui-for-angular)
* [Ignite UI for Angular **GitHub** (英語)](https://github.com/IgniteUI/igniteui-angular)