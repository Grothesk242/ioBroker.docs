---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.alarm/README.md
title: ioBroker.alarm
hash: HTGk4nS62rUA6r2P64RF+fNZf28kh3UB08Sw/nwlbp4=
---
![商标](../../../en/adapterref/iobroker.alarm/admin/alarm.png)

![安装数量](http://iobroker.live/badges/alarm-stable.svg)
![NPM版本](http://img.shields.io/npm/v/iobroker.alarm.svg)
![资料下载](https://img.shields.io/npm/dm/iobroker.alarm.svg)
![依赖状态](https://img.shields.io/david/misanorot/iobroker.alarm.svg)
![已知漏洞](https://snyk.io/test/github/misanorot/ioBroker.alarm/badge.svg)
![NPM](https://nodei.co/npm/iobroker.alarm.png?downloads=true)
![特拉维斯](http://img.shields.io/travis/misanorot/ioBroker.alarm/master.svg)

＃ioBroker.alarm
[![paypal]（https://www.paypalobjects.com/zh_CN/DK/i/btn/btn_donateCC_LG.gif）](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=ZYHW84XXF5REJ&source=url)

**[英文说明](https://github.com/misanorot/ioBroker.alarm/blob/master/lib/Readme_en.md)**

## IoBroker警报
Dies ist ein Adapter（适配器适配器），mit dem sich eine kleine Alarmanlage ohnegroßeprogrammiertechnische Vorkenntnisse realisierenlässt。
二等译本Nachtruhe oder De- und Aktivierung zuüberwachen。德斯坦·维特伦主义者·伊恩·迪内克特·德斯坦·威斯坦·因斯坦斯（州），安德·安德里（auf andere）“州”。 DieseVerknüpfungenwerden im ReiterVeregnüpfungenangelegt。

-------------------------------------------------- -------------------------------------------------- ------------------ *站位05.07.2020 ab版本0.8.0 *

#### Wichtig抗体0.8.0
-如果安装<0.8.0，请更新适配器，然后再安装！ Es haben sich ein paar Datenpunktegeändert。

### Tab Haupteinstellungen
较高的等级，包括Zeiten der Nachtruhe，Sirenezeit，Stiller-Alarm和Passwort vorgenommen。

* Alle Zeiten在Sekunden einzugeben中犯罪*

-Aktivierzeit->Zeitverzögerungbis zu Aktivierung wenn man einen delay Datenpunkt benutzt
-Sienenzeit bei Einbruch-> Bei Einbruch wird der Datenpunkt alarm.0.status.sirenfürdie Zeit auf true gesetzt
-Alarmverzögerung->Verzögerungszeitbis Einbruchausgelöstwird（währenddieser Zeit wird der Stille Alarmausgelöst）
-Warnungen / Sirene innen的Auslösezeitit-> Benachrichtigungskreises ods scharf innen的北AuslösungeKreises，jewerilszugehörigeDatenpunktfürdie Zeit auf true gesetzt

----------------------------------------------------------------------------------------------------------------------

### Tab Benachrichtigungen
BenachrichtigungenüberAndere适配器wie z.B.电报，电子邮件或其他。
[问题](#Probleme)

----------------------------------------------------------------------------------------------------------------------

### TabÜberwachung
werden die Kreise der Anlage konfiguriert。
*戴姆·德恩州立大学拉森学院

阿尔赫拉克（Achage）的优先权和“帽子”优先（scharf）Vorrang vor allen anderen Keisen。阿尔赫拉特（Al dient zur eigentlichenÜberwachungder Anlage）死了。结束了实习生的工作，开始了实习生和实习生的工作。
* Es ist durchausmöglich，艾斯州立大学，登哈肯·贝艾伦·德雷·克赖森马克特。

Die Kreise werdenfolgendermaßenüberwacht：

#### Alarmkreis：
阿兰基拉格州议会议员（沙尔夫·沙尔滕）您可以在警报器中查看警报。

#### Scharf实习生Kreis：
Alle hier konfigurierten州werden beim Zustand scharf实习生überwachtundLösen实习生anerem den internen报警澳大利亚。

#### Meldekreis：
维也纳州立大学和维尔京群岛死了。

----------------------------------------------------------------------------------------------------------------------

### Tab Sprachausgabe
Iine eewgewünschteSprachausgabe z.B. bei beiÄnderungdes Zustandesgewünscht，lässtsich das hier mit dengewünschtenSätzenkonfigurieren。
*曼·穆斯·希奇·谢尔·塞恩（Mus sich sicher sein），达斯·奥斯特瓦特·达滕彭克（das derausgewählteDatenpunkt），麻省理工学院的einem Text beschrieben werden kann！ Z.B. “ sayit.0.tts” *

曼彻斯特人（Ausgabe von Namen mit Ansagen lassen），坎恩曼彻斯（Kann man diese）选择anwählen。

----------------------------------------------------------------------------------------------------------------------

### TabVerknüpfungen
等级较高的适配器州际直属州外部州zuverknüpfen。 Somit ist ein Umwegüberein Skript oderähnlichennicht erforderlich。
Eslässtsich somit z.B.在Nachtruhe的Beginn der初创公司中，Veriegelung desTürschlosses成为了现实。
![商标](../../../en/adapterref/iobroker.alarm/admin/img/short.png)

####Eingabeverknüpfungen
触发器->任意= es wird bei jederÄnderunggetriggert ne = es wird nur getriggert wenn der Wert sichgeändert

Auslösewert-> Ist der Wert，Auf welchen getriggert werden soll

----------------------------------------------------------------------------------------------------------------------

Der Adapter liefert eine ganze Anzahl国家/地区：

####“ alarm.x.use .....”。
紧急状态下的警报和警报状态。

-use.activate_nightrest-> Aktivierung der Nachtruhe
-use.activate_sharp_inside_circuit->战役实习生（实习生）
-use.disable-> Deaktivierung der Anlage（Alarmkreis）
-use.enable-> Aktivierung der Anlage（Alarmkreis）
-use.enable_with_delay->安提格（Alarmkreis）博物馆
-use.list-> Deaktivierung / Aktivierung / Warnkreis / Aktivierung mitVerzögerungszeit
-use.quit_changes->状态设置* info.notification_circuit_changes，info.sharp_inside_siren，status.activation_failed *
-use.toggle_password-> Deaktivierung / Aktivierung der Anlage（Alarmkreis）mit Passwort
-use.toggle_with_delay-> Deaktivierung / Aktivierung der Anlage（Alarmkreis）mitVerzögerungszeit
-use.toggle_with_delay_and_password-> Dealtivierung / Aktivierung der Anlage（Alarmkreis）mit Passwort undVerzögerungszeit
-use.panic->HändischeAuslösungder Alarmanlage（Einbruch）

####“ alarm.x.status ....”
尊贵的祖斯塔德·安拉格能力较高的人。

-status.sleep->自动发送信号Nachtruhe

####“ alarm.x.info ....”
LiefertzusätzlicheInformationen wie z.B. welche“Türenoffen sind” oder einen日志状态。
Mitternacht Geleert的log_today状态。

----------------------------------------------------------------------------------------------------------------------

##问题
-温恩·曼恩（Wen Man eine）的电报oderähnlichesüberdas +hinzufügt，坎恩·曼努尔·爱因州立大学斯坦斯·奥斯威伦州和曼斯·穆斯·比斯·奥夫* telegram.0 * Alleslöschen。

#### Wichtig，死于Benutzung，死于适配器。

## Changelog

#### 1.2.0 (09.07.2020)
* (misanorot) added countdown speech output

#### 1.1.0 (05.07.2020)
* (misanorot) Added input shortcuts

#### 1.0.0 (01.07.2020)
* (misanorot) added alarm and silent flash light

#### 0.9.0 (28.06.2020)
* (misanorot) Homekit integrated, set shortcuts only when changed

#### 0.8.0 (18.06.2020)
#### (misanorot) !!! Changed circuits dramatacly !!! Please do a new installation when you come from less versions

#### 0.7.5 (14.06.2020)
* (misanorot) fixed a few little issues

#### 0.7.0 (07.06.2020)
* (misanorot) edit notification sentences in admin

#### 0.6.0 (31.05.2020)
* (misanorot) changed speech output

#### 0.5.0 (14.05.2020)
* (misanorot) added use.list state

#### 0.4.0 (14.05.2020)
* (misanorot) added warn circuit monitoring

#### 0.3.0 (04.05.2020)
* (misanorot) expaned speech output

#### 0.2.2 (30.04.2020)
* (misanorot) added alexa2 speak output

#### 0.2.0 (22.04.2020)
* (misanorot) added more states

#### 0.1.2 (19.04.2020)
* (misanorot) status.state  activated

#### 0.1.1 (28.03.2020)
* (misanorot) added states and lists - fixed issues - translation

#### 0.1.0 ()
* (misanorot) add password for de/activation -- better logging

#### 0.0.9 (19.02.2020)
* (misanorot) add sayit

#### 0.0.8 (03.02.2020)
* (misanorot) initial release

## License
MIT License

Copyright (c) 2019-2020 misanorot <audi16v@gmx.de>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.