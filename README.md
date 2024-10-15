# lsimon

На сервере с контроллерами LSI устанавливаем утилиту storcli.

Далее настраиваем агента:

1. `git clone https://github.com/d1sl1ke/lsimon.git`
2. `cd lsimon`
3. `sh install.sh`
4. Импортируем шаблон zbx_lsi_json_lld.xml.

В макросах шаблона можно отредактировать периодичность опроса данных:

    - {$ADAP_DISCOVERY_PERIOD} — 1h. Периодичность автообнаружения контроллеров.
    - {$ADAP_HISTORY_PERIOD} — 30d. Срок хранения истории контроллеров.
    - {$ADAP_REQUEST_PERIOD} — 10m. Периодичность опроса контроллеров, кэша, батареек.
    - {$ADAP_THROTTLING_HB_PERIOD} — 3h. Срок тротлинга контроллера.
    - {$ADAP_TREND_PERIOD} — 180d. Срок хранения трендов контроллера.
    - {$BATTERY_HISTORY_PERIOD} — 30d. Срок хранения истории батареек и кэша.
    - {$BATTERY_REQUEST_PERIOD} — 10m. Периодичность опроса батареек и кэша.
    - {$BATTERY_TREND_PERIOD} — 180d. Срок хранения трендов батареек и кэша.
    - {$INTERNAL_ITEMS_HISTORY_PERIOD} — 30d. Срок хранения истории JSON логических и физических дисков.
    - {$LD_DISCOVERY_PERIOD} — 10m. Периодичность автообнаружения и опроса логических дисков.
    - {$LD_HISTORY_PERIOD} — 30d. Срок хранения истории логических дисков.
    - {$LD_REQUEST_PERIOD} — 10m. Периодичность опроса JSON логических дисков. Для просмотра всех параметров, которых нет в элементах данных.
    - {$LD_THROTTLING_HB_PERIOD} — 3h. Срок тротлинга логических дисков.
    - {$PD_DISCOVERY_PERIOD} — 10m. Периодичность автообнаружения и опроса физических дисков.
    - {$PD_HISTORY_PERIOD} — 30d. Срок хранения истории физических дисков.
    - {$PD_REQUEST_PERIOD} — 10m. Периодичность опроса JSON физических дисков. Для просмотра всех параметров, которых нет в элементах данных.
    - {$PD_THROTTLING_HB_PERIOD} — 3h. Срок тротлинга физических дисков.
    - {$PD_TREND_PERIOD} — 180d. Срок хранения трендов физических дисков.
  
А также настроить граничные значения температур в градусах Цельсия:

    - {$ADAP_CACHE_TEMP_CRIT} — 55. Критическая температура кэша.
    - {$ADAP_CACHE_TEMP_AVERAGE} — 45. Высокая температура кэша.
    - {$ADAP_CACHE_TEMP_WARNING} — 40. Повышенная температура кэша.
    - {$ADAP_ROC_TEMP_CRIT}  — 90. Критическая температура чипа.
    - {$ADAP_ROC_TEMP_AVERAGE} — 80. Высокая температура чипа.
    - {$ADAP_ROC_TEMP_WARNING} — 70. Повышенная температура чипа.
    - {$PD_TEMP_CRIT} — 55. Критическая температура физического диска.
    - {$PD_TEMP_AVERAGE} — 50. Высокая температура физического диска.
    - {$PD_TEMP_WARNING} — 45. Повышенная температура физического диска.