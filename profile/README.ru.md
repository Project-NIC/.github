<div align="center">

# ★ N.I.C. ★

**Native Intellect Community** — простые проверенные принципы, стандартное железо, открытые проекты.

[English](https://github.com/Project-NIC) · [Čeština](https://github.com/Project-NIC/.github/blob/main/profile/README.cs.md) · **Русский**

[Что такое NIC?](#что-такое-nic)

</div>

---

# NIC-Arduino

**Программный стек хранения, передачи и просмотра данных для малых устройств** — формат журнала,
устойчивый к сбоям, необязательные сжатие и шифрование, мосты на вход и выход, экспортёры для
сейсмических и геомагнитных сетей и просмотрщик. **Закрыт на версии 1.2 — окончательная версия.**

→ **[Project-NIC/NIC-Arduino](https://github.com/Project-NIC/NIC-Arduino)**

<details>
<summary><b>Модули</b> — восемь</summary>

| модуль | что это |
|---|---|
| [**NIC-MLA**](https://github.com/Project-NIC/NIC-Arduino/tree/main/mla) | Matroshka Logging Archive — базовый формат журнала, один устойчивый к сбоям файл |
| [**NIC-DMD**](https://github.com/Project-NIC/NIC-Arduino/tree/main/dmd) | Delta Markov Duda — необязательное сжатие |
| [**NIC-KSF**](https://github.com/Project-NIC/NIC-Arduino/tree/main/ksf) | Kolmogorov Shannon Feistel — необязательное шифрование |
| [**NIC-GLUE-IN**](https://github.com/Project-NIC/NIC-Arduino/tree/main/glue-in) | запись данных в журнал MLA |
| [**NIC-GLUE-OUT**](https://github.com/Project-NIC/NIC-Arduino/tree/main/glue-out) | чтение и экспорт журнала MLA — CSV, SQLite, … |
| [**NIC-MSEED**](https://github.com/Project-NIC/NIC-Arduino/tree/main/mseed) | журнал MLA → miniSEED (ObsPy / SeisComP / FDSN) |
| [**NIC-IAGA**](https://github.com/Project-NIC/NIC-Arduino/tree/main/iaga) | журнал MLA → IAGA-2002 (INTERMAGNET / SuperMAG) |
| [**NIC-VDE**](https://github.com/Project-NIC/NIC-Arduino/tree/main/vde) | Volkov Data Ecosystem — просмотр и экспорт журналов MLA |

</details>

<br>

---

# NIC-Heimdall

<p align="center"><img src="https://github.com/Project-NIC/.github/raw/main/profile/NIC-Heimdall.jpg" width="300" alt="Heimdall"/></p>

**Одна автономная измерительная станция для твёрдой Земли, атмосферы и ионосферы** — корпус
с центральным блоком, часами и картами и те блоки, которые нужны на данном месте, всё на одной
тактированной шине. Замените блоки — и это другой прибор на той же шине и с тем же кодом.
**Версия 0.2 — концепция на стадии проектирования:** каждая плата описана до последнего
компонента, пока ничего не построено. README — на английском, чешском и русском.

→ **[Project-NIC/NIC-Heimdall](https://github.com/Project-NIC/NIC-Heimdall)**

<details>
<summary><b>Корпус</b> — центральный блок, часы, питание, карты, передача</summary>

| часть | что это | шина · тип |
|---|---|---|
| [**Mayak**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/mayak) | центральный блок — регистратор и связь с миром (Wi-Fi, модем, BLE), архив на двух картах microSD | NodBus 1 |
| [**Kronos**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/kronos) | часы — TCXO, подстраиваемый по GNSS, такт сети и секунда для каждой карты | — |
| ↳ [**Polaris**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/kronos/polaris) | GNSS-фронтенд Kronos, покупной — приёмник только для времени и антенна на плате-носителе | — |
| [**Hermes**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/hermes) | преобразователь BMS/MPPT — читает для центрального блока покупную батарею и зарядное устройство | — |
| [**Bifrost**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/bifrost) | мастер шины NodBus — четыре отвода точка–точка, медь до 500 m, дальше стекло | NodBus 2 |
| ↳ [**Argus**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/bifrost/argus) | та же карта как мастер NodBus mini — четыре сегмента для малых блоков | NodBus 3 |
| [**Galvani**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/galvani) | транспортный уровень — одиннадцать плат; всё, что выходит из корпуса, проходит через одну из них | — |
| [**Mimir**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/mimir) | mini-Heimdall — центральный блок, часы, две карты, Palatine и Hermes на одной плате | — |
| [**Proteus**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/proteus) | самый маленький полный центральный блок станции, одна плата в слот 1-DIN — для машины или места с одним блоком | — |

</details>

<details>
<summary><b>Блоки</b> — что измеряет станция</summary>

| блок | что измеряет | шина · тип |
|---|---|---|
| [**Quake**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quake) | движение грунта, местные события и наклон | NodBus 5 |
| [**Tesla**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/tesla) | молнии — сферики ОНЧ, каждый импульс привязан к часам сети | NodBus 7 |
| ↳ [**Pip**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/tesla/pip) | длинноволновые несущие — область D и время по длинным волнам; плата Tesla | NodBus 12 |
| ↳ [**Steinmetz**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/tesla/steinmetz) | повреждения на линиях электропередачи, с машины или с места; плата Tesla | NodBus 13 |
| [**Marconi**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/marconi) | ионосфера в КВ-диапазоне — уровни передатчиков 0,5–16 MHz, пассивная ионограмма | NodBus 4 |
| [**Sputnik**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/sputnik) | GNSS — полное электронное содержание и время станции, если установлен | NodBus 8 |
| [**Palatine**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/palatine) | метеобаза — четыре ветви ModBus для покупного метеокомплекта и собственных модулей | NodBus 6 |
| ↳ [**Chinook**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/palatine/chinook) | качество воздуха — покупные блоки на ветвях Palatine | — |
| [**Quark**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark) | радиация — два исполнения, трубками и сцинтилляцией | — |
| ↳ [**Quark-Tubes**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark/tubes) | каждая трубка считается на одной плате — трубки ГМ, Helion и Gadolin для нейтронов | mini 2 |
| ↳ [**Photon**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark/scintillation/photon) | гамма и рентген сцинтилляцией, счёт и энергия | NodBus 9 |
| ↳ [**Positron**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark/scintillation/positron) | бета обоих знаков, на той же плате с каналом Neutron | NodBus 11 |
| [**Gauss**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/gauss) | медленное геомагнитное поле — герметичный магнитометрический зонд | mini 1 |
| [**Pascal**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/pascal) | датчик цунами на морском дне | mini 3 |
| [**Pluvius**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/pluvius) | осадки, взвешиванием | ModBus 5 |
| [**Ceres**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/ceres) | влажность и температура почвы, через стекло | ModBus 6 |
| ↳ [**Sakura**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/ceres/sakura) | увлажнённость листьев — плата Ceres в кроне | ModBus 7 |
| [**Babel**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/babel) | любой датчик → Modbus RTU, преобразование у датчика | ModBus 4 |

</details>

<details>
<summary><b>Станция в целом и программы</b></summary>

| часть | что это |
|---|---|
| [**Atlantis**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/atlantis) | морское исполнение — Pascal и Gauss у берега; длинная глубоководная линия отложена |
| [**Daedalus**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/daedalus) | постройка станции — мачта, заземление, корпус, колодец, кабели |
| [**Gaia**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/gaia) | атлас размещения — где на планете стоят станции |
| [**HMC**](https://github.com/Project-NIC/NIC-Heimdall/blob/main/core/archive/HMC.md) | Heimdall Matryoshka Container — архив станции, от карты до сервера |
| [**HCC**](https://github.com/Project-NIC/NIC-Heimdall/blob/main/core/archive/HCC.md) | Heimdall Compression Codec — без потерь, столбец за столбцом; эталонная реализация на Python с тестами |
| [**Exporters**](https://github.com/Project-NIC/NIC-Heimdall/blob/main/core/archive/EXPORTERS.md) | архив в форматах, которые принимает мир — miniSEED, IAGA-2002, RINEX, BUFR, CSV, SQL, … |
| [**Server**](https://github.com/Project-NIC/NIC-Heimdall/blob/main/core/archive/HMC.md#on-the-server) | файлы как основной архив, каталог над ними и просмотрщик |
| [**Handset**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/mayak/handset) | приложение для ввода в эксплуатацию — телефон у открытого корпуса, через BLE |

</details>

<br>

---

# NIC-BumbleBee <sub><i>Russian Power</i></sub>

**Энергетическая часть — NIC-FPLG, двухтактный линейный двигатель без коленчатого вала:** два
поршня на одном штоке с трубчатым линейным генератором в центре, работающий в механическом
резонансе, а не на регулируемых оборотах. ~3 kW механической мощности, 1–1,5 kW электрической;
**спаренный в противофазе**, он гасит ~88 % собственной вибрации.

→ **[Project-NIC/NIC-BumbleBee](https://github.com/Project-NIC/NIC-BumbleBee)**

<br>

---

# NIC-CrazyIvan

<p align="center"><img src="https://github.com/Project-NIC/.github/raw/main/profile/NIC-CrazyIvan.jpg" width="300" alt="Crazy Ivan"/></p>

**Нейрокостюм** — от 126 до 254 электродов и от 16 до 64 датчиков движения на костюме из частей:
рукав, штанина, торс, повязка. Собственные сигналы мышц и движение тела идут в компьютер в
рюкзаке, Radxa ROCK 5T с одним или двумя ИИ-ускорителями Hailo-10H или Raspberry Pi 5 с одним, и
всё тело становится контроллером для компьютера или игры. **Coming soon™.** Ну, не *так* уж скоро.

→ **[Project-NIC/NIC-Crazy_Ivan](https://github.com/Project-NIC/NIC-Crazy_Ivan)** — бета 0.1: проект на бумаге, ничего ещё не построено;
README по-русски, остальные страницы по-английски

<details>
<summary><b>Части</b> — костюм, голова, семья в рюкзаке, помощники</summary>

| часть | что это |
|---|---|
| [**Rubaška**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/rubaska) | рубашка: сам костюм, части с измерительными модулями, Ребята |
| [**Nataša**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/natasa) | блок в повязке: наушники, два микрофона, вибрация и кнопки |
| [**Mamka**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/mamka) | мама, базовая плата: такт всего костюма, звуковой мост, драйверы линий и питание костюма |
| [**Baťa**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/bata) | батя, компьютер в рюкзаке: Radxa ROCK 5T или Raspberry Pi 5, с Умницей, Hailo-10H |
| [**Kormilica**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/kormilica) | кормилица: плата питания Raspberry Pi |
| [**Terem**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/terem) | терем: плата под ROCK 5T с двумя его Hailo-10H и eFuse |
| [**Babuška**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/babuska) | бабушка: батарея и её BMS, рюкзак с жёстким корпусом |
| [**Porjadok**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/porjadok) | порядок: что действует для каждого модуля, процессор, прошивка и связи |
| [**Soňa**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/sona) | помощница для глухих: всё время слушает и вибрацией сообщает, что происходит вокруг |
| [**Míša**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/misa) | помощник, сторож: радар и ультразвук следят за препятствиями и предупреждают через наушники и повязку |
| [**Taťána**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/tatana) | помощница: печатает, что ей диктуют, и читает текст вслух, книги тоже |
| [**Nikita**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/nikita) | помощник: такт музыки как вибрация |

</details>

<br>

---

# ★ N.I.C. ★
## NIC — Native Intellect Community
### Viva la résistance! ✊

---

## Что такое NIC?

NIC — для людей, которые:

- Используют простые и проверенные принципы
- Готовы тестировать и создавать
- Работают со стандартизированным оборудованием и средой
- Не нуждаются в раздутых решениях чтобы доказать, что что-то умеют

NIC — это революционное движение всех товарищей, которых не устраивает сегодняшний переоценённый и излишне усложнённый мир.

*«Сила в простоте.»*

★ **Viva la résistance!** ★

---
[![License: MIT](https://img.shields.io/badge/License-MIT-red.svg)](https://opensource.org/licenses/MIT)
