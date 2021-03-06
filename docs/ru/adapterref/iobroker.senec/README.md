---
BADGE-NPM version: http://img.shields.io/npm/v/iobroker.senec.svg
BADGE-Downloads: https://img.shields.io/npm/dm/iobroker.senec.svg
BADGE-Dependency Status: https://img.shields.io/david/nobl/iobroker.senec.svg
BADGE-Known Vulnerabilities: https://snyk.io/test/github/nobl/ioBroker.senec/badge.svg
BADGE-NPM: https://nodei.co/npm/iobroker.senec.png?downloads=true
BADGE-Travis-CI: http://img.shields.io/travis/nobl/ioBroker.senec/master.svg
translatedFrom: de
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.senec/README.md
title: ioBroker.senec
hash: xeHpc3ZfZ6D1M7ERrGpvfx5Mk53i01uoq2k0hJmuiNg=
---
![логотип](../../../de/adapterref/iobroker.senec/admin/senec.png)

# IoBroker.senec
## Адаптер SENEC для ioBroker
Адаптер был разработан для систем Senec Home V2.1.
Никакие значения не могут быть изменены в системе Senec.Home. Нагрузка на безопасность была намеренно исключена.
Senec больше не предоставляет надежного способа влиять на бритье пиков через веб-интерфейс. Для этого mein-senec.de должен приложить усилия.
То, работают ли другие системы (например, V3), также зависит от того, основаны ли они также на lala.cgi и предоставляют ту же информацию JSON.
Даже с интеграцией в Senec.Clound нет никакой гарантии, что к данным можно будет получить доступ через веб-интерфейс (см. Полевые отчеты).

Системы, которые должны работать, потому что они используют один и тот же интерфейс, перечислены ниже. Однако точки данных могут быть разными (отсутствующими, дополнительными, измененными).

* Senec Home 4.0 / ведущий
* Сенек Хоум 6.0 Pb
* Сенек Хоум 8.0 / свинец
* Сенек Хоум 10.0 Pb
* Senec Home 5.0 / 7.5 / 10.0 / Литий
* Сенек Хоум 15.0 / литий
* Senec Home V2 5.0 / 7.5 / 10.0
* Senec Home V2 10.0 / свинец
* Senec Home V2.1 1ph / Литий
* Senec.Home V3 Hybrid
* Senec.Home V3 Hybrid Duo
* Сенек Бизнес 30.0 / лидерство
* Senec Business V2 30.0 / лидерство
* Сенек Бизнес 25.0 / Литий
* Senec Business V2_2ph / Литий
* Senec Business V2 3ph / Литий
* ADS Tec
* OEM LG
* Solarinvert Storage 10.0 / лидерство,

### Сенек.Дом
Это система, сердцем которой является литий-ионная батарея, которая накапливает и выделяет электричество, генерируемое солнечной системой на крыше. Это работает так же, как аккумулятор в смартфоне, ноутбуке или беспроводной отвертке. В принципе, он также имеет те же проверенные технологии. Если вы производите больше электричества на крыше, чем можете использовать сами в доме, электричество поступает не в сеть, а в ваше хранилище. Вы можете использовать его, когда стемнеет, или будут подниматься облака, и вы будете генерировать меньше или вообще не будет электричества. Затем вы также можете вечером управлять телевизором с помощью солнечной энергии или готовить еду.

## Требования перед установкой
Обязательным условием работы системы хранения Senec.Home с ioBroker является успешная установка системы электриком. Система также должна быть в той же сети, что и ioBroker.

### Установка
Экземпляр адаптера устанавливается через интерфейс администратора ioBroker.
После завершения установки экземпляра адаптера окно конфигурации открывается автоматически.

## Конфигурация
### Главное окно настроек
![Основные настройки](../../../de/adapterref/iobroker.senec/media/mainSettings.png "Основные настройки")

| Поле | Описание |
|:-------------|:-------------|
| Система SENEC | Здесь будет указан IP-адрес нужной системы Senec.Home. Если в сети есть работающий DNS, также можно указать полное доменное имя |
| Интервал запроса с высоким приоритетом | Здесь можно ввести временные интервалы (миллисекунды) для получения высокого приоритета из Senec.Home Systems. (По умолчанию: 10 секунд) |

