# Day 28

# **streamlit-shap**

`[streamlit-shap](https://github.com/snehankekre/streamlit-shap)` is a Streamlit component that provides a wrapper to display [SHAP](https://github.com/slundberg/shap) plots in [Streamlit](https://streamlit.io/).

The library is developed by our in-house staff [Snehan Kekre](https://github.com/snehankekre) who also maintains the [Streamlit Documentation](https://docs.streamlit.io/) website.

Firstly, install Streamlit (of course!) then pip install the `streamlit-shap` library:

`pip install streamlit
pip install streamlit-shap`

There are also other prerequisite libraries to install (e.g. `matplotlib`, `pandas`, `scikit-learn` and `xgboost`) if you haven't yet done so.

## **Demo app**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Code**

Here's how to use `streamlit-shap`:

`import streamlit as st
from streamlit_shap import st_shap
import shap
from sklearn.model_selection import train_test_split
import xgboost
import numpy as np
import pandas as pd

st.set_page_config(layout="wide")

@st.experimental_memodef load_data():
    return shap.datasets.adult()

@st.experimental_memodef load_model(X, y):
    X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=7)
    d_train = xgboost.DMatrix(X_train, label=y_train)
    d_test = xgboost.DMatrix(X_test, label=y_test)
    params = {
        "eta": 0.01,
        "objective": "binary:logistic",
        "subsample": 0.5,
        "base_score": np.mean(y_train),
        "eval_metric": "logloss",
        "n_jobs": -1,
    }
    model = xgboost.train(params, d_train, 10, evals = [(d_test, "test")], verbose_eval=100, early_stopping_rounds=20)
    return model

st.title("`streamlit-shap` for displaying SHAP plots in a Streamlit app")

with st.expander('About the app'):
    st.markdown('''[`streamlit-shap`](https://github.com/snehankekre/streamlit-shap) is a Streamlit component that provides a wrapper to display [SHAP](https://github.com/slundberg/shap) plots in [Streamlit](https://streamlit.io/). 
                    The library is developed by our in-house staff [Snehan Kekre](https://github.com/snehankekre) who also maintains the [Streamlit Documentation](https://docs.streamlit.io/) website.
                ''')

st.header('Input data')
X,y = load_data()
X_display,y_display = shap.datasets.adult(display=True)

with st.expander('About the data'):
    st.write('Adult census data is used as the example dataset.')
with st.expander('X'):
    st.dataframe(X)
with st.expander('y'):
    st.dataframe(y)

st.header('SHAP output')
 
# train XGBoost model
model = load_model(X, y)

# compute SHAP values
explainer = shap.Explainer(model, X)
shap_values = explainer(X)

with st.expander('Waterfall plot'):
    st_shap(shap.plots.waterfall(shap_values[0]), height=300)
with st.expander('Beeswarm plot'):
    st_shap(shap.plots.beeswarm(shap_values), height=300)

explainer = shap.TreeExplainer(model)
shap_values = explainer.shap_values(X)

with st.expander('Force plot'):
    st.subheader('First data instance')
    st_shap(shap.force_plot(explainer.expected_value, shap_values[0,:], X_display.iloc[0,:]), height=200, width=1000)
    st.subheader('First thousand data instance')
    st_shap(shap.force_plot(explainer.expected_value, shap_values[:1000,:], X_display.iloc[:1000,:]), height=400, width=1000)`

## **Line-by-line explanation**

The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` like so:

`import streamlit as st
from streamlit_shap import st_shap
import shap
from sklearn.model_selection import train_test_split
import xgboost
import numpy as np
import pandas as pd`

Next, we'll set the page layout to be wide such that contents in the Streamlit app can spread the full page width.

`st.set_page_config(layout="wide")`

Then, we'll load in a dataset from the `shap` library:

`@st.experimental_memodef load_data():
    return shap.datasets.adult()`

Subsequently, we'll definite a function called `load_model` for taking in the `X, y` matrix pair as input, perform data splitting to train/test sets, constructing a `DMatrix` and build an XGBoost model.

`@st.experimental_memodef load_model(X, y):
    X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=7)
    d_train = xgboost.DMatrix(X_train, label=y_train)
    d_test = xgboost.DMatrix(X_test, label=y_test)
    params = {
        "eta": 0.01,
        "objective": "binary:logistic",
        "subsample": 0.5,
        "base_score": np.mean(y_train),
        "eval_metric": "logloss",
        "n_jobs": -1,
    }
    model = xgboost.train(params, d_train, 10, evals = [(d_test, "test")], verbose_eval=100, early_stopping_rounds=20)
    return model`

The title of the Streamlit app is then displayed:

`st.title("`streamlit-shap` for displaying SHAP plots in a Streamlit app")`

An about expander box is implemented to provide details of the app:

`with st.expander('About the app'):
    st.markdown('''[`streamlit-shap`](https://github.com/snehankekre/streamlit-shap) is a Streamlit component that provides a wrapper to display [SHAP](https://github.com/slundberg/shap) plots in [Streamlit](https://streamlit.io/). 
                    The library is developed by our in-house staff [Snehan Kekre](https://github.com/snehankekre) who also maintains the [Streamlit Documentation](https://docs.streamlit.io/) website.
                ''')`

Here, we'll display the header text along with expander box of the `X` and `y` variables of the Input data:

`st.header('Input data')
X,y = load_data()
X_display,y_display = shap.datasets.adult(display=True)

with st.expander('About the data'):
    st.write('Adult census data is used as the example dataset.')
with st.expander('X'):
    st.dataframe(X)
with st.expander('y'):
    st.dataframe(y)`

Here, we'll display the header text for the forthcoming SHAP output:

`st.header('SHAP output')`

The XGBoost model is then built by using the `load_model` function that was just implemented above. Finally,

`# train XGBoost model
X,y = load_data()
X_display,y_display = shap.datasets.adult(display=True)

model = load_model(X, y)`

Here, we'll compute the SHAP values, which are then used to create the Waterfall and Beeswarm plots.

`# compute SHAP values
explainer = shap.Explainer(model, X)
shap_values = explainer(X)

with st.expander('Waterfall plot'):
    st_shap(shap.plots.waterfall(shap_values[0]), height=300)
with st.expander('Beeswarm plot'):
    st_shap(shap.plots.beeswarm(shap_values), height=300)`

Finally, the Tree SHAP algorithms is used to explain the output of ensemble tree models via the `shap.TreeExplainer` command and visualized via the `shap.force_plot` command:

`explainer = shap.TreeExplainer(model)
shap_values = explainer.shap_values(X)

with st.expander('Force plot'):
    st.subheader('First data instance')
    st_shap(shap.force_plot(explainer.expected_value, shap_values[0,:], X_display.iloc[0,:]), height=200, width=1000)
    st.subheader('First thousand data instance')
    st_shap(shap.force_plot(explainer.expected_value, shap_values[:1000,:], X_display.iloc[:1000,:]), height=400, width=1000)`

## **Further reading**

- `[streamlit-shap](https://github.com/snehankekre/streamlit-shap)`
- [SHAP](https://github.com/slundberg/shap)

# **streamlit-shap**

`[streamlit-shap](https://github.com/snehankekre/streamlit-shap)`—это компонент Streamlit, предоставляющий оболочку для отображения графиков [SHAP](https://github.com/slundberg/shap) в [Streamlit](https://streamlit.io/).

Библиотека разработана нашим сотрудником [Snehan Kekre](https://github.com/snehankekre), который также поддерживает веб-сайт [Streamlit Documentation](https://docs.streamlit.io/).

Во-первых, установите Streamlit (конечно же!), затем pip установите библиотеку `streamlit-shap`:

`pip install streamlit
pip install streamlit-shap`

Также установитe другие необходимые библиотеки (например, matplotlib, pandas, scikit-learn и xgboost), если вы еще этого не сделали.

## **Демонстрационное приложение**

[https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667](https://camo.githubusercontent.com/767be70c92254555bd347ab07908fec67854c2264b77702581bd230fd7eac54f/68747470733a2f2f7374617469632e73747265616d6c69742e696f2f6261646765732f73747265616d6c69745f62616467655f626c61636b5f77686974652e737667)

## **Код**

Как использовать `streamlit-shap`:

`import streamlit as st
from streamlit_shap import st_shap
import shap
from sklearn.model_selection import train_test_split
import xgboost
import numpy as np
import pandas as pd

st.set_page_config(layout="wide")

@st.experimental_memodef load_data():
    return shap.datasets.adult()

@st.experimental_memodef load_model(X, y):
    X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=7)
    d_train = xgboost.DMatrix(X_train, label=y_train)
    d_test = xgboost.DMatrix(X_test, label=y_test)
    params = {
        "eta": 0.01,
        "objective": "binary:logistic",
        "subsample": 0.5,
        "base_score": np.mean(y_train),
        "eval_metric": "logloss",
        "n_jobs": -1,
    }
    model = xgboost.train(params, d_train, 10, evals = [(d_test, "test")], verbose_eval=100, early_stopping_rounds=20)
    return model

st.title("`streamlit-shap` for displaying SHAP plots in a Streamlit app")

with st.expander('About the app'):
    st.markdown('''[`streamlit-shap`](https://github.com/snehankekre/streamlit-shap) is a Streamlit component that provides a wrapper to display [SHAP](https://github.com/slundberg/shap) plots in [Streamlit](https://streamlit.io/). 
                    The library is developed by our in-house staff [Snehan Kekre](https://github.com/snehankekre) who also maintains the [Streamlit Documentation](https://docs.streamlit.io/) website.
                ''')

st.header('Input data')
X,y = load_data()
X_display,y_display = shap.datasets.adult(display=True)

with st.expander('About the data'):
    st.write('Adult census data is used as the example dataset.')
with st.expander('X'):
    st.dataframe(X)
with st.expander('y'):
    st.dataframe(y)

st.header('SHAP output')
 
# train XGBoost model
model = load_model(X, y)

# compute SHAP values
explainer = shap.Explainer(model, X)
shap_values = explainer(X)

with st.expander('Waterfall plot'):
    st_shap(shap.plots.waterfall(shap_values[0]), height=300)
with st.expander('Beeswarm plot'):
    st_shap(shap.plots.beeswarm(shap_values), height=300)

explainer = shap.TreeExplainer(model)
shap_values = explainer.shap_values(X)

with st.expander('Force plot'):
    st.subheader('First data instance')
    st_shap(shap.force_plot(explainer.expected_value, shap_values[0,:], X_display.iloc[0,:]), height=200, width=1000)
    st.subheader('First thousand data instance')
    st_shap(shap.force_plot(explainer.expected_value, shap_values[:1000,:], X_display.iloc[:1000,:]), height=400, width=1000)`

## **Построчное объяснение**

Самое первое, что нужно сделать при создании приложения Streamlit, это импортировать библиотеку `streamlit` как `st`, например:

`import streamlit as st
from streamlit_shap import st_shap
import shap
from sklearn.model_selection import train_test_split
import xgboost
import numpy as np
import pandas as pd`

Затем мы сделаем макет страницы широким, чтобы содержимое в приложении Streamlit могло распространяться на всю ширину страницы.

`st.set_page_config(layout="wide")`

Затем мы загрузим набор данных из библиотеки `shap`:

`@st.experimental_memodef load_data():
    return shap.datasets.adult()`

Впоследствии мы определим функцию под названием `load_model` для приема пары матриц `X, y` в качестве входных данных и выполним разделение данных на обучающие/тестовые наборы, строя `DMatrix` и модель XGBoost.

`@st.experimental_memodef load_model(X, y):
    X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=7)
    d_train = xgboost.DMatrix(X_train, label=y_train)
    d_test = xgboost.DMatrix(X_test, label=y_test)
    params = {
        "eta": 0.01,
        "objective": "binary:logistic",
        "subsample": 0.5,
        "base_score": np.mean(y_train),
        "eval_metric": "logloss",
        "n_jobs": -1,
    }
    model = xgboost.train(params, d_train, 10, evals = [(d_test, "test")], verbose_eval=100, early_stopping_rounds=20)
    return model`

Затем отображается заголовок приложения Streamlit:

`st.title("`streamlit-shap` for displaying SHAP plots in a Streamlit app")`

Для предоставления подробной информации о приложении реализуем окно расширения:

`with st.expander('About the app'):
    st.markdown('''[`streamlit-shap`](https://github.com/snehankekre/streamlit-shap) is a Streamlit component that provides a wrapper to display [SHAP](https://github.com/slundberg/shap) plots in [Streamlit](https://streamlit.io/). 
                    The library is developed by our in-house staff [Snehan Kekre](https://github.com/snehankekre) who also maintains the [Streamlit Documentation](https://docs.streamlit.io/) website.
                ''')`

Здесь мы отобразим текст заголовка вместе с полем расширения переменных `x` и `y` у входных данных:

`st.header('Input data')
X,y = load_data()
X_display,y_display = shap.datasets.adult(display=True)

with st.expander('About the data'):
    st.write('Adult census data is used as the example dataset.')
with st.expander('X'):
    st.dataframe(X)
with st.expander('y'):
    st.dataframe(y)`

Здесь мы отобразим текст заголовка для предстоящего вывода SHAP:

`st.header('SHAP output')`

Затем модель XGBoost строится с использованием функции `load_model`, которая была реализована выше.

`# train XGBoost model
X,y = load_data()
X_display,y_display = shap.datasets.adult(display=True)

model = load_model(X, y)`

Здесь мы вычислим значения SHAP, которые затем используются для создания графиков «Водопад» и «Пчелиный рой».

`# compute SHAP values
explainer = shap.Explainer(model, X)
shap_values = explainer(X)

with st.expander('Waterfall plot'):
    st_shap(shap.plots.waterfall(shap_values[0]), height=300)
with st.expander('Beeswarm plot'):
    st_shap(shap.plots.beeswarm(shap_values), height=300)`

Наконец, алгоритмы Tree SHAP используются для объяснения выходных данных ансамблевых моделей деревьев с помощью команды `shap.TreeExplainer` и визуализируются с помощью команды `shap.force_plot`:

`explainer = shap.TreeExplainer(model)
shap_values = explainer.shap_values(X)

with st.expander('Force plot'):
    st.subheader('First data instance')
    st_shap(shap.force_plot(explainer.expected_value, shap_values[0,:], X_display.iloc[0,:]), height=200, width=1000)
    st.subheader('First thousand data instance')
    st_shap(shap.force_plot(explainer.expected_value, shap_values[:1000,:], X_display.iloc[:1000,:]), height=400, width=1000)`

## **Дальнейшее чтение**

- `[streamlit-shap](https://github.com/snehankekre/streamlit-shap)`
- [SHAP](https://github.com/slundberg/shap)