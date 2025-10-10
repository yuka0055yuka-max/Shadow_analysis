# Shadow_analysis

**Shadow_analysis** は、画像内の影の方向と位置情報から、撮影された時刻を推定する革新的な PWA（Progressive Web App）です。  
Exif情報がない画像でも、緯度・経度・撮影日を入力し、影の始点・終点をキャンバス上で指定することで、太陽の位置から撮影時刻を逆算します。

---

##  特徴

   **Exif解析対応**：GPS・日時・カメラ情報を自動抽出
   **影マーク機能**：キャンバス上で影の始点・終点を指定
   **太陽位置推定**：SunCalcライブラリを用いて太陽の方位・高度を計算
   **撮影時刻推定**：影の方位と太陽の動きを照合し、最も一致する時刻を推定
   **影なし強制検出**：影がない画像でも、緯度・経度・撮影日から太陽南中時刻を推定
   **PWA対応**：スマホでもインストール可能、オフライン動作対応

---

## 🛠 使用技術

- HTML5 / CSS3 / JavaScript
- [Exif.js](https://github.com/exif-js/exif-js) - 画像のExif情報を抽出
- [SunCalc](https://github.com/mourner/suncalc) - 太陽の位置計算
- Service Worker / manifest.json - PWA構成

---

## 📦 ファイル構成

Shadow_analysis/
├── image-analyzer.html       # メインアプリ
├── manifest.json             # PWA設定
├── sw.js                     # Service Worker
├── icon-192.png              # PWAアイコン（任意）
├── icon-512.png              # PWAアイコン（任意）
└── README.md                 # このファイル

使い方

1. `image-analyzer.html` をブラウザで開く
2. 画像をアップロード（Exif情報があれば自動解析）
3. 緯度・経度・撮影日を入力（Exifがない場合）
4. 「影をマーク」ボタン → キャンバス上で2点を指定
5. 「時刻推定を実行」ボタン → 結果表示
6. 影がない場合は「影なし強制時刻検出」ボタンで南中時刻を推定

---

## 注意事項

- 影の方向が正確に指定されていない場合、誤差が生じる可能性があります
- 影なし推定は簡易的なもので、±1〜2時間程度の誤差が出る場合があります
- 太陽の位置は地球上の位置・季節・時刻により大きく変化します

---

## クレジット

Created by **YUME**  
Special thanks to [Exif.js](https://github.com/exif-js/exif-js) and [SunCalc](https://github.com/mourner/suncalc)

---

## ライセンス

MIT License



