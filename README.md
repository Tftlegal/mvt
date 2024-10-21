<p align="center">
     <img src="https://docs.mvt.re/en/latest/mvt.png" width="200" />
</p>

# Mobile Verification Toolkit

[![](https://img.shields.io/pypi/v/mvt)](https://pypi.org/project/mvt/)
[![Documentation Status](https://readthedocs.org/projects/mvt/badge/?version=latest)](https://docs.mvt.re/en/latest/?badge=latest)
[![CI](https://github.com/mvt-project/mvt/actions/workflows/tests.yml/badge.svg)](https://github.com/mvt-project/mvt/actions/workflows/tests.yml)
[![Downloads](https://pepy.tech/badge/mvt)](https://pepy.tech/project/mvt)

Mobile Verification Toolkit (MVT) is a collection of utilities to simplify and automate the process of gathering forensic traces helpful to identify a potential compromise of Android and iOS devices.

It has been developed and released by the [Amnesty International Security Lab](https://securitylab.amnesty.org) in July 2021 in the context of the [Pegasus Project](https://forbiddenstories.org/about-the-pegasus-project/) along with [a technical forensic methodology](https://www.amnesty.org/en/latest/research/2021/07/forensic-methodology-report-how-to-catch-nso-groups-pegasus/). It continues to be maintained by Amnesty International and other contributors.

> **Note**
> MVT is a forensic research tool intended for technologists and investigators. It requires understanding digital forensics and using command-line tools. This is not intended for end-user self-assessment. If you are concerned with the security of your device please seek reputable expert assistance.
>

## Pegasus

Эксплойт Pegasus использует различные уязвимости для удаленной установки шпионского ПО на устройствах iOS, включая версии до 16.0.3. 
В частности, по состоянию на март 2023 года, Pegasus мог использовать нулевой клик эксплойт, который не требует взаимодействия с жертвой для установки.
Основные эксплойты
CVE-2023-41061: Уязвимость в Wallet, которая может привести к выполнению произвольного кода при обработке специально подготовленного вложения.
CVE-2023-41064: Уязвимость переполнения буфера в компоненте Image I/O, которая также может привести к выполнению произвольного кода при обработке специально подготовленного изображения.
Эти уязвимости были частью цепочки эксплойтов под названием BLASTPASS, которая могла скомпрометировать iPhone без какого-либо взаимодействия со стороны жертвы. Эксплойт использовал вложения PassKit с вредоносными изображениями, отправленными через iMessage от учетной записи атакующего.
Подробности
Zero-click атака: Pegasus использует нулевой клик подход, что означает, что жертве не нужно нажимать на ссылку или выполнять какое-либо действие для того, чтобы эксплойт сработал.
Обнаружение: Уязвимости были обнаружены лабораторией Citizen Lab и быстро исправлены Apple в обновлениях безопасности.
Таким образом, Pegasus использует сложные эксплойты для удаленной установки шпионского ПО на устройствах iOS, включая версии до 16.0.3, используя нулевые клики и уязвимости в системных компонентах.

## NO EXPLOIT

Чтобы защитить устройство Android от шпионского ПО Pegasus, следуйте этим рекомендациям:
1. Обновляйте операционную систему и приложения
Регулярно обновляйте Android и устанавливайте последние версии приложений. Обновления часто содержат исправления безопасности, которые могут закрыть уязвимости, используемые шпионским ПО.
2. Используйте антивирусное программное обеспечение
Установите надежное антивирусное программное обеспечение, которое может обнаруживать и блокировать вредоносные программы. Некоторые антивирусы предлагают функции защиты в реальном времени.
3. Ограничьте разрешения приложений
Проверяйте разрешения, которые запрашивают приложения. Не давайте доступ к микрофону, камере или местоположению приложениям, которые не требуют этих функций для своей работы.
4. Будьте осторожны с ссылками и вложениями
Избегайте нажатия на подозрительные ссылки в сообщениях или электронной почте. Pegasus может использовать методы фишинга для установки шпионского ПО.
5. Используйте двухфакторную аутентификацию
Включите двухфакторную аутентификацию для своих учетных записей, чтобы повысить уровень безопасности.
6. Проверка на наличие шпионского ПО
Используйте инструменты для проверки на наличие шпионского ПО, такие как Mobile Verification Toolkit (MVT), разработанный Amnesty International, чтобы проверить наличие следов Pegasus на вашем устройстве.
7. Избегайте использования устаревших устройств
Если ваше устройство больше не поддерживается обновлениями безопасности, рассмотрите возможность его замены на более новое устройство.
8. Используйте VPN
Использование VPN может помочь защитить вашу интернет-активность и скрыть вашу IP-адрес от потенциальных злоумышленников.
Заключение
Следуя этим рекомендациям, вы сможете значительно повысить уровень безопасности вашего устройства Android и снизить риск заражения шпионским ПО, таким как Pegasus. Если у вас есть дополнительные вопросы или нужна помощь с конкретными настройками, дайте знать!

## CHECK EXPLOIT

Как проверить андройд с помощью MVT на наличие эксплойтов ?

Чтобы проверить устройство Android на наличие эксплойтов и шпионского ПО Pegasus с помощью Mobile Verification Toolkit (MVT), выполните следующие шаги:
Шаги для проверки Android с помощью MVT
Установите необходимые инструменты:
Убедитесь, что у вас установлен Python и необходимые зависимости. Для этого выполните следующие команды в терминале:

sudo apt update
sudo apt install python3 python3-pip adb

Скачайте и установите MVT:
Клонируйте репозиторий MVT с GitHub:
```
git clone https://github.com/mvt-project/mvt.git

cd mvt
```
Установите необходимые Python-библиотеки:
```
pip3 install -r requirements.txt
```
Подготовьте устройство:
Включите режим разработчика на вашем Android-устройстве. Для этого перейдите в Настройки > О телефоне и несколько раз нажмите на Номер сборки.
Включите Отладку по USB в разделе Настройки > Для разработчиков.
Подключите устройство к компьютеру:
Подключите ваше Android-устройство к компьютеру с помощью USB-кабеля.
Создайте резервную копию данных устройства:
Используйте ADB для создания резервной копии данных вашего устройства:

```
adb backup -apk -shared -all -f backup.ab
```
Проверьте резервную копию с помощью MVT:
Распакуйте резервную копию с помощью android-backup-extractor:
```
java -jar /path/to/android-backup-extractor/abe.jar unpack backup.ab backup.tar

tar xvf backup.tar
```
Выполните проверку на наличие индикаторов компрометации (IOC) с помощью MVT:

```
./mvt-android check-backup --iocs /usr/local/share/mvt-iocs/pegasus.stix2 --output .
```
Анализируйте результаты:
После завершения проверки MVT создаст отчеты, в которых будут указаны возможные индикаторы компрометации. Обратите внимание на любые предупреждения и рекомендации.
Заключение
Используя Mobile Verification Toolkit (MVT), вы можете проверить свое Android-устройство на наличие шпионского ПО Pegasus и других угроз. 

### Indicators of Compromise

MVT supports using public [indicators of compromise (IOCs)](https://github.com/mvt-project/mvt-indicators) to scan mobile devices for potential traces of targeting or infection by known spyware campaigns. This includes IOCs published by [Amnesty International](https://github.com/AmnestyTech/investigations/) and other  research groups.

> **Warning**
> Public indicators of compromise are insufficient to determine that a device is "clean", and not targeted with a particular spyware tool. Reliance on public indicators alone can miss recent forensic traces and give a false sense of security.
>
> Reliable and comprehensive digital forensic support and triage requires access to non-public indicators, research and threat intelligence.
>
>Such support is available to civil society through [Amnesty International's Security Lab](https://securitylab.amnesty.org/get-help/?c=mvt_docs) or through our forensic partnership with [Access Now’s Digital Security Helpline](https://www.accessnow.org/help/).

More information about using indicators of compromise with MVT is available in the [documentation](https://docs.mvt.re/en/latest/iocs/).

## Installation

MVT can be installed from sources or from [PyPI](https://pypi.org/project/mvt/) (you will need some dependencies, check the [documentation](https://docs.mvt.re/en/latest/install/)):

```
pip3 install mvt
```

For alternative installation options and known issues, please refer to the [documentation](https://docs.mvt.re/en/latest/install/) as well as [GitHub Issues](https://github.com/mvt-project/mvt/issues).


## Usage

MVT provides two commands `mvt-ios` and `mvt-android`. [Check out the documentation to learn how to use them!](https://docs.mvt.re/)


## License

The purpose of MVT is to facilitate the ***consensual forensic analysis*** of devices of those who might be targets of sophisticated mobile spyware attacks, especially members of civil society and marginalized communities. We do not want MVT to enable privacy violations of non-consenting individuals.  In order to achieve this, MVT is released under its own license. [Read more here.](https://docs.mvt.re/en/latest/license/)
