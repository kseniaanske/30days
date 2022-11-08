# Day 18

# **st.file_uploader**

`st.file_uploader` displays a file uploader widget [[1](https://docs.streamlit.io/library/api-reference/widgets/st.file_uploader)].

By default, uploaded files are limited to 200MB. You can configure this using the server.maxUploadSize config option. For more info on how to set config options, see [[2](https://docs.streamlit.io/library/advanced-features/configuration#set-configuration-options)].

## **Demo app**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Code**

Here's how to use `st.file_uploader`:

`import streamlit as st
import pandas as pd

st.title('st.file_uploader')

st.subheader('Input CSV')
uploaded_file = st.file_uploader("Choose a file")

if uploaded_file is not None:
  df = pd.read_csv(uploaded_file)
  st.subheader('DataFrame')
  st.write(df)
  st.subheader('Descriptive Statistics')
  st.write(df.describe())
else:
  st.info('☝️ Upload a CSV file')`

## **Line-by-line explanation**

The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` and other prerequisite library like so:

`import streamlit as st
import pandas as pd`

This is followed by creating a title text for the app:

`st.title('st.file_uploader')`

Next, we'll use `st.file_uploader` to display a file uploader widget for accepting user input file:

`st.subheader('Input CSV')
uploaded_file = st.file_uploader("Choose a file")`

Finally, we define conditional statements for initially displaying a welcome message inviting users to upload their file (as implemented in the `else` condition). Upon file upload, the `if` statements are activated and the CSV file is read by the `pandas` library and displayed via the `st.write` command.

`if uploaded_file is not None:
  df = pd.read_csv(uploaded_file)
  st.subheader('DataFrame')
  st.write(df)
  st.subheader('Descriptive Statistics')
  st.write(df.describe())
else:
  st.info('☝️ Upload a CSV file')`

## **Further reading**

1. `[st.file_uploader](https://docs.streamlit.io/library/api-reference/widgets/st.file_uploader)`
2. [Set configuration options](https://docs.streamlit.io/library/advanced-features/configuration#set-configuration-options)

# **st.file_uploader**

`st.file_uploader` отображает виджет загрузки файлов [[1](https://docs.streamlit.io/library/api-reference/widgets/st.file_uploader)].

По умолчанию загруженные файлы не могут превышать 200 МБ. Вы можете настроить это с помощью параметра конфигурации server.maxUploadSize. Для получения дополнительной информации о том, как установить параметры конфигурации, см. [[2](https://docs.streamlit.io/library/advanced-features/configuration#set-configuration-options)].

## **Демонстрационное приложение**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Вот как использовать `st.file_uploader`:

`import streamlit as st
import pandas as pd

st.title('st.file_uploader')

st.subheader('Input CSV')
uploaded_file = st.file_uploader("Choose a file")

if uploaded_file is not None:
  df = pd.read_csv(uploaded_file)
  st.subheader('DataFrame')
  st.write(df)
  st.subheader('Descriptive Statistics')
  st.write(df.describe())
else:
  st.info('☝️ Upload a CSV file')`

## **Построчное объяснение**

Самое первое, что нужно сделать при создании приложения Streamlit, это импортировать библиотеку `streamlit` как `st` и другие необходимые библиотеки, например:

`import streamlit as st
import pandas as pd`

Затем следует создание текста заголовка для приложения:

`st.title('st.file_uploader')`

Далее мы будем использовать `st.file_uploader`, чтобы отобразить виджет загрузки файлов для принятия файла, введенного пользователем:

`st.subheader('Input CSV')
uploaded_file = st.file_uploader("Choose a file")`

Наконец, мы определим условных операторов для первоначального отображения приветственного сообщения, предлагающего пользователям загрузить свой файл (как реализовано в условии `else` ). После загрузки файла операторы `if` активируются, и файл CSV считывается библиотекой `pandas` и отображается с помощью команды `st.write`.

`if uploaded_file is not None:
  df = pd.read_csv(uploaded_file)
  st.subheader('DataFrame')
  st.write(df)
  st.subheader('Descriptive Statistics')
  st.write(df.describe())
else:
  st.info('☝️ Upload a CSV file')`

## **Дальнейшее чтение**

1. `[st.file_uploader](https://docs.streamlit.io/library/api-reference/widgets/st.file_uploader)`
2. [Установить параметры конфигурации](https://docs.streamlit.io/library/advanced-features/configuration#set-configuration-options)