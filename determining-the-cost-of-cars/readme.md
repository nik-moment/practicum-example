# Определение стоимости автомобилей

Сервис по продаже автомобилей с пробегом разрабатывает приложение для привлечения новых клиентов. В нём можно быстро узнать рыночную стоимость своего автомобиля. В распоряжении исторические данные: технические характеристики, комплектации и цены автомобилей. Построим модель для определения стоимости.

Основные шаги

- Загрузка и чтение данных
- Обработка данных: заполнение пропущенных значений, обработка аномалий в столбцах, удаление неинформативных признаков
- Подготовка выборки для обучения моделей: азбивка данных на выборки, кодирование, масштабирование данных.
- Обучение нескольких моделей: линейная регрессия, LightGBM, CatBoost, использование разных гиперпараметров.
- Анализ времени обучения, времени предсказания и качества моделей (метрика RMSE).
- Опираясь на критерии заказчика, выбор лучшей модели, проверка её качества на тестовой выборке.

Заказчику важны:
- качество предсказания;
- скорость предсказания;
- время обучения.



## Итоги:

Качество модели:
- Линейная: регрессия: 2527.64
- LightGBM: 1609.23
- CatBoost: 1515.67

Время обучения моделей:
- Линейная: 18.7 s
- LightGBM: 6.18 s
- CatBoost: 8min 4s

Скорость предсказания:
- Линейная: 307 ms
- LightGBM: 1.89 s
- CatBoost: 3.98 s

Самая высокая скорость обучения и предсказания у линейно регрессии, при этом она имеет худший показатель метрики, который не соответствует необходимому условию. 
Из двух оставшихся моделей CatBoost имеет наилучший показатель метрики RMSE. Скорость предсказания достаточно высокая у обеих оставшихся моделей. Поскольку это два первостепенных критерия, выбор в пользу модели CatBoost.
