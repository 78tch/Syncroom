# Syncroom の調整方法
本稿は、Mac 版を前提としていますが、Windows版でも読み替え可能と思います。インストールやオーディオインターフェイスなどの設定は終わっている前提です。  

## 1.「環境チェッカー」で自分の環境をチェックしよう
## 2.「設定」画面で自分の機材に合った設定にしよう
## 3.標準的な設定でうまく動くかチェックしよう
## 4.4人の接続相手との接続品質は

### 0.基本的な流れ
1. 「環境チェッカー」で、「回線タイプ」のタイプコードが「AU」または「AU6」であるか確認。
2. 「設定」で、「オーディオデバイス」がMacなら「Core Audio」、Windowsなら「ASIO」であるか確認。
3. 「設定」の「オーディオデバイス」で、「入力デバイス」と「出力デバイス」が同一機種であるか確認。
4. 「設定」の「バッファサイズ」が64または128であるか確認。安定していて、遅延をさらに小さくしたい場合は数値を小さくし、プツプツと途切れる場合は大きくする。
5. 「設定」の「入力のモニタリング」は『モニタリングする（遅延あり）』とし、「オーディオデバイス」のダイレクトモニタリングは切る。なるべくヘッドホンで聞く。最大で20ms遅れて聞こえるが、それを織り込んで演奏する。
6. 「設定」の「基本音質設定」は、「標準」か、できれば「高音質」にする。
7. それでも通信が乱れる場合は、「その他の設定」の「オーディオデータ補間処理を有効にする」をオフにすると改善する場合もある。
8. 「メイン画面」で、「オーディオプレイヤー」や「メトロノーム」を鳴らすと、相手への送信の遅延時間をみて、その分先回り送信してくれる。この機能により、遅延なく同時に音を聞いている状態になるため、タイミングを合わせやすくなる。
9. ひとつのROOMに最大で5人まで入れるが、接続は1対1であるため、通信品質は、接続相手ごとに異なってくる。ある相手との接続が不調で、他の相手との接続が好調である場合の原因は、自分とある相手との問題であり、他の相手には関係がない。


### 1.「環境チェッカー」の見方
「メイン画面」の左下にある「設定」ボタンで「設定画面」を開き、左下にある「環境チェッカー」ボタンを押すと、以下の６項目を判定してくれます。
1. 「IPv6対応状況」：対応しているほうが望ましいようですが、対応するには自宅のインターネット回線の契約変更が必要になります。
2. 「回線タイプ」：タイプコードが「AU」または「AU6」となっていればひとまず安心。「A」は回線情報でA・B・Cの3段階あり、AやBなら問題なく、Cだとつらいかも（改善には自宅のインターネット回線の見直しが必要）。「U」はUPnPによるポートマッピングが使用できることを示しており、IPv4での接続性が向上します。「6」は IPv6に対応していることを示していますが、接続相手もIPv6に対応している場合のみ、その相手とはIPv6で接続されます。
3. 「回線状況」：いま時点の通信安定性が分かります。ネットの混雑状況によるものなので、設定で改善できる部分ではありません。
4. 「オーディオデバイス」：Macは「Core Audio」一択、Windowsは「ASIO」になってないと厳しいです。その下の、入力デバイスと出力デバイスは、同一機器を指定しないと、トラブルのもとになります。バッファサイズは、自動で最適値が設定されていると思いますが、「問題ないがより高品質にしたい場合⇒より小さい値にしてみる」、「途切れたりうまつつながらない場合⇒より大きい値にしてみる」なお、「VSTモード」はDAWと合わせて使う場合のモードで、手動で選ぶ必要はありません。
5. 「CPU性能」：問題があると考えられる場合、画面上に説明文が表示されます。

### 2.「設定」の見方
1. 「オーディオデバイス」：Macは「Core Audio」、Windowsは「ASIO」になっていることを確認。「規定の入力」と「規定の出力」は同一機器にすること。「サンプリング周波数」は44.1kHzまたは48kHzしか選べないので、設定できる機器は合わせること。（例えば48kHzに統一する。）
2. 「バッファサイズ」：接続に問題がなければ、値を「64～128」など小さくすればより遅延が小さくなるが、接続に問題がある（音がプツプツと途切れる）場合は、値を少しずつ大きくしてみると、改善する。
3. 「入力のモニタリング」：3種類から選ぶ。『モニタリングしない』、『モニタリングする（遅延あり）』、『モニタリングする（遅延なし）』だが、推奨は『モニタリングする（遅延あり）』で、「（遅延あり）」の意味は、「入力音のモニターをあえて遅延させることで、ネットワーク遅延がある相手の音とのタイミングのずれを小さくする」ということなので、オーディオデバイスの「ダイレクトモニター」などはオフにしておかないと、音がぼやけてしまう。また、モニター音が遅延することを見越して、先読みして、少し早いタイミングで演奏するように、調節が必要になる。また、遅延はスピーカーよりヘッドホンのほうが小さいので、ヘッドフォンが推奨。
4. 「入力チャンネル」：特に設定は不要か。
5. 「拡張入力チャンネル」：特に設定は不要か。
6. 「出力チャンネル」：特に設定は不要か。
7. 「MIDIコントロール設定」：MIDI信号でアプリを制御できる。
8. 「基本音質設定」：「標準」で試して、問題なければ「高音質」も試す。双方が「高音質」に設定している場合だけ「高音質」で接続される。相手と設定が違う場合、品質の低いほうの設定が選択される。音質設定は、遅延時間には直接的に影響しないが、音の乱れ（途切れやノイズ）には影響する。（引用）「SYNCROOMにおいては、「音質設定」は通信速度にあまり影響しません。そのため、より快適にセッションするためにも、通常はなるべく「高音質」に設定して使用してみてください。通信帯域が不足して繋がらない場合は、音質設定を下げてみてください。」とのこと。
9. 「アラートオン設定」：エラー時や新メンバー入室時に、アラート音が鳴る。
10. 「その他の設定」：基本は初期値のまま。音声が乱れる場合には、試しに「オーディオデータ補間処理を有効にする」をオフにすると改善する場合もある。