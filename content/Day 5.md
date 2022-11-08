# День 5

# **st.write**

`st.write` позволяет записывать текст и аргументы в приложение Streamlit.

Помимо возможности показывать текст с помощью команды `st.write()` можно также показать следующее:

- Печатать строки; работает как `st.markdown()`
- Показывать Python `dict`
- Показываать `Pandas` DataFrame в виде таблицы
- Сюжеты/графики/рисунки из `matplotlib`, `plotly`, `altair`, `graphviz`, `bokeh`
и многое другое (см. [st.write в документации по API](https://docs.streamlit.io/library/api-reference/write-magic/st.write))

## **Что мы строим?**

Простое приложение которое демонстрирует различные способы использования команды `st.write()` для отображения текста, чисел, кадр данных и графиков.

## **Демонстрационное приложение**

Развернутое приложение Streamlit должно выглядеть примерно так, как показано по ссылке ниже:

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Вот как использовать st.write:

`import numpy as np
import altair as alt
import pandas as pd
import streamlit as st

st.header('st.write')

# Example 1

st.write('Hello, *World!* :sunglasses:')

# Example 2

st.write(1234)

# Example 3

df = pd.DataFrame({
     'first column': [1, 2, 3, 4],
     'second column': [10, 20, 30, 40]
     })
st.write(df)

# Example 4

st.write('Below is a DataFrame:', df, 'Above is a dataframe.')

# Example 5

df2 = pd.DataFrame(
     np.random.randn(200, 3),
     columns=['a', 'b', 'c'])
c = alt.Chart(df2).mark_circle().encode(
     x='a', y='b', size='c', color='c', tooltip=['a', 'b', 'c'])
st.write(c)`

## **Построчное объяснение**

Первое, что нужно сделать при создании приложения Streamlit—это начать с импорта библиотеки `streamlit` как `st`, например:

`import streamlit as st`

Затем следует создание текста заголовка для приложения:

`st.header('st.write')`

**Пример 1** Основной вариант использования—вывод текста и текст в формате Markdown:

`st.write('Hello, *World!* :sunglasses:')`

**Пример 2** Как упоминалось выше, его также можно использовать для вывода других форматов данных, таких как числа:

`st.write(1234)`

**Пример 3** Кадры данных также могут быть выведены следующим образом:

`df = pd.DataFrame({
     'first column': [1, 2, 3, 4],
     'second column': [10, 20, 30, 40]
     })
st.write(df)`

**Пример 4** Вы можете передать несколько аргументов:

`st.write('Below is a DataFrame:', df, 'Above is a dataframe.')`

**Пример 5** Наконец, вы также можете вывести графики, передав их в переменную следующим образом:

`df2 = pd.DataFrame(
     np.random.randn(200, 3),
     columns=['a', 'b', 'c'])
c = alt.Chart(df2).mark_circle().encode(
     x='a', y='b', size='c', color='c', tooltip=['a', 'b', 'c'])
st.write(c)`

## **Демонстрационное приложение**

Развернутое приложение Streamlit должно выглядеть примерно так, как показано по ссылке ниже:

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Следующие шаги**

Теперь, когда вы создали приложение Streamlit локально, вы можете развернуть его в [Streamlit Cloud](https://streamlit.io/cloud), как мы объясним в будущей задаче.

Поскольку это первая неделя вашей задачи, мы предоставляем полный код (как показано в выше) и решение (демонстрационное приложение) прямо на этой веб-странице.

Переходя к следующим задачам, мы рекомендуем сначала попробовать реализовать приложение Streamlit самостоятельно.

Не волнуйтесь, если вы застряли, вы всегда можете взглянуть на решение.

## **Дальнейшее чтение**

Помимо `[st.write](<https://docs.streamlit.io/library/api-reference/write-magic/st.write>)`, вы можете изучить другие способы вывода текста:

- `[st.markdown](<https://docs.streamlit.io/library/api-reference/text/st.markdown>)`
- `[st.header](<https://docs.streamlit.io/library/api-reference/text/st.header>)`
- `[st.subheader](<https://docs.streamlit.io/library/api-reference/text/st.subheader>)`
- `[st.caption](<https://docs.streamlit.io/library/api-reference/text/st.caption>)`
- `[ст.текст](<https://docs.streamlit.io/library/api-reference/text/st.text>)`
- `[st.latex](<https://docs.streamlit.io/library/api-reference/text/st.latex>)`
- `[ст.код](<https://docs.streamlit.io/library/api-reference/text/st.code>)`
