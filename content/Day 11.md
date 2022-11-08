# Day 11

# **st.multiselect**

`st.multiselect` displays a multiselect widget.

## **Demo app**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Code**

Here's how to use `st.multiselect`:

`import streamlit as st

st.header('st.multiselect')

options = st.multiselect(
     'What are your favorite colors',
     ['Green', 'Yellow', 'Red', 'Blue'],
     ['Yellow', 'Red'])

st.write('You selected:', options)`

## **Line-by-line explanation**

The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` like so:

`import streamlit as st`

This is followed by creating a header text for the app:

`st.header('st.multiselect')`

Next, we're going to use the `st.multiselect` widget to accept input where users will be able to select one or more colors of there choice.

`options = st.multiselect(
     'What are your favorite colors',
     ['Green', 'Yellow', 'Red', 'Blue'],
     ['Yellow', 'Red'])`

Finally, we'll write out the selected colors:

`st.write('You selected:', options)`

## **Further reading**

- `[st.multiselect](https://docs.streamlit.io/library/api-reference/widgets/st.multiselect)`

# **st.multiselect**

`st.multiselect` отображает виджет множественного выбора.

## **Демонстрационное приложение**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Вот как использовать `st.multiselect`:

`import streamlit as st

st.header('st.multiselect')

options = st.multiselect(
     'What are your favorite colors',
     ['Green', 'Yellow', 'Red', 'Blue'],
     ['Yellow', 'Red'])

st.write('You selected:', options)`

## **Построчное объяснение**

Самое первое, что нужно сделать при создании приложения Streamlit, это импортировать библиотеку `streamlit` как `st`, например:

`import streamlit as st`

Затем следует создание текста заголовка для приложения:

`st.header('st.multiselect')`

Далее мы собираемся использовать виджет `st.multiselect`, чтобы принимать ввод, где пользователи смогут выбрать один или несколько цветов по своему выбору.

`options = st.multiselect(
     'What are your favorite colors',
     ['Green', 'Yellow', 'Red', 'Blue'],
     ['Yellow', 'Red'])`

Наконец, мы выпишем выбранные цвета:

`st.write('Вы выбрали:', параметры)`

## **Дальнейшее чтение**

- `[st.multiselect](<https://docs.streamlit.io/library/api-reference/widgets/st.multiselect>)`