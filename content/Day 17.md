# Day 17

# **st.secrets**

`st.secrets` allows you to store confidential information such as API keys, database passwords or other credentials.

## **Demo app**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Code**

Here's how to use `st.secrets`:

`import streamlit as st

st.title('st.secrets')

st.write(st.secrets['message'])`

## **Line-by-line explanation**

The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` like so:

`import streamlit as st`

This is followed by creating a title text for the app:

`st.title('st.secrets')`

Finally, we'll be displaying the stored secrets:

`st.write(st.secrets['message'])`

It should be noted that, secrets can be stored in Streamlit Cloud as shown in the screenshots shown below.

If working locally, they can be stored in `.streamlit/secrets.toml`, but make sure to avoid uploading this to a GitHub repo when deploying the app.

## **Further reading**

- [Add secrets to your Streamlit apps](https://blog.streamlit.io/secrets-in-sharing-apps/)
- [Secrets management](https://docs.streamlit.io/streamlit-cloud/get-started/deploy-an-app/connect-to-data-sources/secrets-management)

# **ст.секреты**

`st.secrets` позволяет хранить конфиденциальную информацию, такую как ключи API, пароли к базам данных или другие учетные данные.

## **Демонстрационное приложение**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Вот как использовать `st.secrets`:

`import streamlit as st

st.title('st.secrets')

st.write(st.secrets['message'])`

## **Построчное объяснение**

Самое первое, что нужно сделать при создании приложения Streamlit, это импортировать библиотеку `streamlit` как `st`, например:

`import streamlit as st`

Затем следует создание текста заголовка для приложения:

`st.title('st.secrets')`

Наконец, мы будем отображать сохраненные секреты:

`st.write(st.secrets['message'])`

Следует отметить, что секреты могут храниться в облаке Streamlit, как показано на скриншотах ниже.

Если вы работаете локально, их можно хранить в `.streamlit/secrets.toml`, но не загружайте его в репозиторий GitHub при развертывании приложения.

## **Дальнейшее чтение**

- [Добавьте секреты в свои приложения Streamlit](https://blog.streamlit.io/secrets-in-sharing-apps/)
- [Управление секретами](https://docs.streamlit.io/streamlit-cloud/get-started/deploy-an-app/connect-to-data-sources/secrets-management)