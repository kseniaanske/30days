# Day 10

# **st.selectbox**

`st.selectbox` allows the display of a select widget.

## **What we're building?**

A simple app that asks the user what their favorite color is.

Flow of the app:

1. User selects a color
2. App prints out the selected color

## **Demo app**

The deployed Streamlit app should look something like the one shown in the below link:

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Code**

Here's the code to implement the above mentioned app:

`import streamlit as st

st.header('st.selectbox')

option = st.selectbox(
     'What is your favorite color?',
     ('Blue', 'Red', 'Green'))

st.write('Your favorite color is ', option)`

## **Line-by-line explanation**

The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` like so:

`import streamlit as st`

This is followed by creating a header text for the app:

`st.header('st.selectbox')`

Next, we will create a variable called `option` that will accept user input in the form of a **select** input widget via the `st.selectbox()` command.

`option = st.selectbox(
     'What is your favorite color?',
     ('Blue', 'Red', 'Green'))`

As we can see from the above code box, the `st.selectbox()` command accepts 2 input arguments:

1. The text that goes above the select widget, i.e. `'What is your favorite color?'`
2. The possible values to select from `('Blue', 'Red', 'Green')`

Finally, we'll print out the selected color as follows:

`st.write('Your favorite color is ', option)`

## **Next steps**

Now that you have created the Streamlit app locally, it's time to deploy it to [Streamlit Cloud](https://streamlit.io/cloud).

## **References**

More about `[st.selectbox](https://docs.streamlit.io/library/api-reference/widgets/st.selectbox)`

# **st.selectbox**

`st.selectbox` позволяет отображать выбранный виджет.

## **Что мы строим?**

Простое приложение, которое спрашивает пользователя, какой у него любимый цвет.

Процесс приложения:

1. Пользователь выбирает цвет
2. Приложение распечатывает выбранный цвет

## **Демонстрационное приложение**

Развернутое приложение Streamlit должно выглядеть примерно так, как показано по ссылке ниже:

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Вот код для реализации вышеупомянутого приложения:

`import streamlit as st

st.header('st.selectbox')

option = st.selectbox(
     'What is your favorite color?',
     ('Blue', 'Red', 'Green'))

st.write('Your favorite color is ', option)`

## **Построчное объяснение**

Самое первое, что нужно сделать при создании приложения Streamlit, это импортировать библиотеку `streamlit` как `st`, например:

`import streamlit as st`

Затем следует создание текста заголовка для приложения:

`st.header('st.selectbox')`

Далее мы создадим переменную с именем `option`, которая будет принимать пользовательский ввод в виде виджета **выбора** ввода с помощью команды `st.selectbox()`.

`option = st.selectbox(
     'What is your favorite color?',
     ('Blue', 'Red', 'Green'))`

Как видно из кода выше, команда `st.selectbox()` принимает 2 входных аргумента:

1. Текст над виджетом выбора, например `'What is your favorite color?'`
2. Возможные значения для выбора `('Blue', 'Red', 'Green')`

Наконец, мы распечатаем выбранный цвет следующим образом:

`st.write('Your favorite color is ', option)`

## **Следующие шаги**

Теперь, когда вы создали приложение Streamlit локально, пришло время развернуть его в [Streamlit Cloud](https://streamlit.io/cloud).

## **Использованная литература**

Подробнее о `[st.selectbox](<https://docs.streamlit.io/library/api-reference/widgets/st.selectbox>)`