# mpsy

マップとポイントを操作するやつ

XOPSのマップとポイントに対して拡大や回転などの処理を行うプログラムです。

# 使い方

## オプション一覧

|      オプション       |                     意味                     |               引数               |
| :-------------------: | :------------------------------------------: | :------------------------------: |
| -bi, --bd1FilepathIn  | 入力するBD1ファイルのファイルパス (必須引数) |           ファイルパス           |
| -pi, --pd1FilepathIn  | 入力するPD1ファイルのファイルパス (必須引数) |           ファイルパス           |
| -bo, --bd1FilepathOut | 出力するBD1ファイルのファイルパス (必須引数) |           ファイルパス           |
| -po, --pd1FilepathOut | 出力するPD1ファイルのファイルパス (必須引数) |           ファイルパス           |
|   -t, --translation   |               移動を行います。               |         移動量 [x, y, z]         |
|      -s, --scale      |            拡大・縮小を行います。            |         拡大率 [x, y, z]         |
|      -rx, --rotX      |          X軸回りの回転を行います。           |             角度(°)              |
|      -ry, --rotY      |          Y軸回りの回転を行います。           |             角度(°)              |
|      -rz, --rotZ      |         Z軸回りの回転角を行います。          |             角度(°)              |
|       -r, --rot       |         任意軸回りの回転を行います。         | 軸および角度 [x, y, z, 角度 (°)] |
|     -z, --invertZ     |              Z軸を反転します。               |                -                 |
|      -h, --help       |             ヘルプを表示します。             |                -                 |
|     -v, --version     |         バージョン情報を表示します。         |                -                 |

## 使用例

### マップとポイントの操作

```
mpsy.exe \
	-bi map.pd1 \
	-pi points.pd1 \
	-bo map2.bd1 \
	-po points2.pd1 \
	-t 50.0 50.0 50.0 \
	-s 2.0 2.0 2.0 \
	-rx 45 \
	-ry 45 \
	-rz 45 \
	-r 1.0 1.0 1.0 45 \
	-z
```

必須引数以外は省略することもできます。

### ヘルプの表示

```
mpsy.exe -h
```

## 使用上の注意

マップおよびポイントに対する操作は、
**移動**→**拡大・縮小**→**X軸回りの回転**→**Y軸回りの回転**→**Z軸回りの回転**→**任意軸回りの回転**→Z**軸反転**
という順番で行われます。
このため、移動や回転を同時に行うと、想定通りの結果が得られない場合があります。



このプログラムには[JXM (Java XOPSManipulator)](https://github.com/Dabasan/jxm)が使用されています。
JavaがインストールされていないWindowsマシンでも動作するように、Windows用のJREが同封されています。

リリースに含まれる`mpsy.exe`は内部で`mpsy.jar`を実行しています。

Windows以外の環境を使用している方は、`mpsy.jar`を直接実行してください。
この場合には、Java 11以上が必要になります。

# プログラム情報

## 作者

駄場

## バージョン

0.0.1

## ライセンス

JREのライセンスについては、jre/legalを参照してください。
その他のファイルはMITライセンスの下に公開されています。

