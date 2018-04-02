# ArMax Pay Widget
Виджет платежной формы для встраивания в веб-страницу.

## Поддержка
Вопросы по работе и поддерже **сервисов ArMax** можно задать по адресу [support@armax.ru](mailto:support@armax.ru)
Вопросы по настройке, работе и установке платежного виджета можно задать в [Issues](https://github.com/armax-ru/pay-widget-meta/issues) данного репозитория.

## Содержание
* [Настройка веб-терминала](#web-term-setup)
* [Интеграция в веб-страницу](#web-setup)
  * [Простая установка](#simple-setup)
  * [Ручная инициализация](#manual-setup)

## Установка
Для установки необоходимо [создать и/или настроить](/web-term-setup.md) терминал типа **"Web Term 2"** и подключить JS файл для отображения виджета.

### [Настройка веб-терминала](#web-term-setup)
1. В кабинете агента ArMax создать терминал типа **"Web Term 2"**.
2. Настроить профили отоборажения и комиссии.
3. Установить параметры для платежных систем

### [Интеграция в веб-страницу](#web-setup)
Установить виджет на веб-страницу можно двумя способами - простой вставкой HTML кода или ручной инициализацией виджета.

#### [Простая установка](#simple-setup)
Разместите данный код в нужном месте HTML страницы:
```html
<script
  data-terminal-id="00000"
  type="text/javascript"
  src="https://payframe.armax.ru/widget/armax-pay-widget-loader.min.js" async>
</script>
```
У созданного веб-терминала из пункта [Настройка веб-терминала](#web-term-setup) определите ID терминала (колонка ID в общем списке терминалов или поле "Серийный номер" в настройках конкретного терминала).

Замените `00000` в значении аттрибута `data-terminal-id` на ID терминала.

Пример автоматической установки в [examples/auto-setup.html](/examples/auto-setup.html)

#### [Ручная инициализация](#manual-setup)

Для инициализации виджета на странице необходимо подключить npm-пакет [`@armax-ru/pay-widget`](https://github.com/armax-ru/pay-widget) и вызвать функцию-конструктор `ArmaxPayWidget`:

```js
new ArmaxPayWidget ({
  container: document.getElementById('pay-widget-container'),
  terminalId: 00000
});
```
Пример ручной инциализации виджета в [examples/manual-setup.html](/examples/manual-setup.html)
Более подробную информацию по использованию этого метода можно найти в репозитории npm-пакета [`@armax-ru/pay-widget`](https://github.com/armax-ru/pay-widget)
