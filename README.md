# Анализ резюме на сайте hh.ru

## Цель проекта 
Подготовить данные для обучения модели, прогнозирующей примерную заработную плату у соискателей.

## Исходные данные
[Датасет с резюме](https://drive.google.com/file/d/1FFPxcyD781KVrYlNolTe72zHqeIOxrHm/view?usp=share_link)
[Данные с курсами валют](https://drive.google.com/file/d/1ywXEmtCDRA7_EK67DqUcHh7PCC5znDCd/view?usp=share_link)


## Этапы проекта
1. Базовый анализ структуры данных
2. Преобразование данных
3. Разведывательный анализ
4. Очистка данных

## Описание проекта
После проведения анализа данных, обнаружено, что датасет состоит  из 44744 строк и 12 столбцов и представлен категориальным типом данных, присутствуют пропуски  данных. Признаки представлены в неудобном для анализа и очистки формате, поэтому необходимо произвести преобразование данные.
Преобразование данных произведено на следующих признаках:«Образование и ВУЗ», «Пол, возраст», «Опыт работы», «Город, переезд, командировки», «Занятость», «График», «ЗП». На основе признака "ЗП" был создан новый признак "ЗП(руб.)", который отражает указанную заработную плату в рублях, переведенную по курсу даты обновления резюме на основе данных с сайта [MDF.ru] (https://clck.ru/33gEQz). В итоге преобразования данных мы получили датасет, состоящий из 23 признаков, 12 из которых - bool, 8 - object, 1 - int32, и 2 - float64.
Далее приступаем  к разведывательныму анализу (EDA), он предназначен для выявления связей между признаками, выявления закономерностей, определения распределений признаков, поиска аномалий и других дефектов данных. В результате в датасете найдены аномалии в признаках "Возраст", "Опыт работы" и "ЗП (руб.)",  а также обнаружены зависимость медианной заработной платы соискателей от образования, возраста и города проживания.
Датасет был очищен от 161 дубликатов записей. Для очистки данных от выбросов использовался метод z-отклонений для признака "Возраст". Пропуски в признаке "Опыт" были заполнены медианным значением.


## Использованные инструменты и библиотеки
* numpy (1.23.5)
* pandas (1.5.2)
* plotly (5.13.0)
* seaborn (0.12.1)