| Интервал запроса с низким приоритетом | Здесь можно ввести временные интервалы (миллисекунды) для получения низкого приоритета от Senec.Home Systems. (По умолчанию: 60 минут) <br> Внимание! Если система SENEC запрашивается на слишком высокой частоте, это может означать, что на сервер SENEC больше нельзя передавать данные! (например, нет текущих значений в приложении или на mein-senec.de) |

| Request-Timeout | Здесь вы вводите количество миллисекунд, после которых система Senec.Home должна ответить на запрос, прежде чем запрос будет отменен. (По умолчанию: 5000) |
| Попытки повторения | Количество попыток запросить систему Senec в случае возникновения ошибки. Это не относится к моменту запуска адаптера - если система недоступна, адаптер завершает свою работу. (По умолчанию: 10) |
| Коэффициент повтора опроса | Это значение может использоваться для влияния на интервал между попытками повтора. Применяется следующее: попытка n-й попытки выполняется через интервал *множитель* n секунд после попытки n-1. Пример: при значениях по умолчанию 1-я попытка повторной попытки происходит через 20 секунд после первой попытки, а вторая попытка повторной попытки - через 40 секунд после первой. При успешном извлечении данных счетчик повторных попыток сбрасывается. |

После завершения настройки выйдите из диалогового окна конфигурации, нажав `SPEICHERN UND SCHLIEßEN`.
Это затем перезапустит адаптер.

## Экземпляры
При установке адаптера был создан активный экземпляр адаптера sonnen в разделе §SSSSS_0§§.

Несколько экземпляров Senec Adapter могут быть созданы на сервере ioBroker. И наоборот, система Senec.Home также может работать с несколькими серверами ioBroker. Если несколько устройств должны управляться одним сервером ioBroker, для каждой системы должен быть создан один экземпляр. <br/><br/> Цвет поля состояния экземпляра указывает, активирован ли адаптер и подключен ли он к системе. Если указатель мыши указывает на символ, отображается дополнительная подробная информация.

Объекты адаптера
В области `Objekte` все устройства и действия, распознаваемые адаптером в концентраторе, перечислены в древовидной структуре.

Затем объекты делятся на состояния.
Каждая точка данных указана с соответствующим типом данных и ее полномочиями.
Разрешения в настоящее время могут быть прочитаны только (R). Каждую точку данных можно прочитать как минимум (R).
Для поиска конкретной точки данных мы рекомендуем использовать комбинацию клавиш «CTRL + F».
В зависимости от отдельной системы, состояния могут не существовать или могут возникать состояния, которые не задокументированы.
Если документация по штату отсутствует, но кто-то знает, что представляет собой штат, отправьте мне запрос на извлечение (или откройте тикет с соответствующей информацией).

### Примеры состояний (доступные состояния зависят от системы и версии программного обеспечения)
#### Канал: информация
* info.connection

    | Тип данных | Разрешение |
    |:---:|:---:|
    | булево | R |

   *Только для чтения логическое значение, которое верно, когда установлено соединение между ioBroker и Senec.Home.*

