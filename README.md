# M28.HW.Future_async.Merge_sort
О программе

Программа представляет собой многопоточный алгоритм merge sort.

• В качестве инструмента для синхронизации результата работы потоков использован класс std::future.

• Определены независимые части алгоритма, которые могут быть распараллелены; их вычисления запущены в отдельных потоках.

• Потоки запущены через std::async, синхронизация через std::future. 

• Также предусмотрено ограничение количества запускаемых потоков:

    -  Количество одновременно выполняемых потоков не долно превышать количество доступных ядер процессора
       (т.к. начинается конкуренция за ресурсы, что приводит к снижению производительности программы в целом; 
       + создание слишком большого количества потоков может привести к проблемам с управлением памятью).
       
    -  Количество элементов сортируемой части должно быть больше чем 10000.
    

Для примера использован массив случайных целых чисел размером 10 000 000.
