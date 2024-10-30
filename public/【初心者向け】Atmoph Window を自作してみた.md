---
title: 【初心者向け】Atmoph Window を自作してみた
tags:
  - Python
  - 電子工作
  - RaspberryPi
  - 初心者
  - DIY
private: false
updated_at: '2024-10-30T08:53:14+09:00'
id: 480a324234963d5fda5b
organization_url_name: null
slide: false
ignorePublish: false
---
# ✍️ はじめに
**Raspberry Pi**を活用して、自作の「Atmoph Window」風のデバイスを作成しました。ソフトは**python**で動いております(初心者にもおすすめ🔰)。  

<div style="display: flex; gap: 10px;">
    <img src="https://github.com/Rockreeee/image-display-app/raw/main/asset/9.jpg" alt="代替テキスト" width="270" height="400" />
    <img src="https://github.com/Rockreeee/image-display-app/raw/main/asset/8.jpg" alt="代替テキスト" width="270" height="400" />
    <img src="https://github.com/Rockreeee/image-display-app/raw/main/asset/11.jpg" alt="代替テキスト" width="270" height="400" />
</div>

Atmoph Windowを自作した理由:
- 自作したほうが**安い**から！！【半額くらい】
- **カスタマイズ**したいから
  - 今後Raspberry Piをファイルサーバーとしても機能させたい

