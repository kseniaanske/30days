# Day 24

# **st.cache**

`st.cache` allows you to optimize the performance of your Streamlit app.

Streamlit provides a caching mechanism that allows your app to stay performant even when loading data from the web, manipulating large datasets, or performing expensive computations. This is done with the `@st.cache` decorator.

When you mark a function with the @st.cache decorator, it tells Streamlit that whenever the function is called it needs to check a few things:

1. The input parameters that you called the function with
2. The value of any external variable used in the function
3. The body of the function
4. The body of any function used inside the cached function

If this is the first time Streamlit has seen these four components with these exact values and in this exact combination and order, it runs the function and stores the result in a local cache. Then, next time the cached function is called, if none of these components changed, Streamlit will just skip executing the function altogether and, instead, return the output previously stored in the cache.

The way Streamlit keeps track of changes in these components is through hashing. Think of the cache as an in-memory key-value store, where the key is a hash of all of the above and the value is the actual output object passed by reference.

Finally, `@st.cache` supports arguments to configure the cache's behavior. You can find more information on those in our API reference.

## **How to use?**

You can simply add `st.cache` decorator on the preceding line of a custom function that you define in your Streamlit app. See the example below.

## **Demo app**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Code**

Here's how to use `st.cache`:

`import streamlit as st
import numpy as np
import pandas as pd
from time import time

st.title('st.cache')

# Using cache
a0 = time()
st.subheader('Using st.cache')

@st.cache(suppress_st_warning=True)
def load_data_a():
  df = pd.DataFrame(
    np.random.rand(2000000, 5),
    columns=['a', 'b', 'c', 'd', 'e']
  )
  return df

st.write(load_data_a())
a1 = time()
st.info(a1-a0)

# Not using cache
b0 = time()
st.subheader('Not using st.cache')

def load_data_b():
  df = pd.DataFrame(
    np.random.rand(2000000, 5),
    columns=['a', 'b', 'c', 'd', 'e']
  )
  return df

st.write(load_data_b())
b1 = time()
st.info(b1-b0)`

## **Line-by-line explanation**

The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` as well as other libraries used in the app like so:

`import streamlit as st
import numpy as np
import pandas as pd
from time import time`

This is followed by creating a title text for the app:

`st.title('Streamlit Cache')`

Next, we'll define 2 custom functions for generating a large DataFrame where the first one makes use of the `st.cache` decorator while the second does not:

`@st.cache(suppress_st_warning=True)
def load_data_a():
  df = pd.DataFrame(
    np.random.rand(1000000, 5),
    columns=['a', 'b', 'c', 'd', 'e']
  )
  return df

def load_data_b():
  df = pd.DataFrame(
    np.random.rand(1000000, 5),
    columns=['a', 'b', 'c', 'd', 'e']
  )
  return df`

Finally, we run the custom function while also timing the run time using the `time()` command.

`# Using cache
a0 = time()
st.subheader('Using st.cache')

# We insert the load_data_a function here

st.write(load_data_a())
a1 = time()
st.info(a1-a0)

# Not using cache
b0 = time()
st.subheader('Not using st.cache')

# We insert the load_data_b function here

