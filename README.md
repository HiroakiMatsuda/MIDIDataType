MIDIDataType
======================
[RT-Middleware][rtm]上でMIDI (Musical Instrument Digital Interface)メッセージを扱うための独自データ型です．

[rtm]:http://www.openrtm.org/openrtm/ja

データ型の構造
------
MIDIDataTypeには3つのデータ型が定義されています．
各データ型に含まれる変数とその意味を説明します．

###ChannelMessage型###
チャンネルメッセージに関する情報を格納します．
各メッセージで使用する変数を以下に示します．

####Plyphonic Key Pressure####

|変数名|格納する情報|
|note_number|ノート番号|
|velocity|ヴェロシティ|

 ・ `short channel` :  
チャンネル番号を格納します．

 ・`short note_number`:  
ノート番号を格納します．
この変数を使用するメッセージは以下のとおりです．

 Note On
 Note Off

 ・`short velocity`:  
Note OnやNote Offに使うをベロシティを格納します．

 ・`short control_number`:  
コントロール・チェンジに使う，コントロール番号を格納します．

 ・`short value` :  
コントロール・チェンジに使う，コントロール番号を格納します

 ・`short number_of_channels`:  
コントロール・チェンジやポリフォニックキープレッシャーに使う，バリューを格納します．

 ・`short tone_number`:  


 ・`short pressure` :  

 ・`long  pitch_bend`:  

###SystemMessage型###
システメッセージに関する情報を格納します．

 ・ `string data` :  
チャンネル番号を格納します．

 ・`short  sequence_number` :

 ・`string text` :

 ・`string copyright_notice` :

 ・`string sequence_name` :

 ・`string instrument_name` :

 ・`string lyrics` :

 ・`string marker` :

 ・`string cue_point` :

 ・`string program_name` :

 ・`string device_name` :

 ・`short midi_channel` :

 ・`short  port` :
 
 ・`long   tempo` :

 ・`long   offset` :

 ・`short  molecule` :

 ・`short  denominator` :

 ・`short  click` :

 ・`short  notes_per_clocks` :

 ・`short  sf` :

 ・`short  mi` :


###MIDIMessage型###

 ・`RTC::Time tm` :
 
・`string event` :

 ・`ChannelMessage ch` :

 ・`SystemMessage sys` :


ライセンス
----------
Copyright &copy; 2014 Hiroaki Matsuda  
Licensed under the [Apache License, Version 2.0][Apache]  
Distributed under the [MIT License][mit].  
Dual licensed under the [MIT license][MIT] and  [Apache License, Version 2.0][Apache].  
 
[Apache]: http://www.apache.org/licenses/LICENSE-2.0
[MIT]: http://www.opensource.org/licenses/mit-license.php