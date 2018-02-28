# PyVybory

Библиотека для парсинга данных из системы "ГАС выборы"
Пока полностью реализованы только президентские выборы.



### Небольшая справка по выборам
>Первоначальный подсчет голосов осуществляют участковые избирательные комиссии, которые направляют протоколы о результатах подсчета в территориальные избирательные комиссии. Территориальные избирательные комиссии после предварительной проверки правильности составления протоколов участковых комиссий, составляют протоколы об итогах голосования на соответствующей территории и направляют их в избирательные комиссии субъектов РФ, которые в свою очередь после их проверки составляют протоколы об итогах голосования на территории субъектов, и направляют их в Центральную избирательную комиссию.

### Использование
```python
    from pyvybory.pyvybory import PresidentElections
    
    #создаем объект президенских выборов соответсвующего года
    elections = PresidentElections(2012)
    
    Получаем объект итоговых результатов
    final_results = elections.get_final_results()
    
    #получаем данные по субъектам
    regions = final_results.get_regions()
    
    #выводим первый регион
    print(region[0])
    
    #получаем данные всех ТИКов 1-ого субъекта
    tiks = final_results.get_tiks_by_region_url(region[0]['url'])
    
    #выводим данные первого ТИКа первого субъекта
    print(tiks[0])
    
    #получаем данные всех УИКов 1-ого ТИКа
    uiks = final_results.get_uiks_by_tik_url(tiks[0]['url'])
    
    #выводим данные первого УИКАа первого ТИКа первого субъекта
    print(uiks[0])
```
