# pandas

Основные компоненты:

1. **Series** - столбец (вектор)
2. **DataFrame** - многомерная матрица, состоящая из набора Series

Строки имеют индекс. Они могут индексироваться значениями разных типов.

`df = pd.read_csv('purchases.csv', index_col=0)`

`movies_df = pd.read_csv("IMDB-Movie-Data.csv", index_col="Title")`


## Базовые функции для вывода строк и получении данных из матрицы

Вывести `n` строк с начала или конца:

`df.head(n)`

`df.tail(n)`

Кол-во строк и столбцов:

`df.shape`

Вывести имена всех столбцов:

`df.columns`


## Извлечение столбцов (части матрицы)

`new_series = df["column1_name"]`

Чтобы получить именно `DataFrame`, необходимо передать *список* имен столбцов:

`new_df = df[["column1_name"]]`

`new_df = df[["column1_name", "column2_name"]]`


## Выборка по условиям

Вернет `Series` из значений `True` или `False` по каждому индексу:

`condition = (movies_df["director"] == "Ridley Scott")`

Фильтрация матрицы. Получим новый `DataFrame`, останутся только те строки, для которых в `condition` установлено значение `True`:

`filtered_df = movies_df[movies_df["director"] == "Ridley Scott"]` 

Можно использовать логические операторы `|` и `&`. Использование скобок обязательно.

`filtered_df = movies_df[(movies_df["director"] == "Christopher Nolan") | (movies_df["director"] == "Ridley Scott")]`

Более краткая запись:

`filtered_df = movies_df[movies_df["director"].isin(["Christopher Nolan", "Ridley Scott"])]`


## Применение функций

Применение функции к каждому элементу столбца (`Series`). Записываем результат в новый столбец `rating_category` исходного `DataFrame`.

`movies_df["rating_category"] = movies_df["rating"].apply(lambda x: "good" if x >= 8.0 else "bad")`
