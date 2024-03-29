# Хэш-таблицы

Это абстрактный тип данных. Хэш-таблица дает 
возможность хранить данные *любого типа* и 
использует для этого связку **ключ-значение**.

**Хэширование** - это преобразование данных *любой* 
длины в данные *заданной* длины при помощи *хэш-функции* 
(не пустать с кешированием!).

Хэш-функция возвращет один и тоже *хэш* (*хэш-сумму*)
для одного и того же значения (*ключа*).

Чем больше значений в хеш-таблицу мы добавлем,
*тем больше вероятность* того, что соответствующая ей
хеш-функция для каких-либо двух значений (ключей) вернет 
одинаковый хэш - это называется *коллизией*.

Каждому значению в хеш-таблице ставится в
соответствие уникальный ключ. Его вероятность
быть уникальным будет уменьшаться с ростом числа
элементов в хэш-таблице. Число коллизий, возникаемых
с ростом размера хэш-таблицы, зависит от "качества"
хэш-функции. Также существуют методы борьбы с
коллизиями.