st.write(load_data_b())
b1 = time()
st.info(b1-b0)`

Notice how the first run may provide roughly similar run time. Reload the app and notice how the run time changes when using the `st.cache` decorator. Did you observe any speed increase?

## **Further reading**

- `[st.cache` API Documentation](https://docs.streamlit.io/library/api-reference/performance/st.cache)
- [Optimize performance with `st.cache`](https://docs.streamlit.io/library/advanced-features/caching)
- [Experimental cache primitives](https://docs.streamlit.io/library/advanced-features/experimental-cache-primitives)
- `[st.experimental_memo](https://docs.streamlit.io/library/api-reference/performance/st.experimental_memo)`
- `[st.experimental_singleton](https://docs.streamlit.io/library/api-reference/performance/st.experimental_singleton)`

# **st.cache**

`st.cache` позволяет оптимизировать производительность вашего приложения Streamlit.

Streamlit предоставляет механизм кэширования, который позволяет вашему приложению оставаться производительным даже при загрузке данных из Интернета, манипулировании большими наборами данных или выполнении дорогостоящих вычислений. Это делается с помощью декоратора `@st.cache`.

Когда вы помечаете функцию декоратором `@st.cache`, он сообщает Streamlit что при каждом вызове функции необходимо проверить несколько вещей:

1. Входные параметры, с которыми вы вызывали функцию
2. Значение любой внешней переменной, используемой в функции
3. Тело функции
4. Тело любой функции, используемой внутри кэшированной функции.

Если Streamlit впервые видит эти четыре компонента с такими точными значениями, именно в такой комбинации и порядке, он запускает функцию и сохраняет результат в локальном кэше. Затем при следующем вызове кэшированной функции, если ни один из этих компонентов не изменился, Streamlit просто пропустит выполнение функции и вместо этого вернет результат, ранее сохраненный в кэше.

Streamlit отслеживает изменения в этих компонентах с помощью кеширования. Думайте о кеше как о хранилище ключей и значений в памяти, где ключ представляет собой кэш всего вышеперечисленного, а значение — это фактический выходной объект, переданный по ссылке.

Наконец, `@st.cache` поддерживает аргументы для настройки поведения кэша. Дополнительную информацию о них можно найти в нашем справочнике по API.

## **Как использовать?**

Вы можете просто добавить декоратор `st.cache` в предыдущую строку пользовательской функции, которую вы определяете в своем приложении Streamlit. См. пример ниже.

## **Демонстрационное приложение**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Как использовать `st.cache`:

`import streamlit as st
import numpy as np
import pandas as pd
from time import time

st.title('st.cache')

# Using cache
a0 = time()
st.subheader('Using st.cache')

@st.cache(suppress_st_warning=True)
def load_data_a():
  df = pd.DataFrame(
    np.random.rand(2000000, 5),
    columns=['a', 'b', 'c', 'd', 'e']
  )
  return df

st.write(load_data_a())
a1 = time()
st.info(a1-a0)

# Not using cache
b0 = time()
st.subheader('Not using st.cache')

def load_data_b():
  df = pd.DataFrame(
    np.random.rand(2000000, 5),
    columns=['a', 'b', 'c', 'd', 'e']
  )
  return df

st.write(load_data_b())
b1 = time()
st.info(b1-b0)`

## **Построчное объяснение**

Самое первое, что нужно сделать при создании приложения Streamlit, это импортировать библиотеку `streamlit` как `st`, а также других библиотек используемых в приложении, следующим образом:

`import streamlit as st
import numpy as np
import pandas as pd
from time import time`

Затем следует создание текста заголовка для приложения:

`st.title('Streamlit Cache')`

Далее мы определим две пользовательские функции для создания большого DataFrame, где первая использует декоратор `st.cache`, а вторая нет:

`@st.cache(suppress_st_warning=True)
def load_data_a():
  df = pd.DataFrame(
    np.random.rand(1000000, 5),
    columns=['a', 'b', 'c', 'd', 'e']
  )
  return df

def load_data_b():
  df = pd.DataFrame(
    np.random.rand(1000000, 5),
    columns=['a', 'b', 'c', 'd', 'e']
  )
  return df`

Наконец, мы запускаем пользовательскую функцию, а также измеряем время выполнения с помощью команды `time()`.

`# Using cache
a0 = time()
st.subheader('Using st.cache')

# We insert the load_data_a function here

st.write(load_data_a())
a1 = time()
st.info(a1-a0)

# Not using cache
b0 = time()
st.subheader('Not using st.cache')

# We insert the load_data_b function here

st.write(load_data_b())
b1 = time()
st.info(b1-b0)`

Обратите внимание, что первый запуск может обеспечить примерно одинаковое время выполнения. Перезагрузите приложение и обратите внимание на изменение времени выполнения при использовании декоратора `st.cache`. Вы не заметили увеличения скорости?

## **Дальнейшее чтение**

- `[st.cache` API Documentation](https://docs.streamlit.io/library/api-reference/performance/st.cache)
- [Optimize performance with `st.cache`](https://docs.streamlit.io/library/advanced-features/caching)
- [Experimental cache primitives](https://docs.streamlit.io/library/advanced-features/experimental-cache-primitives)
- `[st.experimental_memo](https://docs.streamlit.io/library/api-reference/performance/st.experimental_memo)`
- `[st.experimental_singleton](https://docs.streamlit.io/library/api-reference/performance/st.experimental_singleton)`