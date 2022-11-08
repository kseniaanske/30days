# Day 14

# **Streamlit Components**

Components are third-party Python modules that extend what's possible with Streamlit [[1](https://docs.streamlit.io/library/components)].

## **What Streamlit components are available?**

There are several dozens of Streamlit components featured on Streamlit's website [[2](https://streamlit.io/components)].

Fanilo (a Streamlit Creator) curated an amazing list of Streamlit components on a wiki post [[3](https://discuss.streamlit.io/t/streamlit-components-community-tracker/4634)] that lists about 85 Streamlit components as of April 2022.

## **How to use?**

Streamlit components are just a pip-install away.

In this tutorial, let's get you started in using the `streamlit_pandas_profiling` component [[4](https://share.streamlit.io/okld/streamlit-gallery/main?p=pandas-profiling)].

### **Install the component**

`pip install streamlit_pandas_profiling`

## **Demo app**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Code**

Here's how to build a Streamlit app using a component:

`import streamlit as st
import pandas as pd
import pandas_profiling
from streamlit_pandas_profiling import st_profile_report

st.header('`streamlit_pandas_profiling`')

df = pd.read_csv('https://raw.githubusercontent.com/dataprofessor/data/master/penguins_cleaned.csv')

pr = df.profile_report()
st_profile_report(pr)`

## **Line-by-line explanation**

The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` as well as other libraries used in the app like so:

`import streamlit as st
import pandas as pd
import pandas_profiling
from streamlit_pandas_profiling import st_profile_report`

This is followed by creating a header text for the app:

`st.header('`streamlit_pandas_profiling`')`

Next, we load in the Penguins dataset using the `read_csv` command of `pandas`.

`df = pd.read_csv('https://raw.githubusercontent.com/dataprofessor/data/master/penguins_cleaned.csv')`

Finally, the pandas profiling report is generated via the `profile_report()` command and displayed using `st_profile_report`:

`pr = df.profile_report()
st_profile_report(pr)`

## **Making your own Components**

If you're interested in making your own component, please check out the following resources:

- [Create a Component](https://docs.streamlit.io/library/components/create)
- [Publish a Component](https://docs.streamlit.io/library/components/publish)
- [Components API](https://docs.streamlit.io/library/components/components-api)
- [Blog post on Components](https://blog.streamlit.io/introducing-streamlit-components/)

Alternatively, if you prefer to learn using videos, our engineer Tim Conkling has put together some amazing tutorials:

- [How to build a Streamlit component | Part 1: Setup and Architecture](https://youtu.be/BuD3gILJW-Q)
- [How to build a Streamlit component | Part 2: Part 2: Make a Slider Widget](https://youtu.be/QjccJl_7Jco)

## **Further reading about Components**

1. [Streamlit Components - API Documentation](https://docs.streamlit.io/library/components)
2. [Featured Streamlit Components](https://streamlit.io/components)
3. [Streamlit Components - Community Tracker](https://discuss.streamlit.io/t/streamlit-components-community-tracker/4634)
4. `[streamlit_pandas_profiling](https://share.streamlit.io/okld/streamlit-gallery/main?p=pandas-profiling)`

# **Компоненты Streamlit**

Компоненты—это сторонние модули для Python, расширяющие возможности Streamlit [[1](https://docs.streamlit.io/library/components)].

## **Какие компоненты Streamlit доступны?**

На сайте Streamlit [[2](https://streamlit.io/components)] представлено несколько десятков компонентов Streamlit.

Фанило (Streamlit Creator) курировал удивительный список компонентов Streamlit в вики-сообщении [[3](https://discuss.streamlit.io/t/streamlit-components-community-tracker/4634)], в котором перечислены около 85 компонентов Streamlit по состоянию на апрель 2022 года.

## **Как использовать?**

Компоненты Streamlit находятся всего в нескольких шагах от установки.

В этом руководстве мы познакомим вас с использованием компонента streamlit_pandas_profiling [[4](https://share.streamlit.io/okld/streamlit-gallery/main?p=pandas-profiling)].

### **Установить компонент**

`pip install streamlit_pandas_profiling`

## **Демонстрационное приложение**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Как создать приложение Streamlit с помощью компонента:

`import streamlit as st
import pandas as pd
import pandas_profiling
from streamlit_pandas_profiling import st_profile_report

st.header('`streamlit_pandas_profiling`')

df = pd.read_csv('https://raw.githubusercontent.com/dataprofessor/data/master/penguins_cleaned.csv')

pr = df.profile_report()
st_profile_report(pr)`

## **Построчное объяснение**

Самое первое, что нужно сделать при создании приложения Streamlit, это импортировать библиотеку `streamlit` как `st`, а также другие библиотеки используемые в приложении, следующим образом:

`import streamlit as st
import pandas as pd
import pandas_profiling
from streamlit_pandas_profiling import st_profile_report`

Затем следует создание текста заголовка для приложения:

`st.header('`streamlit_pandas_profiling`')`

Затем мы загружаем набор данных Penguins с помощью команды read_csv для pandas.

`df = pd.read_csv('https://raw.githubusercontent.com/dataprofessor/data/master/penguins_cleaned.csv')`

Наконец, отчет о профилировании pandas создается с помощью команды `profile_report()` и отображается с помощью `st_profile_report`:

`pr = df.profile_report()
st_profile_report(pr)`

## **Создание собственных компонентов**

Если вы заинтересованы в создании собственного компонента, ознакомьтесь со следующими ресурсами:

- [Создать компонент](https://docs.streamlit.io/library/components/create)
- [Опубликовать компонент](https://docs.streamlit.io/library/components/publish)
- [API компонентов](https://docs.streamlit.io/library/components/components-api)
- [Блог о компонентах](https://blog.streamlit.io/introduction-streamlit-components/)

В качестве альтернативы, если вы предпочитаете учиться с помощью видео, наш инженер Тим Конклинг сделал несколько замечательных руководств:

- [Как создать компонент Streamlit | Часть 1: Настройка и архитектура](https://youtu.be/BuD3gILJW-Q)
- [Как создать компонент Streamlit | Часть 2: Часть 2: Создание виджета-слайдера](https://youtu.be/QjccJl_7Jco)

## **Дополнительная информация о компонентах**

1. [Компоненты Streamlit — Документация по API](https://docs.streamlit.io/library/components)
2. [Избранные компоненты Streamlit](https://streamlit.io/components) 
3. [Компоненты Streamlit — трекер сообщества](https://discuss.streamlit.io/t/streamlit-components-community-tracker/4634)
4. `[streamlit_pandas_profiling](https://share.streamlit.io/okld/streamlit-gallery/main?p=pandas-profiling)`