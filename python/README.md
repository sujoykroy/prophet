# Prophet: Automatic Forecasting Procedure

Prophet is a procedure for forecasting time series data based on an additive model where non-linear trends are fit with yearly, weekly, and daily seasonality, plus holiday effects. It works best with time series that have strong seasonal effects and several seasons of historical data. Prophet is robust to missing data and shifts in the trend, and typically handles outliers well.

Prophet is [open source software](https://code.facebook.com/projects/>)  released by [Facebook's Core Data Science team ](https://research.fb.com/category/data-science/).

Full documentation and examples available at the homepage: https://facebook.github.io/prophet/

## Important links

- HTML documentation: https://facebook.github.io/prophet/docs/quick_start.html
- Issue tracker: https://github.com/facebook/prophet/issues
- Source code repository: https://github.com/facebook/prophet
- Implementation of Prophet in R: https://cran.r-project.org/package=prophet

## Other forecasting packages

- Rob Hyndman's [forecast package](http://robjhyndman.com/software/forecast/)
- [Statsmodels](http://statsmodels.sourceforge.net/)

## Installation
To install along with pre-compiling of stand model, use
```shell
python setup.py install --build-model
```
Alternatively, you can try following to create the model right in the source package.
```shell
python setup.py develop --build-model
```

To install the default compiled stan model, run

```shell
python setup.py install
```
Note:  Installation requires PyStan, which has its [own installation instructions](http://pystan.readthedocs.io/en/latest/installation_beginner.html).
On Windows, PyStan requires a compiler so you'll need to [follow the instructions](http://pystan.readthedocs.io/en/latest/windows.html).
 The key step is installing a recent [C++ compiler](https://visualstudio.microsoft.com/visual-cpp-build-tools/)

## Installation using Docker and docker-compose (via Makefile)

Simply type `make build` and if everything is fine you should be able to `make shell` or alternative jump directly to `make py-shell`. 

To run the tests, inside the container `cd python/fbprophet` and then `python -m unittest`

### Example usage

```python
  >>> from fbprophet import Prophet
  >>> m = Prophet()
  >>> m.fit(df)  # df is a pandas.DataFrame with 'y' and 'ds' columns
  >>> future = m.make_future_dataframe(periods=365)
  >>> m.predict(future)
  ```
