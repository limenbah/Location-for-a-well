# Описание проекта

*Допустим, вы работаете в добывающей компании «ГлавРосГосНефть». Нужно решить, где бурить новую скважину.
Мне предоставлены пробы нефти в трёх регионах: в каждом 10 000 месторождений, где измерили качество нефти и объём её запасов. Постройте модель машинного обучения, которая поможет определить регион, где добыча принесёт наибольшую прибыль. Нужно Проанализировать возможную прибыль и риски техникой Bootstrap*

- 
*Шаги для выбора локации:*
- 
- В избранном регионе ищут месторождения, для каждого определяют значения признаков;
- Строят модель и оценивают объём запасов;
- Выбирают месторождения с самым высокими оценками значений. Количество месторождений зависит от бюджета компании и стоимости разработки одной скважины;
- Прибыль равна суммарной прибыли отобранных месторождений.


1. Загрузка и подготовка данных
2. Обучите и проверка модели для каждого региона:
    - Разбеение данных на обучающую и валидационную выборки в соотношении 75:25.
    - Обучение модели и предсказания на валидационной выборке.
    - Сохранение предсказания и правильных ответов на валидационной выборке.
    - Напечатать на экране средний запас предсказанного сырья и RMSE модели.
    - Проанализировать результаты.
3. Подготовка к расчёту прибыли:
    - Все ключевые значения для расчётов сохранить в отдельных переменных.
    - Рассчитать достаточный объём сырья для безубыточной разработки новой скважины. Сравнение полученного объёма сырья со средним запасом в каждом регионе.
    - Выводы по этапу подготовки расчёта прибыли.
4. Функция для расчёта прибыли по выбранным скважинам и предсказаниям модели:
    - Выберать скважины с максимальными значениями предсказаний.
    - Просуммировать целевое значение объёма сырья, соответствующее этим предсказаниям.
    - Рассчитать прибыль для полученного объёма сырья.
5. Посчитать риски и прибыль для каждого региона:
    - Применить технику Bootstrap с 1000 выборок, чтобы найти распределение прибыли.
    - Найти среднюю прибыль, 95%-й доверительный интервал и риск убытков. Убыток — это отрицательная прибыль.
    - Написать выводы: Регион для разработки скважин.

- `id` — уникальный идентификатор скважины;
- `f0`, `f1`, `f2` — три признака точек (неважно, что они означают, но сами признаки значимы);
- `product` — объём запасов в скважине (тыс. баррелей).

***Условия задачи:***
- Для обучения модели подходит только линейная регрессия (остальные — недостаточно предсказуемые).
- При разведке региона исследуют 500 точек, из которых с помощью машинного обучения выбирают 200 лучших для разработки.
- Бюджет на разработку скважин в регионе — 10 млрд рублей.
- При нынешних ценах один баррель сырья приносит 450 рублей дохода. Доход с каждой единицы продукта составляет 450 тыс. рублей, поскольку объём указан в тысячах баррелей.
- После оценки рисков нужно оставить лишь те регионы, в которых вероятность убытков меньше 2.5%. Среди них выбирают регион с наибольшей средней прибылью.
- Данные синтетические: детали контрактов и характеристики месторождений не разглашаются.