[**プログラム**](https://github.com/Rockreeee/image-display-app)も公開していますので、是非真似してみてください🎶

# ✅ 実際に完成したもの

<img src="https://github.com/Rockreeee/image-display-app/raw/main/asset/10.jpg" alt="代替テキスト" width="500" height="760" />

正面から見た様子



<img src="https://github.com/Rockreeee/image-display-app/raw/main/asset/12.jpg" alt="代替テキスト" width="500" height="760" />

裏側はこんな感じ



# 👍 活用方法

<img src="https://github.com/Rockreeee/image-display-app/raw/main/asset/2.png" alt="代替テキスト" width="200" height="400" />
<img src="https://github.com/Rockreeee/image-display-app/raw/main/asset/3.png" alt="代替テキスト" width="200" height="400" />

時間日付確認  
天気予報確認  
ランダム画像表示

<img src="https://github.com/Rockreeee/image-display-app/raw/main/asset/1.jpg" alt="代替テキスト" width="400" height="400" />

アート作品や写真を飾る

<img src="https://github.com/Rockreeee/image-display-app/raw/main/asset/4.png" alt="代替テキスト" width="400" height="240" />

暗記

# 🛠️ 用意したものと費用
- [**Raspberry Pi4 ModelB 4GB**](https://www.amazon.co.jp/dp/B081YD3VL5?ref=ppx_pop_mob_ap_share)  
→ 10000円
- [**Raspberry Pi ケース**](https://www.amazon.co.jp/dp/B07VC3RWYZ?ref=ppx_pop_mob_ap_share)  
→ 2000円
- [**microSD 128GB**](https://www.amazon.co.jp/dp/B09378JC6B?ref=ppx_pop_mob_ap_share)  
→ 2000円
- [**ディスプレイ**](https://www.amazon.co.jp/dp/B08PTSFF4B?ref=ppx_pop_mob_ap_share&th=1)(ベゼルが薄い、IPSパネルがおすすめ)  
→ 12000円
- **木材**:  
→ 2000円
- [**ミニスピーカー**](https://www.amazon.co.jp/dp/B075M7FHM1?ref=ppx_pop_mob_ap_share&th=1)  
→ 1400円
- [**電源タップ**](https://www.amazon.co.jp/dp/B005FDE8EQ?ref=ppx_pop_mob_ap_share)   
→ 800円
- [**HDMI L字 コネクタ**](https://www.amazon.co.jp/dp/B00Y7UT6EK?ref=ppx_pop_mob_ap_share)  
→ 700円
- [**Micro HDMI to HDMI 変換 ケーブル**](https://www.amazon.co.jp/dp/B0873ZCH3R?ref=ppx_pop_mob_ap_share&th=1)  
→ 1000円
- [**マイクロUSBメモリー 32GB**](https://www.amazon.co.jp/dp/B00KBP29B2?ref=ppx_pop_mob_ap_share&th=1)  
→ 1500円
- [**Bluetooth折りたたみ式ワイヤレスキーボード**](https://www.amazon.co.jp/dp/B0CLMZRWWY?ref=ppx_pop_mob_ap_share)  
→ 3000円

<span style="font-size:20px;">**合計: 36400円**</span>(結構高かった)

# 🔨 作り方
作り方はいたって単純
1. ディスプレイの大きさに合わせて木をカットする
2. 釘やボンドを使って枠を組み合わせる
3. Raspberry Piなどをつなぐ
4. Raspberry Piの環境構築

プログラムの動かし方は[**こちら**](https://github.com/Rockreeee/image-display-app)に書いております。

:::note warn
警告
動作は自己責任でお願いします。
:::


# 📋 特徴
自作Atmoph Windowの主な機能
- **風景画像のスライドショー**: ランダムで景色やアートの画像を表示
- **日付・時計の表示**: 日付・時間表示
- **天気の表示**: 指定の場所の天気予報表示（tenki.jp）
- **音楽再生**: 優雅な音楽の目覚まし
- **明るさの自動調整**: 朝昼晩に応じて、画面の明るさを自動的に調整
- **学習モード**: 英単語やフレーズを表示して、語彙力を高められる学習機能も搭載！！


# 👀 動作の様子
<img src="https://github.com/Rockreeee/image-display-app/raw/main/asset/7.png" width="200" height="230" /> 

２つのモードがあります
- 🖼 画像表示モード
- 🧠 勉強モード

## 🖼 画像表示モード
<img src="https://github.com/Rockreeee/image-display-app/raw/main/asset/5.png" width="400" height="250" /> 

### - 設定
- Image Path: 画像フォルダのパス
- Image Display Interval: 画像が切り替わるまでの時間
- Image With Margin: 画像の周りに余白を表示するか否か
- Automatic Brightness Adjustment: 明るさを自動調整するか否か
- Show Clock: 時間を表示するか否か
- Show Weather: 天気を表示するか否か
- Sound Path: 音楽フォルダのパス
- Sound Off: 音楽オフ
- Sound On: 音楽オン
- Morning Sound Only: 朝の10分間音楽を流す

### - キーバインド
- \<Escape key> or \<q key>: 終了する
- \<b key>: 周りの枠の明るさ調整
- \<i key>: 画像の明るさ調整
- \<f key>: ウィンドウ大きさ変更
- \<h key>: カーソル表示切り替え
- \<v key>: 音量の調整
- \<m key>: ミュートの切り替え
- \<Space key>: 次の画像に移動する

## 🧠 勉強モード
<img src="https://github.com/Rockreeee/image-display-app/raw/main/asset/6.png" width="400" height="150" /> 

### - 設定
- Study Directory: 問題が保存されているファイルのパス
- Answer Interval: 答えが出るまでの時間
- Change Interval: 問題が変わるまでの時間

### - キーバインド
- \<Escape key> or \<q key>: 終了する
- \<Space key>: 暗記完了（ループから削除されて、もう表示されない）
- \<b key>: 明るさ調整

# ✅ まとめ
- 今回は、Raspberry PiとPythonを活用して自作の「Atmoph Window」を手軽に再現してみました！
- 風景画像のスライドショー、天気・時間の表示、自動明るさ調整機能など、多様な機能を備え、さらに勉強モードを利用して単語暗記もサポートしてます。
- 自宅で「デジタル窓」として雰囲気を演出するだけでなく、学習にも役立つ多機能デバイスとなりました。
- お手頃価格で作成できるため、趣味や学習に最適でした〜！
