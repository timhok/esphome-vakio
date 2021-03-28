# esphome-vakio
Подходит для моделей с ИК-пультом: Vakio Base, Vakio Window

# Железо
Я использовал клон wemos d1 mini на базе esp8266 и какой-то инфрокрасный светодиод от старого пульта:

[Фотография прототипа](https://github.com/timhok/esphome-vakio/blob/main/image.png)

Для конечного устройства настроятельно рекомендую использовать токоограничивающий резистор или вовсе питать светодиод с помощью транзистора (типа 2N2222)

# Конфиг
Исправьте `pin_led_ir` в конфиге на тот пин который используется в вашем варианте.

Не забудьте задать секретные переменные `wifi_ssid`, `wifi_password`, `esphome_password`

# Самое главное
Не нравится мой вариант? Сделай свой!

Вот таблица наименований, названий, ir кодов и иконок, использованных в этом проекте:

name | id | ir_code | icon
--- | --- | --- | ---
Increase speed | speed_inc | 0x00FFA05F | fan-plus
Decrease speed | speed_dec | 0x00FF906F | fan-minus
Power | power | 0x00FF00FF | power
Intake mode | mode_in | 0x00FF30CF | home-import-outline
Exhaust mode | mode_out | 0x00FF708F | home-export-outline
Recuperation mode | mode_recuperation | 0x00FFB04F | rotate-3d-variant
Winter mode | mode_winter | 0x00FF807F | snowflake
Night mode | mode_night | 0x00FF40BF | weather-night

IR-коды в формате [`transmit_lg`](https://esphome.io/components/remote_transmitter.html#remote-transmitter-transmit-lg-action) c `nbits: 32`
