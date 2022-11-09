# Day 25

# **st.session_state**

We define access to a Streamlit app in a browser tab as a session. For each browser tab that connects to the Streamlit server, a new session is created. Streamlit reruns your script from top to bottom every time you interact with your app. Each reruns takes place in a blank slate: no variables are shared between runs.

Session State is a way to share variables between reruns, for each user session. In addition to the ability to store and persist state, Streamlit also exposes the ability to manipulate state using Callbacks.

In this tutorial, we will illustrate the usage of Session State and Callbacks as we build a weight conversion app.

`st.session_state` allows the implementation of session state in a Streamlit app.

## **Demo app**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Code**

Here's how to use `st.session_state`:

`import streamlit as st

st.title('st.session_state')

def lbs_to_kg():
  st.session_state.kg = st.session_state.lbs/2.2046
def kg_to_lbs():
  st.session_state.lbs = st.session_state.kg*2.2046

st.header('Input')
col1, spacer, col2 = st.columns([2,1,2])
with col1:
  pounds = st.number_input("Pounds:", key = "lbs", on_change = lbs_to_kg)
with col2:
  kilogram = st.number_input("Kilograms:", key = "kg", on_change = kg_to_lbs)

st.header('Output')
st.write("st.session_state object:", st.session_state)`

## **Line-by-line explanation**

The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` like so:

`import streamlit as st`

Firstly, we'll start by creating the title of the app:

`st.title('st.session_state')`

Next, we define custom functions for the weight conversion from lbs to kg and vice versa:

`def lbs_to_kg():
  st.session_state.kg = st.session_state.lbs/2.2046
def kg_to_lbs():
  st.session_state.lbs = st.session_state.kg*2.2046`

Here, we use `st.number_input` to accept numerical inputs of the weight values:

`st.header('Input')
col1, spacer, col2 = st.columns([2,1,2])
with col1:
  pounds = st.number_input("Pounds:", key = "lbs", on_change = lbs_to_kg)
with col2:
  kilogram = st.number_input("Kilograms:", key = "kg", on_change = kg_to_lbs)`

The above 2 custom functions will be called upon as soon as a numerical value is entered into the number box created using the `st.number_input` command. Notice how the `on_change` option specifies the 2 custom functions `lbs_to_kg` and `kg_to_lbs`).

In a nutshell, upon entering a number into the `st.number_input` box the number is converted by these custom functions.

Finally, the weight values in `kg` and `lbs` units as stored in the session state as `st.session_state.kg` and `st.session_state.lbs` will be printed out via `st.write`:

`st.header('Output')
st.write("st.session_state object:", st.session_state)`

## **Further reading**

- [Session State](https://docs.streamlit.io/library/api-reference/session-state)
- [Add statefulness to apps](https://docs.streamlit.io/library/advanced-features/session-state)

# **st.session_state**

Мы определяем доступ к приложению Streamlit на вкладке браузера как session. Для каждой вкладки браузера, которая подключается к серверу Streamlit, создается новый session. Streamlit перезапускает ваш скрипт сверху вниз каждый раз, когда вы взаимодействуете с приложением. Каждый повтор происходит с чистого листа: никакие переменные не используются совместно.

Session State—это способ обмена переменными между повторами для каждого session. В дополнение к возможности сохранять state, Streamlit также предоставляет возможность манипулировать состоянием с помощью Callbacks.

В этом руководстве мы проиллюстрируем использование Session State и Callbacks при создании приложения для преобразования веса.

`st.session_state` позволяет реализовать Session State в приложении Streamlit.

## **Демонстрационное приложение**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Вот как использовать `st.session_state`:

`import streamlit as st

st.title('st.session_state')

def lbs_to_kg():
  st.session_state.kg = st.session_state.lbs/2.2046
def kg_to_lbs():
  st.session_state.lbs = st.session_state.kg*2.2046

st.header('Input')
col1, spacer, col2 = st.columns([2,1,2])
with col1:
  pounds = st.number_input("Pounds:", key = "lbs", on_change = lbs_to_kg)
with col2:
  kilogram = st.number_input("Kilograms:", key = "kg", on_change = kg_to_lbs)

st.header('Output')
st.write("st.session_state object:", st.session_state)`

## **Построчное объяснение**

Самое первое, что нужно сделать при создании приложения Streamlit, это импортировать библиотеку `streamlit` как `st`, например:

`import streamlit as st`

Во-первых, мы начнем с создания заголовка приложения:

`st.title('st.session_state')`

Затем мы определяем пользовательские функции для преобразования веса из фунтов в кг и наоборот:

`def lbs_to_kg():
  st.session_state.kg = st.session_state.lbs/2.2046
def kg_to_lbs():
  st.session_state.lbs = st.session_state.kg*2.2046`

Здесь мы используем `st.number_input`, чтобы принимать числовые значения значений веса:

`st.header('Input')
col1, spacer, col2 = st.columns([2,1,2])
with col1:
  pounds = st.number_input("Pounds:", key = "lbs", on_change = lbs_to_kg)
with col2:
  kilogram = st.number_input("Kilograms:", key = "kg", on_change = kg_to_lbs)`

Вышеупомянутые 2 пользовательские функции будут вызываться, как только числовое значение будет введено в числовое поле, созданное с помощью команды `st.number_input`. Обратите внимание, как параметр `on_change` определяет две пользовательские функции lbs_to_kg и `kg_to_lbs`).

В двух словах, при вводе числа в поле `st.number_input` число преобразуется этими пользовательскими функциями.

Наконец, значения веса в единицах `kg` и `lbs`, сохраненные в Session State как `st.session_state.kg` и `st.session_state.lbs`, будут распечатаны с помощью `st.write`:

`st.header('Output')
st.write("st.session_state object:", st.session_state)`

## **Дальнейшее чтение**

- [Session State](https://docs.streamlit.io/library/api-reference/session-state)
- [Добавить состояние в приложения](https://docs.streamlit.io/library/advanced-features/session-state)