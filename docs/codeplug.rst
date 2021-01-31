コードプラグの推奨仕様
**********************
 
はじめに
########

コードプラグは拡張子が *.m17* となる、テキストファイルである。以下の情報が含まれている:

 * チャネルのバンク
 * チャネルの周波数
 * 宛先 ID
 * モード
 * ペイロード種別
 * 暗号化

コードプラグは可読性があり、一般的なテキストエディタで編集可能なものとする。

コードプラグファイルの構造
##########################

コードプラグの記述には YAML を使用する。

キーワード
----------

**codeplug:**
  **author:**
    文字列 - コードプラグの作者、最大 16 文字
  **version:**
    日付と時刻 YYYY-MM-DDTHH:MM:SS 形式

**bank:**
  **name:**
    文字列 - チャネルバンクの名称、最大 16 文字

**channel:** 
  **name:**
    文字列 - チャネルの名称、最大 16 文字
  **descr:**
    文字列 - チャネルの説明、最大 16 文字
  **freq_rx:**
    整数 - チャネルの受信周波数 (Hz)
  **freq_tx:**
    整数 - チャネルの送信周波数 (Hz)
  **mode:**
    整数 - モード (0〜3) 0 - アナログ, 1 - デジタル音声, 2 - デジタルデータ, 3 - デジタル音声とデータ
  **encr:**
    整数 - 暗号化の有無および種別 (0〜2) 0 暗号化なし, 1 - AES256, 2 - scrambler など (詳しくは M17_spec を参照)
  **nonce:**
    文字列 - 14 桁の 16 進数 (ただし先頭に 0x はつけない) 暗号化におけるノンス値もしくは scrambler での LFSR 初期値
  **gps:**
    ブール値 - モードがデジタルデータでかつこの値が true の場合は、GPS データがペイロードとなる

コードプラグの例
################

::

  codeplug:
    author: SP5WWP
    version: 2020-28-09T13:20:49
    - bank:
      name: M17
      - channel:
        name: M17_DMO
        descr: 
        freq_rx: 439575000
        freq_tx: 439575000
        mode: 2
        encr: 0
        nonce: 0
        gps: false
      - channel:
        name: M17_DMO_2
        descr: 
        freq_rx: 439975000
        freq_tx: 439975000
        mode: 2
        encr: 0
        nonce: 0
        gps: false
    - bank:
      name: Repeaters
      - channel:
        name: SR5MS
        descr: 
        freq_rx: 439425000
        freq_tx: 431825000
        mode: 2
        encr: 0
        nonce: 0
        gps: false
  #codeplug end
