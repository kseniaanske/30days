# Day 9

# **st.line_chart**

`st.line_chart` displays a line chart.

This is syntax-sugar around `st.altair_chart`. The main difference is this command uses the data's own column and indices to figure out the chart's spec. As a result this is easier to use for many "just plot this" scenarios, while being less customizable.

If `st.line_chart` does not guess the data specification correctly, try specifying your desired chart using st.altair_chart.

## **What we're building?**

A simple app for displaying a line chart.

Flow of the app:

1. Create a `Pandas` DataFrame from numbers randomly generated via `NumPy`.
2. Create and display the line chart via `st.line_chart()` command.

## **Demo app**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Code**

Here's how to use `[st.line_chart](https://docs.streamlit.io/library/api-reference/charts/st.line_chart)`:

`import streamlit as st
import pandas as pd
import numpy as np

st.header('Line chart')

chart_data = pd.DataFrame(
     np.random.randn(20, 3),
     columns=['a', 'b', 'c'])

st.line_chart(chart_data)`

## **Line-by-line explanation**

The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` as well as other libraries like so:

`import streamlit as st
import pandas as pd
import numpy as np`

Next, we create a header text for the app:

`st.header('Line chart')`

Then, we create a DataFrame of randomly generated numbers that contains 3 columns.

`chart_data = pd.DataFrame(
     np.random.randn(20, 3),
     columns=['a', 'b', 'c'])`

Finally, a line chart is created by using `st.line_chart()` with the DataFrame stored in the `chart_data` variable as the input data:

`st.line_chart(chart_data)`

## **Further reading**

Read more about the following related Streamlit command from which `[st.line_chart](https://docs.streamlit.io/library/api-reference/charts/st.line_chart)` is based on:

- `[st.altair_chart](https://docs.streamlit.io/library/api-reference/charts/st.altair_chart)`

# **st.line_chart**

`st.line_chart` отображает линейный график.

Это синтаксический сахар вокруг `st.altair_chart`. Основное отличие состоит в том, что эта команда использует собственный столбец данных и индексы для определения спецификации диаграммы. В результате его легче использовать для многих сценариев «просто постройте это», но при этом он менее настраиваемый.

Если `st.line_chart` не угадывает спецификацию данных, попробуйте указать желаемую диаграмму с помощью st.altair_chart.

## **Что мы строим?**

Простое приложение для отображения линейной диаграммы.

Процесс приложения:

1. Создайте DataFrame Pandas из чисел, случайно сгенерированных с помощью NumPy.
2. Создайте и отобразите линейный график с помощью команды `st.line_chart()`.

## **Демонстрационное приложение**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Вот как использовать `[st.line_chart](<https://docs.streamlit.io/library/api-reference/charts/st.line_chart>)`:

`import streamlit as st
import pandas as pd
import numpy as np

st.header('Line chart')

chart_data = pd.DataFrame(
     np.random.randn(20, 3),
     columns=['a', 'b', 'c'])

st.line_chart(chart_data)`

## **Построчное объяснение**

Самое первое, что нужно сделать при создании приложения Streamlit, это импортировать библиотекуи`streamlit` как `st`, а также другие библиотеки, например:

`import streamlit as st
import pandas as pd
import numpy as np`

Далее мы создаем текст заголовка для приложения:

`st.header('Line chart')`

Затем мы создаем DataFrame из случайно сгенерированных чисел, который содержит три столбца.

`chart_data = pd.DataFrame(
     np.random.randn(20, 3),
     columns=['a', 'b', 'c'])`

Наконец, линейная диаграмма создается с помощью `st.line_chart()` с DataFrame, хранящимся в переменной `chart_data`, в качестве входных данных:

`st.line_chart(chart_data)`

## **Дальнейшее чтение**

Узнайте больше о следующей соответствующей команде Streamlit, на основе которой [st.line_chart](https://docs.streamlit.io/library/api-reference/charts/st.line_chart) работает:

- `[st.altair_chart](<https://docs.streamlit.io/library/api-reference/charts/st.altair_chart>)`