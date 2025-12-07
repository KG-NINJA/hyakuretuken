# 10秒ジャブ連打チャレンジ - 開発プラン

## プロジェクト概要
ウェブカメラでパンチ（ジャブ）の数を計測する10秒チャレンジゲーム

## 技術スタック
- **フロントエンド**: HTML5 + CSS3 + Vanilla JavaScript
- **ポーズ検出**: MediaPipe Tasks Vision (PoseLandmarker)
- **目標**: シングルHTMLファイルで完結

## 進捗状況 (Progress)

```
██████████ 100%
[■■■■■■■■■■]
```

### 完了タスク ✅
- [x] 基本HTMLレイアウト作成
- [x] CSSスタイリング（ダークテーマ）
- [x] ゲームタイマー実装
- [x] キーボード入力サポート（A/←: 左ジャブ, L/→: 右ジャブ）
- [x] MediaPipe PoseLandmarker統合
- [x] ウェブカメラアクセス
- [x] ポーズ描画（スケルトン表示）
- [x] ジャブ検出アルゴリズム
- [x] スコア管理・ベスト記録
- [x] **エラー修正**: TensorFlow.js CDN問題 → MediaPipe Tasks Visionに移行

### 未完了タスク ⬜
（現在なし - すべて完了）

## Alternative Angle（代替アプローチ）
万が一MediaPipe読み込みに問題が発生した場合:
1. TensorFlow.js + BlazePose（ローカルモデル）
2. キーボード専用モード（カメラなし）
3. OpenCV.js + 色ベーストラッキング

## 行動ログ
- **2024-12-07**: TensorFlow.jsのpose-detection CDN読み込みエラーを修正
  - 原因: `@tensorflow-models/pose-detection`には`dist/pose-detection.min.js`が存在しない
  - 解決: MediaPipe Tasks Vision APIに移行（ES Modulesで安定動作）

## 動作確認方法
```bash
# プロジェクトディレクトリで
python -m http.server 8000
# ブラウザで http://localhost:8000 にアクセス
```
