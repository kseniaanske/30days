# Day 26

# **How to use API by building the Bored API app**

The Bored API app suggests fun things for you to do when you are bored!

Technically, it also demonstrates the usage of APIs from within a Streamlit app.

## **Demo app**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Code**

Here's how to implement the Bored-API app:

`import streamlit as st
import requests

st.title('🏀 Bored API app')

st.sidebar.header('Input')
selected_type = st.sidebar.selectbox('Select an activity type', ["education", "recreational", "social", "diy", "charity", "cooking", "relaxation", "music", "busywork"])

suggested_activity_url = f'http://www.boredapi.com/api/activity?type={selected_type}'
json_data = requests.get(suggested_activity_url)
suggested_activity = json_data.json()

c1, c2 = st.columns(2)
with c1:
  with st.expander('About this app'):
    st.write('Are you bored? The **Bored API app** provides suggestions on activities that you can do when you are bored. This app is powered by the Bored API.')
with c2:
  with st.expander('JSON data'):
    st.write(suggested_activity)
    
st.header('Suggested activity')
st.info(suggested_activity['activity'])

col1, col2, col3 = st.columns(3)
with col1:
  st.metric(label='Number of Participants', value=suggested_activity['participants'], delta='')
with col2:
  st.metric(label='Type of Activity', value=suggested_activity['type'].capitalize(), delta='')
with col3:
  st.metric(label='Price', value=suggested_activity['price'], delta='')`

## **Line-by-line explanation**

The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` and the `requests` library like so:

`import streamlit as st
import requests`

The app's title is displayed via `st.title`:

`st.title('🏀 Bored API app')`

Next, we'll accept user input on the **activity type** by means of the `st.selectbox` command:

`st.sidebar.header('Input')
selected_type = st.sidebar.selectbox('Select an activity type', ["education", "recreational", "social", "diy", "charity", "cooking", "relaxation", "music", "busywork"])`

The selected activity mentioned above is then appended to the URL via an f-string, which is then used to retrieve the resulting JSON data:

`suggested_activity_url = f'http://www.boredapi.com/api/activity?type={selected_type}'
json_data = requests.get(suggested_activity_url)
suggested_activity = json_data.json()`

Here, we'll display information about the app and the JSON data via the `st.expander` command.

`c1, c2 = st.columns(2)
with c1:
  with st.expander('About this app'):
    st.write('Are you bored? The **Bored API app** provides suggestions on activities that you can do. This app is powered by the Bored API.')
with c2:
  with st.expander('JSON data'):
    st.write(suggested_activity)`

We'll then display a suggested activity like so:

`st.header('Suggested activity')
st.info(suggested_activity['activity'])`

Finally, we'll also display the accompanying information of the suggested activity such as the `Number of Participants`, `Type of Activity` and `Price`.

`col1, col2, col3 = st.columns(3)
with col1:
  st.metric(label='Number of Participants', value=suggested_activity['participants'], delta='')
with col2:
  st.metric(label='Type of Activity', value=suggested_activity['type'].capitalize(), delta='')
with col3:
  st.metric(label='Price', value=suggested_activity['price'], delta='')`

## **Further reading**

- [Bored API](http://www.boredapi.com/)

# **Как использовать API при создании приложения Bored API**

Приложение Bored API предлагает интересные занятия, когда вам скучно!

Технически оно также демонстрирует использование API в приложении Streamlit.

## **Демонстрационное приложение**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Как реализовать приложение Bored-API:

`import streamlit as st
import requests

st.title('🏀 Bored API app')

st.sidebar.header('Input')
selected_type = st.sidebar.selectbox('Select an activity type', ["education", "recreational", "social", "diy", "charity", "cooking", "relaxation", "music", "busywork"])

suggested_activity_url = f'http://www.boredapi.com/api/activity?type={selected_type}'
json_data = requests.get(suggested_activity_url)
suggested_activity = json_data.json()

c1, c2 = st.columns(2)
with c1:
  with st.expander('About this app'):
    st.write('Are you bored? The **Bored API app** provides suggestions on activities that you can do when you are bored. This app is powered by the Bored API.')
with c2:
  with st.expander('JSON data'):
    st.write(suggested_activity)
    
st.header('Suggested activity')
st.info(suggested_activity['activity'])

col1, col2, col3 = st.columns(3)
with col1:
  st.metric(label='Number of Participants', value=suggested_activity['participants'], delta='')
with col2:
  st.metric(label='Type of Activity', value=suggested_activity['type'].capitalize(), delta='')
with col3:
  st.metric(label='Price', value=suggested_activity['price'], delta='')`

## **Построчное объяснение**

Самое первое, что нужно сделать при создании приложения Streamlit, это импортировать библиотеку `streamlit` как `st` и библиотеку `requests` следующим образом:

`import streamlit as st
import requests`

Название приложения отображается через `st.title`:

`st.title('🏀 Bored API app')`

Затем мы примем пользовательский ввод для **типа активности** с помощью команды `st.selectbox`:

`st.sidebar.header('Input')
selected_type = st.sidebar.selectbox('Select an activity type', ["education", "recreational", "social", "diy", "charity", "cooking", "relaxation", "music", "busywork"])`

Выбранное действие, упомянутое выше, затем добавляется к URL-адресу через f-string, которое затем используется для получения результирующих данных JSON:

`suggested_activity_url = f'http://www.boredapi.com/api/activity?type={selected_type}'
json_data = requests.get(suggested_activity_url)
suggested_activity = json_data.json()`

Здесь мы будем отображать информацию о приложении и о данных JSON с помощью команды `st.expander` .

`c1, c2 = st.columns(2)
with c1:
  with st.expander('About this app'):
    st.write('Are you bored? The **Bored API app** provides suggestions on activities that you can do. This app is powered by the Bored API.')
with c2:
  with st.expander('JSON data'):
    st.write(suggested_activity)`

Затем мы отобразим предлагаемое действие следующим образом:

`st.header('Suggested activity')
st.info(suggested_activity['activity'])`

Наконец, мы также отобразим сопутствующую информацию о предлагаемом мероприятии, такую как `Number of Participants`, `Type of Activity`, и `Price`.

`col1, col2, col3 = st.columns(3)
with col1:
  st.metric(label='Number of Participants', value=suggested_activity['participants'], delta='')
with col2:
  st.metric(label='Type of Activity', value=suggested_activity['type'].capitalize(), delta='')
with col3:
  st.metric(label='Price', value=suggested_activity['price'], delta='')`

## **Дальнейшее чтение**

- [Bored API](http://www.boredapi.com/)