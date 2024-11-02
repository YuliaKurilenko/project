Этот проект предназначен для загрузки исторических данных об акциях и их визуализации. Он использует библиотеку yfinance для получения данных и matplotlib для создания графиков. Пользователи могут выбирать различные тикеры и временные периоды для анализа, а также просматривать движение цен и скользящие средние на графике.

Структура и модули проекта

1. data_download.py:

- Отвечает за загрузку данных об акциях.

- Содержит функции для извлечения данных об акциях из интернета и расчёта скользящего среднего.



2. main.py:

- Является точкой входа в программу.

- Запрашивает у пользователя тикер акции и временной период, загружает данные, обрабатывает их и выводит результаты в виде графика.



3. data_plotting.py:

- Отвечает за визуализацию данных.

- Содержит функции для создания и сохранения графиков цен закрытия и скользящих средних.



Описание функций



1. data_download.py:

- fetch_stock_data(ticker, period): Получает исторические данные об акциях для указанного тикера и временного периода. Возвращает DataFrame с данными.

- add_moving_average(data, window_size): Добавляет в DataFrame колонку со скользящим средним, рассчитанным на основе цен закрытия.

- calculate_and_display_average_price(data): Рассчитывает среднюю цену закрытия акций за заданный период.

- notify_if_strong_fluctuations(data, threshold=20): Анализирует данные и уведомляет пользователя, если цена акций колебалась более чем на заданный процент за период.

- calculate_rsi(data, window=14): Рассчитывает индекс относительной силы (RSI) для данных о ценах акций.

- calculate_macd(data, short_window=12, long_window=26, signal_window=9):  Рассчитывает Moving Average Convergence Divergence (MACD) для данных о ценах акций.


2. main.py:

- main(): Основная функция, управляющая процессом загрузки, обработки данных и их визуализации. 
Запрашивает у пользователя ввод данных, вызывает функции загрузки и обработки данных, а затем передаёт результаты на визуализацию.



3. data_plotting.py:

- create_and_save_plot(data, ticker, period, filename): Создаёт график, отображающий цены закрытия и скользящие средние. Предоставляет возможность сохранения графика в файл. Параметр filename опционален; если он не указан, имя файла генерируется автоматически.
- export_data_to_csv(data, filename): Cоздает csv файл с таблицей по запрошенной акции и периоду. имя файла состоитт из названия акции и временного отрезка


Пошаговое использование

1. Запустить main.py.

2. Введите интересующий вас тикер акции (например, 'AAPL' для Apple Inc).

3. Введите желаемый временной период для анализа (например, '1mo' для данных за один месяц).

4. Введите порог колебания акций относительно стредней цены закрытия в процентах

5. Программа обработает введённые данные, загрузит соответствующие данные об акциях, рассчитает скользящее среднее, отобразит график и выведет среднюю цену закрытия акций в консоль
