# Day 22

# **st.form**

`st.form` creates a form that batches elements together with a "Submit" button.

Typically, whenever a user interacts with a widget, the Streamlit app is rerun.

A form is a container that visually groups other elements and widgets together, and contains a Submit button. Herein, a user can interacts with one or more widgets for as many times as they like without causing a rerun. Finally, when the form's Submit button is pressed, all widget values inside the form will be sent to Streamlit in a single batch.

To add elements to a form object, you can use the `with` notation (preferred) or you could use it as an object notation by just calling methods directly on the form (by first assigning it to a variable and subsequently applying Streamlit methods on it). See in the example app.

Forms have a few constraints:

- Every form must contain a `st.form_submit_button`.
- `st.button` and `st.download_button` cannot be added to a form.
- Forms can appear anywhere in your app (sidebar, columns, etc), but they cannot be embedded inside other forms.

For more information about forms, check out our [blog post](https://blog.streamlit.io/introducing-submit-button-and-forms/).

## **Demo app**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Code**

Here's how to use `st.form`:

`import streamlit as st

st.title('st.form')

# Full example of using the with notation
st.header('1. Example of using `with` notation')
st.subheader('Coffee machine')

with st.form('my_form'):
    st.subheader('**Order your coffee**')
    
    # Input widgets
    coffee_bean_val = st.selectbox('Coffee bean', ['Arabica', 'Robusta'])
    coffee_roast_val = st.selectbox('Coffee roast', ['Light', 'Medium', 'Dark'])
    brewing_val = st.selectbox('Brewing method', ['Aeropress', 'Drip', 'French press', 'Moka pot', 'Siphon'])
    serving_type_val = st.selectbox('Serving format', ['Hot', 'Iced', 'Frappe'])
    milk_val = st.select_slider('Milk intensity', ['None', 'Low', 'Medium', 'High'])
    owncup_val = st.checkbox('Bring own cup')
    
    # Every form must have a submit button
    submitted = st.form_submit_button('Submit')

if submitted:
    st.markdown(f'''
        ☕ You have ordered:
        - Coffee bean: `{coffee_bean_val}`
        - Coffee roast: `{coffee_roast_val}`
        - Brewing: `{brewing_val}`
        - Serving type: `{serving_type_val}`
        - Milk: `{milk_val}`
        - Bring own cup: `{owncup_val}`
        ''')
else:
    st.write('☝️ Place your order!')

# Short example of using an object notation
st.header('2. Example of object notation')

form = st.form('my_form_2')
selected_val = form.slider('Select a value')
form.form_submit_button('Submit')

st.write('Selected value: ', selected_val)`

## **Line-by-line explanation**

The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` like so:

`import streamlit as st`

This is followed by creating a title text for the app:

`st.title('st.form')`

### **First example**

Let's start with the first example, here we'll apply the `st.form` command via the `with` notation. Inside the form, we'll start with writing a subheader `Order your coffee` then create several input widgets (`st.selectbox`, `st.select_slider` and `st.checkbox`) to collect information about the coffee order. Finally, a submit button is created via the `st.form_submit_button` command, which when clicked on will send all user input as a single batch of information to the app for processing.

`# Full example of using the with notation
st.header('1. Example of using `with` notation')
st.subheader('Coffee machine')

with st.form('my_form'):
    st.subheader('**Order your coffee**')

    # Input widgets
    coffee_bean_val = st.selectbox('Coffee bean', ['Arabica', 'Robusta'])
    coffee_roast_val = st.selectbox('Coffee roast', ['Light', 'Medium', 'Dark'])
    brewing_val = st.selectbox('Brewing method', ['Aeropress', 'Drip', 'French press', 'Moka pot', 'Siphon'])
    serving_type_val = st.selectbox('Serving format', ['Hot', 'Iced', 'Frappe'])
    milk_val = st.select_slider('Milk intensity', ['None', 'Low', 'Medium', 'High'])
    owncup_val = st.checkbox('Bring own cup')
    
    # Every form must have a submit button.
    submitted = st.form_submit_button('Submit')`

Next, we'll add the logic of what happen's after the submit button is clicked on. By default, whenever the Streamlit app is loaded the `else` statement will be run and we see a message `☝️ Place your order!`. Whereas upon clicking on the submit button, all user provided input via the various widgets are stored in several variables (e.g. `coffee_bean_val`, `coffee_roast_val`, etc.) and printed out via the `st.markdown` command with the help of f-string.

`if submitted:
    st.markdown(f'''
        ☕ You have ordered:
        - Coffee bean: `{coffee_bean_val}`
        - Coffee roast: `{coffee_roast_val}`
        - Brewing: `{brewing_val}`
        - Serving type: `{serving_type_val}`
        - Milk: `{milk_val}`
        - Bring own cup: `{owncup_val}`
        ''')
else:
    st.write('☝️ Place your order!')`

### **Second example**

Let's now proceed to the second example on using the `st.form` as an object notation. Here, the `st.form` command is assigned to the `form` variable. Subsequently, various Streamlit commands such as `slider` or `form_submit_button` is applied on the `form` variable.

`# Short example of using an object notation
st.header('2. Example of object notation')

form = st.form('my_form_2')
selected_val = form.slider('Select a value')
form.form_submit_button('Submit')

st.write('Selected value: ', selected_val)`

## **Further reading**

- `[st.form](https://docs.streamlit.io/library/api-reference/control-flow/st.form)`
- [Introducing Submit button and Forms](https://blog.streamlit.io/introducing-submit-button-and-forms/)

# **st.form**

`st.form` создает форму, которая объединяет элементы вместе с кнопкой "Отправить".

Как правило, всякий раз, когда пользователь взаимодействует с виджетом, приложение Streamlit перезапускается.

Форма — это контейнер, который визуально группирует вместе другие элементы и виджеты и содержит кнопку «Отправить». Здесь пользователь может взаимодействовать с одним или несколькими виджетами столько раз сколько ему нужно, без повторного запуска. Наконец, когда на форме нажата кнопка «Отправить», все значения виджетов внутри формы будут отправлены в Streamlit одним пакетом.

Чтобы добавить элементы в объект формы, вы можете использовать нотацию `with` (предпочтительно) или использовать ее как нотацию объекта, просто вызывая методы непосредственно в форме (сначала присваивая ее переменной, а затем применяя методы Streamlit). См. пример приложения.

Формы имеют несколько ограничений:

- Каждая форма должна содержать `st.form_submit_button`.
- `st.button` и `st.download_button` нельзя добавить в форму.
- Формы могут появляться в любом месте вашего приложения (боковая панель, столбцы, и т. д.), но их нельзя встраивать в другие формы.

Для получения дополнительной информации о формах ознакомьтесь с нашим [блогом](https://blog.streamlit.io/introduction-submit-button-and-forms/).

## **Демонстрационное приложение**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Как использовать `st.form`:

`import streamlit as st

st.title('st.form')

# Full example of using the with notation
st.header('1. Example of using `with` notation')
st.subheader('Coffee machine')

with st.form('my_form'):
    st.subheader('**Order your coffee**')
    
    # Input widgets
    coffee_bean_val = st.selectbox('Coffee bean', ['Arabica', 'Robusta'])
    coffee_roast_val = st.selectbox('Coffee roast', ['Light', 'Medium', 'Dark'])
    brewing_val = st.selectbox('Brewing method', ['Aeropress', 'Drip', 'French press', 'Moka pot', 'Siphon'])
    serving_type_val = st.selectbox('Serving format', ['Hot', 'Iced', 'Frappe'])
    milk_val = st.select_slider('Milk intensity', ['None', 'Low', 'Medium', 'High'])
    owncup_val = st.checkbox('Bring own cup')
    
    # Every form must have a submit button
    submitted = st.form_submit_button('Submit')

if submitted:
    st.markdown(f'''
        ☕ You have ordered:
        - Coffee bean: `{coffee_bean_val}`
        - Coffee roast: `{coffee_roast_val}`
        - Brewing: `{brewing_val}`
        - Serving type: `{serving_type_val}`
        - Milk: `{milk_val}`
        - Bring own cup: `{owncup_val}`
        ''')
else:
    st.write('☝️ Place your order!')

# Short example of using an object notation
st.header('2. Example of object notation')

form = st.form('my_form_2')
selected_val = form.slider('Select a value')
form.form_submit_button('Submit')

st.write('Selected value: ', selected_val)`

## **Построчное объяснение**

Самое первое, что нужно сделать при создании приложения Streamlit, это импортировать библиотеку `streamlit` как `st`, например:

`import streamlit as st`

Затем следует создание текста заголовка для приложения:

`st.title('st.form')`

### **Первый пример**

Начнем с первого примера—здесь мы применим команду `st.form` через нотацию `with`. Внутри формы мы начнем с написания подзаголовка `Order your coffee`, затем создадим несколько виджетов ввода (`st.selectbox`, `st.select_slider` и `st.checkbox`) для сбора информации о заказе кофе. Наконец, с помощью команды `st.form_submit_button` создается кнопка отправки, которая при нажатии отправляет ввод пользователя в виде единого пакета информации в приложение для обработки.

`# Full example of using the with notation
st.header('1. Example of using `with` notation')
st.subheader('Coffee machine')

with st.form('my_form'):
    st.subheader('**Order your coffee**')

    # Input widgets
    coffee_bean_val = st.selectbox('Coffee bean', ['Arabica', 'Robusta'])
    coffee_roast_val = st.selectbox('Coffee roast', ['Light', 'Medium', 'Dark'])
    brewing_val = st.selectbox('Brewing method', ['Aeropress', 'Drip', 'French press', 'Moka pot', 'Siphon'])
    serving_type_val = st.selectbox('Serving format', ['Hot', 'Iced', 'Frappe'])
    milk_val = st.select_slider('Milk intensity', ['None', 'Low', 'Medium', 'High'])
    owncup_val = st.checkbox('Bring own cup')
    
    # Every form must have a submit button.
    submitted = st.form_submit_button('Submit')`

Далее мы добавим логику того, что происходит после нажатия кнопки отправки. По умолчанию, всякий раз, когда загружается приложение Streamlit, будет выполняться оператор else, и мы видим сообщение `☝️ Разместите заказ!`. При нажатии на кнопку отправки все введенные пользователем данные через различные виджеты сохраняются в нескольких переменных (например, `coffee_bean_val`, `coffee_roast_val` и т. д.) и распечатываются с помощью команды `st.markdown` с помощью f-string.

`if submitted:
    st.markdown(f'''
        ☕ You have ordered:
        - Coffee bean: `{coffee_bean_val}`
        - Coffee roast: `{coffee_roast_val}`
        - Brewing: `{brewing_val}`
        - Serving type: `{serving_type_val}`
        - Milk: `{milk_val}`
        - Bring own cup: `{owncup_val}`
        ''')
else:
    st.write('☝️ Place your order!')`

### **Второй пример**

Давайте теперь перейдем ко второму примеру использования `st.form` в качестве обозначен я объекта. Здесь команда `st.form` назначается переменной `form`. Впоследствии к переменной `form` применяются различные команды Streamlit, такие как `slider` или `form_submit_button`.

`# Short example of using an object notation
st.header('2. Example of object notation')

form = st.form('my_form_2')
selected_val = form.slider('Select a value')
form.form_submit_button('Submit')

st.write('Selected value: ', selected_val)`

## **Дальнейшее чтение**

- `[st.form](https://docs.streamlit.io/library/api-reference/control-flow/st.form)`
- [Представляем кнопку «Отправить» и Формы](https://blog.streamlit.io/introduction-submit-button-and-forms/)