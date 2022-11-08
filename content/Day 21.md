# Day 21

# **st.progress**

`st.progress` displays a progress bar that updates graphically as the iteration progresses.

## **Demo app**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Code**

Here's how to use `st.progress`:

`import streamlit as st
import time

st.title('st.progress')

with st.expander('About this app'):
     st.write('You can now display the progress of your calculations in a Streamlit app with the `st.progress` command.')

my_bar = st.progress(0)

for percent_complete in range(100):
     time.sleep(0.05)
     my_bar.progress(percent_complete + 1)

st.balloons()`

## **Line-by-line explanation**

The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` along with the `time` library like so:

`import streamlit as st
import time`

Next, we create a title text for the app:

`st.title('st.progress')`

An **About box** is created using `st.expander` and description is displayed via `st.write`:

`with st.expander('About this app'):
     st.write('You can now display the progress of your calculations in a Streamlit app with the `st.progress` command.')`

Finally, we define a progress bar and instantiate it with a starting value of `0`. Then, a `for` loop will iterate from `0` until `100` is reached. In each iteration, we use `time.sleep(0.05)` to allow the app to wait for `0.05` before adding a value of `1` to the `my_bar` progress bar and in doing so the graphical display of the bar increases with each iteration.

`my_bar = st.progress(0)

for percent_complete in range(100):
     time.sleep(0.05)
     my_bar.progress(percent_complete + 1)

st.balloons()`

## **Further reading**

- `[st.progress](https://docs.streamlit.io/library/api-reference/status/st.progress)`

# **st.progress**

`st.progress` отображает индикатор выполнения, который графически обновляется по мере выполнения итерации.

## **Демонстрационное приложение**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Как использовать `st.progress`:

`import streamlit as st
import time

st.title('st.progress')

with st.expander('About this app'):
     st.write('You can now display the progress of your calculations in a Streamlit app with the `st.progress` command.')

my_bar = st.progress(0)

for percent_complete in range(100):
     time.sleep(0.05)
     my_bar.progress(percent_complete + 1)

st.balloons()`

## **Построчное объяснение**

Самое первое, что нужно сделать при создании приложения Streamlit, это импортировать библиотеку `streamlit` как `st` вместе с библиотекой `time` следующим образом:

`import streamlit as st
import time`

Далее мы создаем текст заголовка для приложения:

`st.title('st.progress')`

Поле **О программе** создается с помощью `st.expander`, а описание отображается с помощью `st.write`:

`with st.expander('About this app'):
     st.write('You can now display the progress of your calculations in a Streamlit app with the `st.progress` command.')`

Наконец, мы определяем индикатор выполнения и создаем его экземпляр с начальным значением `0`. Затем цикл for будет повторяться от `0` до `100`. В каждой итерации мы используем `time.sleep(0.05)`, чтобы позволить приложению ждать `0,05`, прежде чем добавить значение `1` в индикатор выполнения `my_bar`, при этом графическое отображение полосы увеличивается с каждой итерацией.

`my_bar = st.progress(0)

for percent_complete in range(100):
     time.sleep(0.05)
     my_bar.progress(percent_complete + 1)

st.balloons()`

## **Дальнейшее чтение**

- `[st.progress](https://docs.streamlit.io/library/api-reference/status/st.progress)`