#### Канал: BMS
* BL [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, указывающий:? для каждого аккумулятора.*

* CHARGED_ENERGY [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   * Только для чтения номер, который указывает, сколько энергии было заряжено за батарейный блок. Единица измерения: ?*

* CHARGE_CURRENT_LIMIT [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемое число, которое указывает, насколько высокая зарядная емкость на батарейный блок в амперах.*

* ТЕКУЩИЙ [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только для чтения номер, который указывает, сколько ампер каждый батарейный блок имеет в настоящее время.*

* ЦИКЛЫ [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает, сколько циклов зарядки имеет каждый батарейный блок.*

* DISCHARGED_ENERGY [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   * Только для чтения номер, который указывает, сколько энергии было извлечено из батарейного блока. Единица измерения: ?*

* DISCHARGE_CURRENT_LIMIT [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает, какая разрядная емкость каждого батарейного блока в настоящее время имеет.*

* FW [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает, какую версию прошивки имеет аккумуляторная батарея.*

* HW_EXTENSION [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает, какое аппаратное расширение имеет соответствующий аккумуляторный блок.*

* HW_MAINBOARD [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает, какую версию аппаратного обеспечения имеет материнская плата соответствующего аккумулятора.*

* MAX_CELL_VOTAGE [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только для чтения номер, который указывает максимальное напряжение отдельного аккумулятора.*

* MIN_CELL_VOTAGE [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только для чтения номер, который указывает минимальное напряжение отдельного аккумулятора.*

* SN [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает серийный номер каждого аккумулятора.*

* SOC [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только для чтения номер, который указывает состояние зарядки отдельного аккумулятора.*

* SOH [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает на состояние здоровья отдельного аккумулятора.*

* СТАТУС [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает, каково состояние каждого аккумулятора.*

* TEMP_MAX [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только для чтения номер, который указывает максимальную температуру отдельного аккумулятора.*

* TEMP_MIN [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только для чтения номер, который указывает минимальную температуру отдельного аккумулятора.*

* НАПРЯЖЕНИЕ [0-3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает, насколько высоко вольт каждого батарейного блока.*

* BMS_READY_FLAG

    | Тип данных | Разрешение |
    |:---:|:---:|
    | булево | R |

   *Только для чтения логическое значение, которое истинно, если BMS готова.*

* MODULES_CONFIGURED

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает, сколько модулей настроено в системе.*

* MODULE_COUNT

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает, сколько модулей подключено в системе (включая ненастроенные).*

* НАЧАТЬ ОБНОВЛЕНИЕ

    | Тип данных | Разрешение |
    |:---:|:---:|
    | булево | R |

   *Только читаемое логическое значение, которое имеет значение true, если необходимо запустить обновление.*

* WIZARD_ABORT

    | Тип данных | Разрешение |
    |:---:|:---:|
    | булево | R |

   *Только для чтения логическое значение, что правда, процесс установки был прерван.*

* WIZARD_CONFIRM

    | Тип данных | Разрешение |
    |:---:|:---:|
    | булево | R |

   *Только читаемое логическое значение, которое верно, процесс установки был подтвержден.*

* WIZARD_DCCONNECT

    | Тип данных | Разрешение |
    |:---:|:---:|
    | булево | R |

   *Только читаемое логическое значение, что верно, процесс установки ?.*

* WIZARD_START

    | Тип данных | Разрешение |
    |:---:|:---:|
    | булево | R |

   *Только для чтения логическое значение, которое верно при запуске процесса установки.*

* WIZARD_STATE

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает на состояние процесса установки.*

#### Канал: ЭНЕРГИЯ
* GUI_BAT_DATA_CURRENT

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает текущий ток батареи в амперах.*

* GUI_BAT_DATA_FUEL_CHARGE

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только для чтения номер, который указывает уровень в% от системы.*

* GUI_BAT_DATA_VOLTAGE

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает текущее напряжение батареи в вольтах*

* GUI_BAT_DATA_POWER

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемое число, которое указывает, сколько ватт в настоящее время подается в батарею или извлекается из нее (отрицательное значение).*

* GUI_BOOSTING_INFO

    | Тип данных | Разрешение |
    |:---:|:---:|
    | булево | R |

   *Только читаемое логическое значение, значение которого пока неясно.*

* GUI_CHARGING_INFO

    | Тип данных | Разрешение |
    |:---:|:---:|
    | булево | R |

   *Только читаемое логическое значение, указывающее, заряжается ли батарея.*

* GUI_GRID_POW

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемое число, которое указывает, сколько ватт в настоящее время извлекается из сетки или подается в сетку (отрицательное значение).*

* GUI_HOUSE_POW

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только для чтения номер, который указывает, сколько ватт в настоящее время используется в доме.*

* GUI_INVERTER_POWER

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только для чтения номер, который указывает, сколько ватт в настоящее время генерируется системой PV.*

* STAT_HOURS_OF_OPERATION

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает часы работы системы.*

* STAT_MAINT_REQUIRED

    | Тип данных | Разрешение |
    |:---:|:---:|
    | булево | R |

   *Только для чтения логическое значение, указывающее, нуждается ли система в обслуживании.*

* STAT_STATE

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который представляет состояние системы.*

* STAT_STATE_Text

    | Тип данных | Разрешение |
    |:---:|:---:|
    | строка | R |

   *Только читаемая символьная строка, которая указывает состояние системы в виде простого текста. К сожалению, у нас есть только оригинальные тексты Senec на немецком языке.*

#### Канал: STATISTIC
* STAT_DAY_BAT_CHARGE

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемое число, которое указывает, сколько киловатт-часов хранилось в батарее сегодня.*

* STAT_DAY_BAT_DISCHARGE

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемое число, которое указывает, сколько киловатт-часов было взято от батареи сегодня.*

* STAT_DAY_E_GRID_EXPORT

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемое число, которое указывает, сколько кВтч было подано в сеть сегодня.*

* STAT_DAY_E_GRID_IMPORT

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает, сколько кВтч было получено из сети сегодня.*

* STAT_DAY_E_HOUSE

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемое число, которое указывает текущее потребление дома в кВтч.*

* STAT_DAY_E_PV

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемое число, которое указывает, сколько кВтч было произведено системой PV сегодня.*

#### Канал: SYS_UPDATE
* NPU_IMAGE_VERSION

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   * Только для чтения номера, со значением для ревизии NPU-IMAGE (*

* NPU_VER

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер со значением для редакции NPU-REGS*

* ОБНОВЛЕНИЯ ДОСТУПНЫ

    | Тип данных | Разрешение |
    |:---:|:---:|
    | булево | R |

   *Только читаемое логическое значение, указывающее, доступно ли обновление (однако оно предоставляется Senec и также импортируется автоматически).*

#### Канал: WIZARD
* APPLICATION_VERSION

    | Тип данных | Разрешение |
    |:---:|:---:|
    | строка | R |

   *Только для чтения текста, со значением для ревизии MCU.*

* CONFIG_LOADED

    | Тип данных | Разрешение |
    |:---:|:---:|
    | булево | R |

   *Только для чтения логическое значение, которое указывает, была ли загружена конфигурация (это значение не должно быть постоянно неверным).*

* INTERFACE_VERSION

    | Тип данных | Разрешение |
    |:---:|:---:|
    | строка | R |

   *Только читаемый текст со значением для графического интерфейса редакции.*

* SETUP_NUMBER_WALLBOXES

    | Тип данных | Разрешение |
    |:---:|:---:|
    | число | R |

   *Только читаемый номер, который указывает, сколько настенных ящиков настроено в системе.*

* SETUP_WALLBOX_SERIAL [0..3]

    | Тип данных | Разрешение |
    |:---:|:---:|
    | строка | R |

   *Только читаемый текст, который указывает серийные номера возможных существующих настенных коробок 0-3.*

## Changelog
### 1.0.9 (NoBl)
* IP types are shown as IP again.
* added datapoints for FACTORY along with more state descriptions for Battery Type, Country and System Type.
* added datapoints for GRIDCONFIG

### 1.0.8 (NoBl)
* Added more states to known states (please feedback if they need special handling (unit, special description, value modification, ...))
* Bugfix in creating debug data
* Unknown states are now reported in debug instead of info.
* Code cleanup

### 1.0.7 (NoBl)
* Reading all known states from SENEC.
* Split states into high/low priority (heavy requesting the SENEC system renders it unable to sync with the SENEC datacenter!).
* Updated adapter-core and testing versions along with current dev dependencies. Removed node 8 support.
* Added more state descriptions to manual. But need input on these and those that are still not documented.

### 1.0.6 (NoBl)
* Moved senec states and state attributes to libs
* Added missing state descriptions

### 1.0.5 (2020-03-07) (NoBl)
* Added States for: Energy: GUI_BAT_DATA_VOLTAGE, GUI_BAT_DATA_CURRENT, STAT_HOURS_OF_OPERATION; Sys_update: NPU_VER, NPU_IMAGE_VERSION, Wizard: APPLICATION_VERSION, INTERFACE_VERSION
* Readme and Documentation (EN exists, now) updated
* Changed behavior for unknown values completely. They will now be stored as string plus prefixed with "REPORT TO DEV:" so users can easily report back what needs updating.
* added handling for "st_" values in json
* added additional configuration options
* changed retry-behaviour in case of connection issues, ...

### 1.0.4 (2020-03-06)
* (NoBl) Repo URL updated
### 1.0.3 (2020-03-06)
* (NoBl) added link to documentation in german
### 1.0.2 (2020-03-04)
* (NoBl) added missing status codes (85 in total now)
* (NoBl) added status code to status message for easier reference
* (NoBl) added states for wallboxes and battery modules
### 1.0.1
* (NoBl) updated readme
### 1.0.0
* (NoBl) initial release

## License
MIT License

Copyright (c) 2020 Norbert Bluemle <github@bluemle.org>

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