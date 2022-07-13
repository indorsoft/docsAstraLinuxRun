# Установка продуктов ИндорСофт <br/>в ASTRA LINUX

Шаги:

- [Установка ASTRA LINUX](#установка-astra-linux)
- [Установка IndorTrafficPlan](#установка-indortrafficplan)

Дополнения:

- [Полезные ссылки](#поезные-ссылки)


## Установка ASTRA LINUX

Скачиваем ISO-образ с операционной системой ASTRA LINUX
```url
https://mirror.yandex.ru/astra/stable/orel/iso/
```

Устанавливаем любым известным образом: на компьютер через [USB-загрузочную флешку]((https://remontka.pro/zagruzochnaya-fleshka-iz-obraza/)) или в виртуальную машину ([VirtualBox](https://www.virtualbox.org/), [VMWare](https://www.vmware.com/ru/products/workstation-player.html) и др.).

Следуем инструкциям на экране в процессе установки.

![Установка ASTRA LINUX](/img/00-install.png)

> В момент написания руководства был использован Intel-совместимый компютер. Установка производилась в виртуальную машину. Характеристики виртуальной машины: 4 ядра ЦПУ, 4 ГБ ОЗУ, 64 ГБ диск.
> Было выбрано ядро устновки linux-5.1-generic.

В итоге получим рабочий стол ОС:

![Рабочий стол ASTRA LINUX](/img/01-astra-desktop.png)

## Предварительная настройка ОС

Запустите терминал. Для этого необходимо на клавиатуре нажать кнопку стартового меню или на экране внизу слева звёздочку. Начать набирать «тер», что приведёт с сокращению вариантов выбора и можно будет быстро указать «Терминал Fly».

![Запуск терминала](/img/02-start-terminal.png)

Далее в терминале запустите обновление системы:

```sh
$ sudo apt update
$ sudo apt upgrade -y
```

Добавим слой совместимости для Windows-приложений [WINE](https://wiki.debian.org/Wine):

```sh
$ sudo apt install wine -y
```

Получим примерно такоую картину:

![После установки Wine](/img/03-install-wine.png)


## Установка IndorTrafficPlan

Запустим веб-браузер и скачаем с сайта ИндорСофт дистрибутив программы IndorTrafficPlan:

![Сайт ИндорСофт](/img/04-indorsoft-site.png)

Переходим в «Загрузка» — «[Дистрибутивы](https://www.indorsoft.ru/download/distribs/)»:

![Загрузка дистрибутивов ИндорСофт](/img/05-indorsoft-download.png)

Скачиваем дистрибутив IndorTrafficPlan.

![Скачиваем дистрибутив IndorTrafficPlan](/img/06-download-traffic.png)

> Скорее всего дистрибутив будет скачан в папку <nobr>/home/*<_пользователь_>*/Загрузки/</nobr>

В окне терминала выполните следующие команды:

```sh
$ cd ~/Загрузки
$ ls
```

Должен появится список загруженных файлов:

![Дистрибутив IndorTrafficPlan](/img/07-downloaded-msi.png)

Запускаем на установку дистрибутив:

```sh
$ msiexec /i IndorTrafficPlan-2022.6757-Win64.msi
```

![Установка IndorTrafficPlan](/img/08-install-traffic.png)

Далее следуем инструкциям установщика.

После установки сверните все окна. На рабочем столе будет ярлык программы IndorTrafficPlan. **НЕ запускайте**.

![Ярлык IndorTrafficPlan](/img/09-link-traffic.png)

Правой кнопкой мыши на ярлыке вызываем «Свойства».
Во вкладке «Ярлык» меняем поле «Команда» на:

```sh
wine "C:/Program Files/IndorSoft/9.0/Bin/IndorTrafficPlan.exe"
```

![Меняем ярлык IndorTrafficPlan](/img/10-link-change.png)

Сохраняем изменения. Дважды победно щёлкаем на ярлык!

![Запускаем IndorTrafficPlan](/img/11-traffic.png)

По всем дальнейшим возникающим вопросам предлагаем такой порядок действий:

- Поиск ответа в документации на программный продукт
- Поиск ответа в форуме и на [сайте ИндорСофт](www.indorsoft.ru)
- Написать электронное письмо в техническую поддержку <support@indorsoft.ru>


## Поезные ссылки

* [Сайт ОС ASTRA LINUX](https://astralinux.ru/)
* [Дистрибутив ОС ASTRA LINUX](https://mirror.yandex.ru/astra/stable/orel/iso/)
* [Справочный центра ASTRA LINUX](https://wiki.astralinux.ru/)
* [Руководство администратора ASTRA LINUX](https://astralinux.ru/products/astra-linux-special-edition/relizyi/smolensk/dokumentacziya/rukovodstvo-administratora-chast-1-astra-se.pdf)
* [Шрифты с бесплатной лицензией от ПараТайп](https://www.paratype.ru/catalog?freefonts=true&sortType=bestsellers)
* [Создать загрузочную флешку из образа ISO](https://remontka.pro/zagruzochnaya-fleshka-iz-obraza/)

> Вот интересно, почему название внедорожника PATRIOT по латыни?