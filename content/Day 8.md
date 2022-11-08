# Day 8

# **st.slider**

`st.slider` allows the display of a slider input widget.

The following data types are supported: int, float, date, time, and datetime.

## **What we're building?**

A simple app that shows the various ways on how to accept user input by adjusting the slider widget.

Flow of the app:

1. User selects value by adjusting the slider widget
2. App prints out the selected value

## **Demo app**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Code**

Here's how to use st.slider:

`import streamlit as st
from datetime import time, datetime

st.header('st.slider')

# Example 1

st.subheader('Slider')

age = st.slider('How old are you?', 0, 130, 25)
st.write("I'm ", age, 'years old')

# Example 2

st.subheader('Range slider')

values = st.slider(
     'Select a range of values',
     0.0, 100.0, (25.0, 75.0))
st.write('Values:', values)

# Example 3

st.subheader('Range time slider')

appointment = st.slider(
     "Schedule your appointment:",
     value=(time(11, 30), time(12, 45)))
st.write("You're scheduled for:", appointment)

# Example 4

st.subheader('Datetime slider')

start_time = st.slider(
     "When do you start?",
     value=datetime(2020, 1, 1, 9, 30),
     format="MM/DD/YY - hh:mm")
st.write("Start time:", start_time)`

## **Line-by-line explanation**

The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` like so:

`import streamlit as st
from datetime import time, datetime`

This is followed by creating a header text for the app:

`st.header('st.slider')`

**Example 1**

Slider:

`st.subheader('Slider')

age = st.slider('How old are you?', 0, 130, 25)
st.write("I'm ", age, 'years old')`

As we can see, the `st.slider()` command is used to collect user input about the age of users.

The first input argument displays the text just above the **slider** widget asking `'How old are you?'`.

The following three integers `0, 130, 25` represents the minimum, maximum and default values, respectively.

**Example 2**

Range slider:

`st.subheader('Range slider')

values = st.slider(
     'Select a range of values',
     0.0, 100.0, (25.0, 75.0))
st.write('Values:', values)`

The range slider allow selection of a lower and upper bound value pair.

The first input argument displays the text just above the **range slider** widget asking `'Select a range of values'`.

The following three arguments `0.0, 100.0, (25.0, 75.0)` represents the minimum and maximum values while the last tuple denotes the default values to use as the selected lower (25.0) and upper (75.0) bound values.

**Example 3**

Range time slider:

`st.subheader('Range time slider')

appointment = st.slider(
     "Schedule your appointment:",
     value=(time(11, 30), time(12, 45)))
st.write("You're scheduled for:", appointment)`

The range time slider allows selection of a lower and upper bound value pair of datetime.

The first input argument displays the text just above the **range time slider** widget asking `'Schedule your appointment:`.

The default values for the lower and upper bound value pairs of datetime are set to 11:30 and 12:45, respectively.

**Example 4**

Datetime slider:

`st.subheader('Datetime slider')

start_time = st.slider(
     "When do you start?",
     value=datetime(2020, 1, 1, 9, 30),
     format="MM/DD/YY - hh:mm")
st.write("Start time:", start_time)`

The datetime slider allows selection of a datetime.

The first input argument displays the text just above the **datetime** slider widget asking `'When do you start?'`.

The default value for the datetime was set using the `value` option to be January 1, 2020 at 9:30

## **Further reading**

You can also explore the following related widget:

- `[st.select_slider](https://docs.streamlit.io/library/api-reference/widgets/st.select_slider)`

# **st.slider**

`st.slider` позволяет отображать виджет ввода слайдера.

Поддерживаются следующие типы данных: int, float, date, time, и datetime.

## **Что мы строим?**

Простое приложение, которое показывает различные способы принятия пользовательского ввода путем настройки виджета slider.

Процесс приложения:

1. Пользователь выбирает значение, настраивая виджет slider.
2. Приложение распечатывает выбранное значение.

## **Демонстрационное приложение**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Вот как использовать st.slider:

`import streamlit as st
from datetime import time, datetime

st.header('st.slider')

# Example 1

st.subheader('Slider')

age = st.slider('How old are you?', 0, 130, 25)
st.write("I'm ", age, 'years old')

# Example 2

st.subheader('Range slider')

values = st.slider(
     'Select a range of values',
     0.0, 100.0, (25.0, 75.0))
st.write('Values:', values)

# Example 3

st.subheader('Range time slider')

appointment = st.slider(
     "Schedule your appointment:",
     value=(time(11, 30), time(12, 45)))
st.write("You're scheduled for:", appointment)

# Example 4

st.subheader('Datetime slider')

start_time = st.slider(
     "When do you start?",
     value=datetime(2020, 1, 1, 9, 30),
     format="MM/DD/YY - hh:mm")
st.write("Start time:", start_time)`

## **Построчное объяснение**

Самое первое, что нужно сделать при создании приложения Streamlit, это импортировать библиотеку `streamlit` как `st`, например:

`import streamlit as st
from datetime import time, datetime`

Затем следует создание текста заголовка для приложения:

`st.header('st.slider')`

**Пример 1**

Ползунок:

`st.subheader('Slider')

age = st.slider('How old are you?', 0, 130, 25)
st.write("I'm ", age, 'years old')`

Как вы видите, команда `st.slider()` используется для сбора информации о возрасте пользователей.

Первый входной аргумент отображает текст чуть выше **ползунка** виджета с вопросом `'How old are you?'`.

Следующие три целых числа `0, 130, 25` представляют минимальное значение, максимальное значение, и значение по умолчанию соответственно.

**Пример 2**

Ползунок диапазона:

`st.subheader('Range slider')

values = st.slider(
     'Select a range of values',
     0.0, 100.0, (25.0, 75.0))
st.write('Values:', values)`

Ползунок диапазона позволяет выбрать пару значений нижней и верхней границы.

Первый входной аргумент отображает текст чуть выше **ползунка диапазона** виджета с вопросом `'Select a range of values'`.

Следующие три аргумента `0,0, 100,0, (25,0, 75,0)` представляют минимальное и максимальное значения, а последний кортеж обозначает значения по умолчанию для использования в качестве выбранных нижних (25,0) и верхних (75,0) граничных значений.

**Пример 3**

Ползунок времени диапазона:

`st.subheader('Range time slider')

appointment = st.slider(
     "Schedule your appointment:",
     value=(time(11, 30), time(12, 45)))
st.write("You're scheduled for:", appointment)`

Ползунок диапазона времени позволяет выбрать пару значений нижней и верхней границ даты и времени.

Первый входной аргумент отображает текст чуть выше **ползунка времени** виджета с запросом `'Schedule your appointment:`.

По умолчанию, значения для пар значений нижней и верхней границ даты и времени установлены на 11:30 и 12:45 соответственно.

**Пример 4**

Ползунок даты и времени:

`st.subheader('Datetime slider')

start_time = st.slider(
     "When do you start?",
     value=datetime(2020, 1, 1, 9, 30),
     format="MM/DD/YY - hh:mm")
st.write("Start time:", start_time)`

Ползунок даты и времени позволяет выбрать дату и время.

Первый входной аргумент отображает текст прямо над виджетом **datetime** ползунком с запросом `'When do you start?'`.

По умолчанию, значение для даты и времени было установлено с помощью параметра `value`: 1 января 2020 года, 9:30.

## **Дальнейшее чтение**

Вы также можете изучить следующий соответствующий виджет:

- `[st.select_slider](<https://docs.streamlit.io/library/api-reference/widgets/st.select_slider>)`