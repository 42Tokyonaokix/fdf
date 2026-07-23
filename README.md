# fdf (Fil de Fer / Wireframe)

42 Common Core の課題。`.fdf` 形式の地形データ（高さマップ）を読み込み、minilibX（X11ベースのグラフィックライブラリ）でワイヤーフレーム3Dモデルとして描画します。

## やっていること

- `.fdf` ファイル（スペース区切りの整数グリッド = 高さマップ）をパースし、2D座標を等角投影（isometric projection）で3D風に変換して描画
- `test_maps/` に42・凹凸地形・グラデーションなど複数のサンプルマップを同梱

## Build & Run

```sh
make
./fdf test_maps/42.fdf
```

## 技術ポイント

- `perth_2Dmap.c` / `perth_3Dmap.c` で座標変換ロジックとレンダリングを分離
- ウィンドウサイズに応じたスケーリング・フィッティング（`perth_fix_size.c`）
- 独自の `get_next_line` ベースのファイルパーサでマップ読み込み時のメモリ管理を実装
