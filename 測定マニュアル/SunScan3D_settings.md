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