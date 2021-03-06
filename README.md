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

####Note Off####

|変数名|格納する情報|  
|---|---|  
|channel|チャンネル番号|  
|note_number|ノート番号|  
|velocity|ベロシティ|

####Note On####

|変数名|格納する情報|  
|---|---|  
|channel|チャンネル番号|  
|note_number|ノート番号|  
|velocity|ベロシティ|

####Polyphonic Key Pressure####

|変数名|格納する情報|  
|---|---|  
|channel|チャンネル番号|  
|note_number|ノート番号|  
|pressure|プレッシャー|  

####Control Change####

|変数名|格納する情報|  
|---|---|  
|channel|チャンネル番号|  
|control_number|コントロール番号|  
|value|バリュー|  
|number_of_channels|モード4で使用するチャンネル番号|  

####Program Change####

|変数名|格納する情報|  
|---|---|  
|channel|チャンネル番号|  
|tone_number|音色番号|  

####Channel Pressure####

|変数名|格納する情報|  
|---|---|  
|channel|チャンネル番号|  
|pressure|プレッシャー|  

####Pitch Bend####

|変数名|格納する情報|  
|---|---|  
|channel|チャンネル番号|  
|pitch_bend|ピッチベンド|  

###SystemMessage型###
システメッセージに関する情報を格納します．  
各メッセージで使用する変数を以下に示します．  

####SysEx F0####

|変数名|格納する情報|  
|---|---|  
|data|エクスクルーシブメッセージ|  

####SysEx F7####

|変数名|格納する情報|  
|---|---|  
|data|エクスクルーシブメッセージ|  

####Sequence Number####

|変数名|格納する情報|  
|---|---|  
|sequence_number|シーケンス番号|  

####Text####

|変数名|格納する情報|  
|---|---|  
|text|コメントなどのテキスト|  

####Copyright Notice####

|変数名|格納する情報|  
|---|---|  
|copyright_notice|著作権表示|  

####Sequence Name####

|変数名|格納する情報|  
|---|---|  
|sequence_name|シーケンス名，トラック名|  

####Instrument Names####

|変数名|格納する情報|  
|---|---|  
|instrument_name|楽器名|  

####Lyrics####

|変数名|格納する情報|  
|---|---|  
|lyrics|歌詞|  

####Marker####

|変数名|格納する情報|  
|---|---|  
|marker|マーカー|     

####Cue Point####

|変数名|格納する情報|  
|---|---|  
|cue_point|キューポイント|     

####Program Name####

|変数名|格納する情報|  
|---|---|  
|program_name|プログラム色|     

####Device Name####

|変数名|格納する情報|  
|---|---|  
|device_name|デバイス名|     

####MIDI Channel Prefix####

|変数名|格納する情報|  
|---|---|  
|midi_channel|イベントに対応させるMIDIチャンネル番号|     

####Port Designation####

|変数名|格納する情報|  
|---|---|  
|port|ポート|     

####Tempo####

|変数名|格納する情報|  
|---|---|  
|tempo|テンポ|     

####SMPTE Offset####

|変数名|格納する情報|  
|---|---|  
|offset|トラックチャンクがスタートすべきSMPTE時間|     

####Setting Time Signature####

|変数名|格納する情報|  
|---|---|  
|molecule|拍子の分子|  
|denominator|拍子の分子|  
|click|メトロノームの1カウントあたりのMIDIクロック数|  
|notes_per_clocks|４分音符あたりの32分音符の数|   

####Setting Tone####

|変数名|格納する情報|  
|---|---|  
|sf|シャープまたはフラットの数|  
|mi|メジャーかマイナー|  

####Sequencer Specific Meta-Event####

|変数名|格納する情報|  
|---|---|  
|data|データ|  

####Unkown####

|変数名|格納する情報|  
|---|---|  
|data|データ|  

###MIDIMessage型###
MIDIメッセージに関する情報を格納します．  
MIDIMessage型はChannelMessage型の構造体と，SystemMessage型の構造体で構成されています．
使用する変数を以下に示します．

|変数名|格納する情報|  
|---|---|  
|tm|タイムスタンプ|  
|event|イベント名|  
|ch|チャンネルメッセージのデータ|  
|sys|システムメッセージのデータ|  

event変数に格納されているテキストを確認し，必要な構造体のメンバにアクセスして下さい．  
event変数に格納されるテキストは以下のようになります．

|イベント名|テキスト|  
|---|---|  
|Note Off|'Note Off'|  
|Note On|'Note On'|  
|Polyphonic Key Pressure|'Polyphonic Key Pressure'|  
|Program Change|'Program Change'|  
|Control Change|'Control Change'|  
|Channel Pressure|'Channel Pressure'|  
|Pitch Bend|'Pitch Bend'|  
|SysEx F0|'SysEx F0'|  
|SysEx F7|'SysEx F7'|  
|Sequence Number|'Sequence Number'|  
|Text|'Text'|  
|Copyright Notice|'Copyright Notice'|  
|Sequence Name|'Sequence Name'|  
|Instrument Names|'Instrument Names'|  
|Lyrics|'Lyrics'|  
|Marker|'Marker'|  
|Cue Point|'Cue Point'|  
|Program Name|'Program Name'|  
|Device Name|'Device Name'|  
|MIDI Channel Prefix|'MIDI Channel Prefix'|  
|Port Designation|'Port Designation'|  
|Track Termination|'Track Termination'|  
|Tempo|'Tempo'|  
|SMPTE Offset|'SMPTE Offset'|  
|Setting Time Signature|'Setting Time Signature'|  
|Setting Tone|'Setting Tone'|  
|Sequencer Specific Meta-Event|'Sequencer Specific Meta-Event'|  
|Unkownt|'Unkown'|  

ライセンス
----------
Copyright &copy; 2014 Hiroaki Matsuda  
Licensed under the [Apache License, Version 2.0][Apache]  
Distributed under the [MIT License][mit].  
Dual licensed under the [MIT license][MIT] and  [Apache License, Version 2.0][Apache].  
 
[Apache]: http://www.apache.org/licenses/LICENSE-2.0
[MIT]: http://www.opensource.org/licenses/mit-license.php