M17 RF Protocol: 要約
========================

M17 とは以下のような無線通信 (RF) プロトコルである:

* 完全にオープンであること: 仕様が公開され、オープンソースコードであり、
  オープンソースハードウェアであり、アルゴリズムも公開されている。
  M17 無線機の製造および他の M17 無線機と相互運用することは誰でも行うこと
  ができ、それに対する支払いは要求されない。
* アマチュア無線用途に最適化されている。
* 理解と実装が容易である。  
* アマチュア無線家がデジタルプロトコルに求める、以下の機能を実現できる。

  * 音声 (例: DMR, D-Star など)
  * データ (例: パケット, D-Star など)
  * テレメトリ (例: APRS など)
  * 拡張性 (将来における機能追加の余地がある)

この目的を果たすため、M17 プロトコルは以下の三つの階層に分かれている。

#. 物理層: 1 や 0 のビット列を RF にエンコードする部分。
   変調方式、シンボルレート、ビットとシンボルの対応などについて。
#. データリンク層: 実際のデータと、パケット化された 1 や 0 のビット列との
   変換を行う部分。
   Packet/Stream モード、ヘッダ、アドレスなどについて。
#. アプリケーション層: 目的を達成する部分。
   音声やデータストリーム、制御パケット、ビーコン等について。

本文書は、これらの階層を説明するために存在する。

.. [TETRA] Dunlop, John; Girma, Demessie; Irvine, James "Digital
           Mobile Communications and the TETRA System" Wiley 1999,
           ISBN: 9780471987925

.. [DMR] ETSI TS 102 361-1 V2.2.1 (2013-02): "Electromagnetic
         compatibility and Radio spectrum Matters (ERM); Digital
         Mobile Radio (DMR) Systems; Part 1: DMR Air Interface (AI)
         protocol"
         https://www.etsi.org/deliver/etsi_ts/102300_102399/10236101/02.02.01_60/ts_10236101v020201p.pdf
