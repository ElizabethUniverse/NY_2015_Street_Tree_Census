# NY_2015_Street_Tree_Census
Для решения нашей задачи была выбрана нейронная сеть с архитектурой Multilayer Perceptron, поскольку она довольно проста и хорошо подходит для решения задач классификации, в особенности многоклассовой, как в нашем случае. Также она хорошо себя показывает при работе с табличными данными.

Было выбрано 3 слоя, поскольку задача несложная и большее количество слоев могло бы привести к переобучению. Первый слой состоит из 256 нейронов и учитывает базовые признаки в данных. Второй слой содержит 128 нейронов и позволяет учитывать более сложные комбинации признаков. Последний - 3 слой на выходе дает 3 класса, поскольку у нас 3 класса.

Для данной задачи были выбраны learning rate = 0.0001 и также был использован lr_scheduler, такой начальный lr был выбран путем экспериментов и показал наиболее плавный процесс обучения.

Weight decay был выбран равным 0.00001, для борьбы с переобучением. Также был добавлен dropout = 0.3 для первого слоя и 0.2 для второго.

Количество шагов тренировки было выбрано равным 100, поскольку у нас довольно маленький learning rate это позволяет модели не сильно переобучиться, но при этом выявить более точные зависимости при дисбалансе классов.

Также для решения проблемы с дисбалансом классов была выбрана вместо классической функции потерь - взвешенная функция потерь(кросс-энтропия).
