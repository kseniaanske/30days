# Day 16

# **Customizing the theme of Streamlit apps**

We can customize the theme by adjusting parameters in `config.toml`, which is a configuration file stored in the same folder as the app in the `.streamlit` folder.

## **What we're building?**

A simple app that shows the result of our theme customization. This is made possible by customizing the HTML HEX code inside the `[.streamlit/config.toml](https://github.com/dataprofessor/streamlit-custom-theme/blob/master/.streamlit/config.toml)` file.

## **Demo app**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Code**

Here's the code to the `[streamlit_app.py](https://github.com/dataprofessor/streamlit-custom-theme/blob/master/streamlit_app.py)` file:

`import streamlit as st

st.title('Customizing the theme of Streamlit apps')

st.write('Contents of the `.streamlit/config.toml` file of this app')

st.code("""
[theme]
primaryColor="#F39C12"
backgroundColor="#2E86C1"
secondaryBackgroundColor="#AED6F1"
textColor="#FFFFFF"
font="monospace"
""")

number = st.sidebar.slider('Select a number:', 0, 10, 5)
st.write('Selected number from slider widget is:', number)`

Here's the code to the `[.streamlit/config.toml](https://github.com/dataprofessor/streamlit-custom-theme/blob/master/.streamlit/config.toml)` file:

`[theme]
primaryColor="#F39C12"
backgroundColor="#2E86C1"
secondaryBackgroundColor="#AED6F1"
textColor="#FFFFFF"
font="monospace"`

## **Line-by-line explanation**

The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` like so:

`import streamlit as st`

This is followed by creating a title text for the app:

`st.title('Theming with config.toml')`

Next, we're going to show the contents of the `.streamlit/config.toml` file which we'll first display a note of this via `st.write` followed by the actual code via `st.code`:

`st.write('Contents of the ./streamlit/config.toml file of this app')

st.code("""
[theme]
primaryColor="#F39C12"
backgroundColor="#2E86C1"
secondaryBackgroundColor="#AED6F1"
textColor="#FFFFFF"
font="monospace"
""")`

Finally, we're creating a slider widget in the sidebar followed by displaying the selected number:

`number = st.sidebar.slider('Select a number:', 0, 10, 5)
st.write('Selected number from slider widget is:', number)`

Let's now take a look at the custom colors that we've used in this app, which is specified in the `.streamlit/config.toml` file:

- `primaryColor="#F39C12"` - This sets the primary color to orange. Notice the orange colors in the slider widget.
- `backgroundColor="#2E86C1"` - This sets the background color to blue. Notice the main panel has a blue background color.
- `secondaryBackgroundColor="#AED6F1"` - This sets the secondary background color to dark gray. Notice the gray background color of the sidebar and the background color of the code box in the main panel.
- `textColor="#FFFFFF"` - The text color is set to white.
- `font="monospace"` - This sets the font to monospace.

## **Further reading**

- [Theming](https://docs.streamlit.io/library/advanced-features/theming)
- [HTML Color Codes](https://htmlcolorcodes.com/) is a great tool for selecting colors of interest.

# **Настройка темы приложений Streamlit**

Мы можем настроить тему, настроив параметры в `config.toml`, который представляет собой файл конфигурации хранящийся в той же папке что и приложение—в папке `.streamlit`.

## **Что мы строим?**

Простое приложение, которое показывает результат настройки нашей темы. Это стало возможным благодаря настройке HTML HEX-кода внутри `[.streamlit/config.toml](https://github.com/dataprofessor/streamlit-custom-theme/blob/master/.streamlit/config.toml)` файла.

## **Демонстрационное приложение**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Вот код файла `[streamlit_app.py](https://github.com/dataprofessor/streamlit-custom-theme/blob/master/streamlit_app.py)`:

`import streamlit as st

st.title('Customizing the theme of Streamlit apps')

st.write('Contents of the `.streamlit/config.toml` file of this app')

st.code("""
[theme]
primaryColor="#F39C12"
backgroundColor="#2E86C1"
secondaryBackgroundColor="#AED6F1"
textColor="#FFFFFF"
font="monospace"
""")

number = st.sidebar.slider('Select a number:', 0, 10, 5)
st.write('Selected number from slider widget is:', number)`

Вот код файла [.streamlit/config.toml](https://github.com/dataprofessor/streamlit-custom-theme/blob/master/.streamlit/config.toml):

`[theme]
primaryColor="#F39C12"
backgroundColor="#2E86C1"
secondaryBackgroundColor="#AED6F1"
textColor="#FFFFFF"
font="monospace"`

## **Построчное объяснение**

Самое первое, что нужно сделать при создании приложения Streamlit, это импортировать библиотеку `streamlit` как `st`, например:

`import streamlit as st`

Затем следует создание текста заголовка для приложения:

`st.title('Theming with config.toml')`

Далее мы собираемся показать содержимое файла `.streamlit/config.toml`, в котором мы сначала отобразим примечание через `st.write`, а затем сам код через `st.code`:

`st.write('Contents of the ./streamlit/config.toml file of this app')

st.code("""
[theme]
primaryColor="#F39C12"
backgroundColor="#2E86C1"
secondaryBackgroundColor="#AED6F1"
textColor="#FFFFFF"
font="monospace"
""")`

Наконец, мы создаем виджет слайдера на боковой панели, после чего отображается выбранный номер:

`number = st.sidebar.slider('Select a number:', 0, 10, 5)
st.write('Selected number from slider widget is:', number)`

Теперь давайте посмотрим на пользовательские цвета, которые мы использовали в этом приложении, указанные в файле `.streamlit/config.toml`:

- `primaryColor="#F39C12"` – Это устанавливает оранжевый как основной цвет. Обратите внимание на оранжевые цвета в виджете слайдера.
- `backgroundColor="#2E86C1"` – Это устанавливает синий цвет фона. Обратите внимание, что основная панель имеет синий цвет фона.
- `secondaryBackgroundColor="#AED6F1"` – Это устанавливает темно-серый цвет вторичного фона. Обратите внимание на серый цвет фона боковой панели и цвет фона поля кода на главной панели.
- `textColor="#FFFFFF"` – Это устанавливает белый цвет текста.
- `font="monospace"` – Это устанавливает моноширинный шрифт.

## **Дальнейшее чтение**

- [Тематика](https://docs.streamlit.io/library/advanced-features/theming)
- [Цветовые коды HTML](https://htmlcolorcodes.com/) это отличный инструмент для выбора цветов.