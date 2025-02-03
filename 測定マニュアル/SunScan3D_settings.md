---
marp: true
---
#### 1. SunScan3D測定後の処理
![alt text](img1.png)
- MLC取得の場合
    1. `Smooth`を選択
    `Spike Removal`で値は`0.2`(step-by-step, Dwell time=1.0で特に有効)
    2. `Smooth`を選択
    `Digital Smoothing Polynomial`
    3. `Normalize`
- 上記以外
    1. `Smooth`を選択
    `Digital Smoothing Polynomial`
    2. `Normalize`

---
#### 2. データ処理のtips
- `step-by-step`で取得した場合
    !`Smooth`の`Spike Removal`で移動に対する測定値の変動を除去することができそう　　
    `step-by-step`の`Dwell time(seconds)`の設定によって異なるので、Dwell timeを変更したときには注意  
    > Dwell timeとSpike Removalの設定は反比例させる(Dwell time=0.25 → Spike Removal=0.5のように)
- `continuous`で取得したデータに対してスパイクノイズを消したい場合
    - `Smooth`の`SG Fitting`を最初に用いて、
    あとは`Digital Smoothing Polynomial`→`Normalize`を実行する

---
#### Reference線量計を用いない場合の測定方法
1. Referenceを`No Detector`にする
2. 使用するビームのエネルギーの測定前に`setup`の`Normalize`を行う
（MEASURE画面のNormalizeからできる）
3. 測定を開始する

**tips**
`Reference`を`(No Detector)`にするには、`一括で測定項目を選択`して`EDIT`に入り`Remove reference`で可能

---
### SFDで測定する場合
前提:AutoSetupが全て終了後に以下を実施する
1. Attachmentホルダを`universal vertical`に交換する
2. `universal vertical`の取付面が水面と同じになっていることを確認する
3. SFDを軽く止めて、ホルダ上面とSFDの測定部分の下端が引っかかるように固定する
4. 水面とSFD上端が一致していることを確認する。実効中心をONにして、`Positionのz=0`にして水面と一致を確認する。
5. 水面と一致しないときは、`ENVIRONMENT`の`Detectors`からSFDの`Offset`を変更する。（2月3日現在、1.50cm設定）