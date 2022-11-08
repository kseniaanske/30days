# Day 15

# **st.latex**

`st.latex` display mathematical expressions formatted as LaTeX.

## **What we're building?**

A simple app that displays a mathematical equation using LaTeX syntax via the `st.latex` command.

## **Demo app**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Code**

Here's how to use `st.latex`:

`import streamlit as st

st.header('st.latex')

st.latex(r'''
     a + ar + a r^2 + a r^3 + \cdots + a r^{n-1} =
     \sum_{k=0}^{n-1} ar^k =
     a \left(\frac{1-r^{n}}{1-r}\right)
     ''')`

## **Line-by-line explanation**

The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` like so:

`import streamlit as st`

This is followed by creating a header text for the app:

`st.header('st.latex')`

Next, we're displaying the mathematical equation via `st.latex`:

`st.latex(r'''
     a + ar + a r^2 + a r^3 + \cdots + a r^{n-1} =
     \sum_{k=0}^{n-1} ar^k =
     a \left(\frac{1-r^{n}}{1-r}\right)
     ''')`

## **References**

- Read more about `[st.latex](https://docs.streamlit.io/library/api-reference/text/st.latex)` in the Streamlit API Documentation.

# **ст.латекс**

st.latex отображает математические выражения в формате LaTeX.

## **Что мы строим?**

Простое приложение, которое отображает математическое уравнение с использованием синтаксиса LaTeX с помощью команды `st.latex`.

## **Демонстрационное приложение**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Вот как использовать `st.latex`:

`import streamlit as st

st.header('st.latex')

st.latex(r'''
     a + ar + a r^2 + a r^3 + \cdots + a r^{n-1} =
     \sum_{k=0}^{n-1} ar^k =
     a \left(\frac{1-r^{n}}{1-r}\right)
     ''')`

## **Построчное объяснение**

Самое первое, что нужно сделать при создании приложения Streamlit, это импортировать библиотеку `streamlit` как `st`, например:

`import streamlit as st`

Затем следует создание текста заголовка для приложения:

`st.header('st.latex')`

Затем мы отображаем математическое уравнение через `st.latex`:

`st.latex(r'''
     a + ar + a r^2 + a r^3 + \cdots + a r^{n-1} =
     \sum_{k=0}^{n-1} ar^k =
     a \left(\frac{1-r^{n}}{1-r}\right)
     ''')`

## **Использованная литература**

– Узнайте больше о `[st.latex](https://docs.streamlit.io/library/api-reference/text/st.latex)` в документации по API Streamlit.