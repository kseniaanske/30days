# Day 19

# **How to layout your Streamlit app**

In this tutorial, we're going to use the following commands to layout our Streamlit app:

- `st.set_page_config(layout="wide")` - Displays the contents of the app in wide mode (otherwise by default, the contents are encapsulated in a fixed width box.
- `st.sidebar` - Places the widgets or text/image displays in the sidebar.
- `st.expander` - Places text/image displays inside a collapsible container box.
- `st.columns` - Creates a tabular space (or column) within which contents can be placed inside.

## **Demo app**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Code**

Here's how to customize the layout of your Streamlit app:

`import streamlit as st

st.set_page_config(layout="wide")

st.title('How to layout your Streamlit app')

with st.expander('About this app'):
  st.write('This app shows the various ways on how you can layout your Streamlit app.')
  st.image('https://streamlit.io/images/brand/streamlit-logo-secondary-colormark-darktext.png', width=250)

st.sidebar.header('Input')
user_name = st.sidebar.text_input('What is your name?')
user_emoji = st.sidebar.selectbox('Choose an emoji', ['', '😄', '😆', '😊', '😍', '😴', '😕', '😱'])
user_food = st.sidebar.selectbox('What is your favorite food?', ['', 'Tom Yum Kung', 'Burrito', 'Lasagna', 'Hamburger', 'Pizza'])

st.header('Output')

col1, col2, col3 = st.columns(3)

with col1:
  if user_name != '':
    st.write(f'👋 Hello {user_name}!')
  else:
    st.write('👈  Please enter your **name**!')

with col2:
  if user_emoji != '':
    st.write(f'{user_emoji} is your favorite **emoji**!')
  else:
    st.write('👈 Please choose an **emoji**!')

with col3:
  if user_food != '':
    st.write(f'🍴 **{user_food}** is your favorite **food**!')
  else:
    st.write('👈 Please choose your favorite **food**!')`

## **Line-by-line explanation**

The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` like so:

`import streamlit as st`

We'll start by first defining the page layout to be displayed in the `wide` mode, which allows the page content to expand to the browser's width.

`st.set_page_config(layout="wide")`

Next, we'll give the Streamlit app a title.

`st.title('How to layout your Streamlit app')`

An expandable box titled `About this app` is placed under the app title. Upon expansion, we'll see additional details inside.

`with st.expander('About this app'):
  st.write('This app shows the various ways on how you can layout your Streamlit app.')
  st.image('https://streamlit.io/images/brand/streamlit-logo-secondary-colormark-darktext.png', width=250)`

Input widgets for accepting user input is placed in the sidebar as specified by using the `st.sidebar` command before the Streamlit commands `text_input` and `selectbox`. Input values entered or selected by the user are assigned and stored in the `user_name`, `user_emoji` and `user_food` variables.

`st.sidebar.header('Input')
user_name = st.sidebar.text_input('What is your name?')
user_emoji = st.sidebar.selectbox('Choose an emoji', ['', '😄', '😆', '😊', '😍', '😴', '😕', '😱'])
user_food = st.sidebar.selectbox('What is your favorite food?', ['', 'Tom Yum Kung', 'Burrito', 'Lasagna', 'Hamburger', 'Pizza'])`

Finally, we'll create 3 columns using the `st.columns` command which corresponds to `col1`, `col2` and `col3`. Then, we assign contents to each of the column by creating individual code blocks starting with the `with` statement. Underneath this, we create conditional statements that display 1 of 2 alternative text depending on whether the user had provided their input data (specified in the sidebar) or not. By default, the page displays text under the `else` statement. Upon providing user input, the corresponding information that the user gives to the app is displayed under the `Output` header text.

`st.header('Output')

col1, col2, col3 = st.columns(3)

with col1:
  if user_name != '':
    st.write(f'👋 Hello {user_name}!')
  else:
    st.write('👈  Please enter your **name**!')

with col2:
  if user_emoji != '':
    st.write(f'{user_emoji} is your favorite **emoji**!')
  else:
    st.write('👈 Please choose an **emoji**!')

with col3:
  if user_food != '':
    st.write(f'🍴 **{user_food}** is your favorite **food**!')
  else:
    st.write('👈 Please choose your favorite **food**!')`

It is also worthy to note that `f` strings were used to combine pre-canned text together with the user provided values.

## **Further reading**

- [Layouts and Containers](https://docs.streamlit.io/library/api-reference/layout)

# **Как оформить приложение Streamlit**

На этом уроке мы будем использовать следующие команды для макета нашего приложения Streamlit:

- `st.set_page_config(layout="wide")` – отображает содержимое приложения в расширенном режиме (в противном случае по умолчанию содержимое заключено в поле фиксированной ширины).
- `st.sidebar` – размещает виджеты или текст/изображения на боковой панели.
- `st.expander` – размещает дисплеи с текстом/изображением внутри складной коробки-контейнера.
- `st.columns` – создает табличное пространство (или столбец), внутри которого может быть размещено содержание.

## **Демонстрационное приложение**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Как настроить макет вашего приложения Streamlit:

`import streamlit as st

st.set_page_config(layout="wide")

st.title('How to layout your Streamlit app')

with st.expander('About this app'):
  st.write('This app shows the various ways on how you can layout your Streamlit app.')
  st.image('https://streamlit.io/images/brand/streamlit-logo-secondary-colormark-darktext.png', width=250)

st.sidebar.header('Input')
user_name = st.sidebar.text_input('What is your name?')
user_emoji = st.sidebar.selectbox('Choose an emoji', ['', '😄', '😆', '😊', '😍', '😴', '😕', '😱'])
user_food = st.sidebar.selectbox('What is your favorite food?', ['', 'Tom Yum Kung', 'Burrito', 'Lasagna', 'Hamburger', 'Pizza'])

st.header('Output')

col1, col2, col3 = st.columns(3)

with col1:
  if user_name != '':
    st.write(f'👋 Hello {user_name}!')
  else:
    st.write('👈  Please enter your **name**!')

with col2:
  if user_emoji != '':
    st.write(f'{user_emoji} is your favorite **emoji**!')
  else:
    st.write('👈 Please choose an **emoji**!')

with col3:
  if user_food != '':
    st.write(f'🍴 **{user_food}** is your favorite **food**!')
  else:
    st.write('👈 Please choose your favorite **food**!')`

## **Построчное объяснение**

Самое первое, что нужно сделать при создании приложения Streamlit, это импортировать библиотеку `streamlit` как `st`, например:

`import streamlit as st`

Мы начнем с определения макета страницы, который будет отображаться в режиме `wide`, который позволяет содержимому страницы расширяться до ширины браузера.

`st.set_page_config(layout="wide")`

Далее мы дадим приложению Streamlit название.

`st.title('How to layout your Streamlit app')`

Раскрывающееся поле под названием `About this app` находится под заголовком приложения. После расширения, внутри мы увидим дополнительные детали.

`with st.expander('About this app'):
  st.write('This app shows the various ways on how you can layout your Streamlit app.')
  st.image('https://streamlit.io/images/brand/streamlit-logo-secondary-colormark-darktext.png', width=250)`

Виджеты ввода для приема пользовательского ввода размещаются на боковой панели, как указано с помощью команды `st.sidebar` перед командами Streamlit `text_input` и `selectbox`. Входные значения, введенные или выбранные пользователем, назначаются и сохраняются в переменных `user_name`, `user_emoji`, и `user_food`.

`st.sidebar.header('Input')
user_name = st.sidebar.text_input('What is your name?')
user_emoji = st.sidebar.selectbox('Choose an emoji', ['', '😄', '😆', '😊', '😍', '😴', '😕', '😱'])
user_food = st.sidebar.selectbox('What is your favorite food?', ['', 'Tom Yum Kung', 'Burrito', 'Lasagna', 'Hamburger', 'Pizza'])`

Наконец, мы создадим 3 столбца с помощью команды `st.columns`, которая соответствует `col1`, `col2`, и `col3`. Затем мы назначаем содержимое каждому столбцу, создавая отдельные блоки кода, начиная с оператора `with`. Под этим мы создаем условные операторы, которые отображают 1 из 2 альтернативных текстов в зависимости от того, предоставил ли пользователь свои входные данные (указанные на боковой панели) или нет. По умолчанию на странице отображается текст под оператором `else`. После ввода данных соответствующая информация которую пользователь предоставляет приложению отображается под текстом заголовка `Output`.

`st.header('Output')

col1, col2, col3 = st.columns(3)

with col1:
  if user_name != '':
    st.write(f'👋 Hello {user_name}!')
  else:
    st.write('👈  Please enter your **name**!')

with col2:
  if user_emoji != '':
    st.write(f'{user_emoji} is your favorite **emoji**!')
  else:
    st.write('👈 Please choose an **emoji**!')

with col3:
  if user_food != '':
    st.write(f'🍴 **{user_food}** is your favorite **food**!')
  else:
    st.write('👈 Please choose your favorite **food**!')`

Также стоит отметить, что строки `f` использовались для объединения предварительно подготовленного текста с предоставленными пользователем значениями.

## **Дальнейшее чтение**

- [Макеты и контейнеры](https://docs.streamlit.io/library)