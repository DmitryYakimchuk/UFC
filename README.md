# Межгалактический хакатон 2022

[UFC](https://user-images.githubusercontent.com/76701877/169634479-fac0d992-394d-4d43-9639-ec98bd71619f.png)

Вашему вниманию представлен проект в рамках которого была решена задача по предсказанию победителя бойца UFC в рамках межгалактического хакатона 2022.

### Команда:   
Якимчук Дмитрий   
Жданович Владислав   
Конышева Татьяна   
Любочко Александр   
Кукунов Андрей   
Крупень Сергей   

### Цель проекта:
на основе исторических статистических данных о боях лиги UFC создать модель, предсказывающую победителя. <br>
Для создания рабочей модели, благодаря которой можно будет делать успешные букмекерские ставки, необходимо решить следующие задачи:
1) Изучить имеющиеся данные;
2) Предварительно обработать разные датасеты;
3) Построить статистические данные для бойцов;
4) Объединить обработанные данные в один датасет;
5) Построить кумулятивные признаки;
6) Заполнить пропуски;
7) Апробировать различные модели машинного обучения;
8) Подобрать наилучшие параметры для моделей машинного обучения;
9) Выбрать наилучшую модель машинного обучения;
10) Сделать выводы по проекту.

### Предобработка данных
По результатам предобработки добавлены следующие данные:
* данные о каждом бойце (рост, вес,, ранг, год рождения, количество побед)
* расчитаны статистики (простая статистика, кумулятивная статистика, а также подключены данные в те бои, где у бойцов не было предыдущих боев)
* устранены пропуска

### Машинное обучение
В ходе работы над проектом были апробированы следующие модели машинного обучения:    
* RandomForestClassifier    
* GradientBoostingClassifier    
* CatBoostClassifier    
* CatBoost CV

Наилучшей моделью для решения данной задачи оказался CatBoost c accuracy=0.72. <br>
Параметры модели:
- Кросс-валидация на 10 под-выборках
- Построение по принцами TimeSeries
- Автоматическая балансировка классов
- Без отбора самых значимых признаков 

# Выводы:
Разработаны 2 нотбука:
1) UFC_Data_preprocessing.ipynb - подготовка данных к анализу и создание train и valid данных. 
2) UFC_Models_AK.ipynb - эксприменты с моделями
3) train_combined_2.csv - датасет для тренировок 
4) valid_combined_2.csv - датасет для валидации

Таким образом, на основе исторических статистических данных о боях лиги UFC разработана модель, предсказывающая исход боя с достоверностью результатов выше бейзлайна и метрикой accuracy = 0.72. Наиболее значимыми признаками для модели являются "успешные акцентированные удара", а также "акцентированные позиционные удары, выраженные в процентах"








