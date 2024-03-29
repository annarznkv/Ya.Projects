# Проект "Прогнозирование заказов такси"


## Данные

Исторические данные о заказах такси в аэропортах.
Данные лежат в файле taxi.csv. Количество заказов находится в столбце num_orders (от англ. number of orders, «число заказов»).

## Задача

Чтобы привлекать больше водителей в период пиковой нагрузки, нужно спрогнозировать количество заказов такси на следующий час. 
Значение метрики RMSE на тестовой выборке должно быть не больше 48.

## Ход исследования

- Загрузили данные - в материале предоставлены только время и количество заказов.
- Агрегировали заказы по каждому часу, в качестве признаков выделили день недели, час заказа и др
- Посмотрели на данные в динамике - количество заказов по часам, в том числе скользящее среднее. Обнаружили восходящий тренд числа заказов с течением времени, нет сезонности в почасовых данных в течение полугода
- Подготовили выборки - обучающая составила 90% от всех данных (по условию задачи)
- Обучили и протестировали на обеих выборках несколько моделей - линейную регрессию, случайный лес, дерево решений и CatBoostRegressor
- Сравнили результат модели и целевой функции - они схожи


## Выводы

Лучший результат на тестовой выборке показала модель CatBoostRegressor с 139 итерациями: RMSE тестовой выборки CatBoostRegressor: 47.5 (целевое значение RMSE - 48)


## Используемые библиотеки
*pandas, numpy, sklearn, catboost, matplotlib, statsmodels*
