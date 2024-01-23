# Разработка системы для автоматической фильтрации и классификации спама в электронной почте с применением нейронных сетей. (Лабораторная №3)
В данной работе рассмотрим процесс разработки системы для автоматической фильтрации и классификации спама в электронной почте с использованием нейронных сетей. Будем использовать язык программирования Python и несколько библиотек, таких как nltk, matplotlib, wordcloud, pandas и numpy.

## Требования.
- Python 3.x
- Google Colab или Jupyter Notebook.

## Как работает программа :
1. **Загрузка данных**:
   * Подключаем все необходимые библиотеки.
   * Загружаем файл "spam.csv". Это будет набор данных, который содержит электронные сообщения, размеченные на "ham" (не спам) и "spam" (спам).
   * Файл прикреплен к работе.
    
2. **Предобработка данных**:
   * Удалим лишние столбцы и переименуем оставшиеся, чтобы сделать данные более удобными для работы.

3. **Визуализация данных**:
   * Для лучшего понимания содержания наших данных визуализируем слова, которые чаще встречаются в спам-сообщениях и "хороших" сообщениях.
   * В этом нам помогут "облако слов".

4. **Разделение данных на обучающий и тестовый наборы**:
   * Данные для обучения отправляются в trainData, а для тестов - в testData.

5. **Разработка модели классификации спама**:
   * Делим текст на отдельные слова или токены, уменьшаем регистр всех слов и приводим их к основной форме.
   * Исключаем часто встречающихся слов, которые не несут смысла для классификации.
   * Используем уже разделённые данные. Обучающий набор будет использоваться для обучения модели, а тестовый набор - для оценки ее производительности.
   * Создаем объект SpamClassifier с использованием обучающего набора данных и метода классификации 'tf-idf'.
   * Происходит прогнозирование на тестовом наборе, а затем оценка результатов с использованием метрик, таких как точность, полнота, F-мера и др.

6. **Оценка результатов**:
   Пишем текст и проверяем, отправится ли он в спам.

6. **Как работает классификация внутри нейросети**:
   * Внутри классификатора на основе TF-IDF, нейронная сеть (в данном случае неявно представленная структурой, включающей LSTM слои) обучается на векторах TF-IDF для каждого сообщения.
   * Эти векторы представляют собой числовое представление каждого сообщения, учитывая важность каждого термина.
   * Модель обучается с использованием задачи бинарной классификации (спам или не спам), и в конечном итоге, после обучения, она может классифицировать новые сообщения как спам или нет, основываясь на их числовом представлении.
  
## Colab
| Colab                                                                                                                                                                          | Info               |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------ |
| [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1zuvhCyRR9tnYGmaxyvjyutYbp0qrTmVz#scrollTo=yI2WJ_A88D1-) | Laba3 |

## Результат.
1. **Веса.**
   
   ![xxxx](https://sun9-15.userapi.com/impg/GuDkdtCgj_0vGzFffmMLGyj7ywvyh09oE3TO4g/8sJvUvt68mQ.jpg?size=282x764&quality=96&sign=8a56d8e35fc07f52556ab10cc0bcabbd&type=album)
  * После завершения обучения модели мы получаем количество весов, равное количеству эпох.
  * Ранние веса не имеют смысла, поэтому прикрепляю только лучшие (с 24 и 25 эпох)

2. **Результат 24 веса.**
    
   ![xxxx](https://sun9-6.userapi.com/impg/Gjs8rGkTwnbtmG8YlVi9Yx5Ph-wUTtD_qvjqzg/24pTIn4yX9k.jpg?size=838x559&quality=96&sign=72b558846ce7c5cd95b6c47ac4edfebe&type=album)
   
3. **Несколько результатов 25 веса.**
   ![xxxx](https://sun9-65.userapi.com/impg/MIxhKk5DiRq5PVG2b5FaI3tFjAkXd72xWNbiUQ/_iFQDmSeyTc.jpg?size=1120x537&quality=96&sign=e43290fab8b08c59666c87dfe648d8c8&type=album)
   ![xxxx](https://sun9-34.userapi.com/impg/65BA1Cyy5kvHYnaVH68ZAKeCU3IU984HS4byOw/Xa6jlLxsAGs.jpg?size=1236x531&quality=96&sign=95e32d5e42b8349e8cc498e671663347&type=album)
