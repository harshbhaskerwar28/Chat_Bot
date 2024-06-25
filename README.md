**SET-1**

1. **Develop a model on Analysis of Variance (ANOVA) and table for the given data.**

```python
import pandas as pd
from scipy.stats import f_oneway

# Load the data
data = pd.read_csv('data.csv')

# Perform one-way ANOVA
groups = [data[data['group'] == 'A']['value'], data[data['group'] == 'B']['value'], data[data['group'] == 'C']['value']]
f_value, p_value = f_oneway(*groups)

print(f'F-value: {f_value:.2f}')
print(f'p-value: {p_value:.4f}')
```

**SET-2**

1. **Calculating the skewness of a data set by Pandas and SciPy.**

```python
import pandas as pd
from scipy.stats import skew

# Load the data
data = pd.read_csv('data.csv')

skewness_pandas = data['value'].skew()
print(f'Skewness (Pandas): {skewness_pandas:.2f}')

skewness_scipy = skew(data['value'])
print(f'Skewness (SciPy): {skewness_scipy:.2f}')
```

**SET-3**

1. **Design a model to calculate Percentile by SciPy and Stats Models.**

```python
import pandas as pd
from scipy.stats import percentileofscore
import statsmodels.api as sm

# Load the data
data = pd.read_csv('data.csv')

# Calculate percentile using SciPy
percentile_scipy = percentileofscore(data['value'], 75)
print(f'Percentile (SciPy): {percentile_scipy}th')

# Calculate percentile using StatsModels
percentile_statsmodels = sm.DistributionDistance().percentile(data['value'], 0.75)
print(f'Percentile (StatsModels): {percentile_statsmodels:.2f}')
```

**SET-4**

1. **Develop a model to find the variance and standard deviation of univariate statistics measures by using Pandas.**

```python
import pandas as pd

# Load the data
data = pd.read_csv('data.csv')

# Calculate variance and standard deviation using Pandas
variance = data['value'].var()
std_dev = data['value'].std()

print(f'Variance: {variance:.2f}')
print(f'Standard Deviation: {std_dev:.2f}')
```

**SET-5**

1. **Demo on Bivariate and Multivariate Descriptive Statistics measures.**

```python
import pandas as pd

# Load the data
data = pd.read_csv('data.csv')

# Calculate bivariate descriptive statistics
bivariate_stats = data[['column1', 'column2']].describe()
print('Bivariate Descriptive Statistics:')
print(bivariate_stats)

# Calculate multivariate descriptive statistics
multivariate_stats = data.describe()
print('\nMultivariate Descriptive Statistics:')
print(multivariate_stats)
```

**SET-6**

1. **Develop a model to measure covariance matrix, correlation matrix, and heat map of the given data set.**

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load the data
data = pd.read_csv('data.csv')

# Calculate covariance matrix
covariance_matrix = data.cov()
print('Covariance Matrix:')
print(covariance_matrix)

# Calculate correlation matrix
correlation_matrix = data.corr()
print('\nCorrelation Matrix:')
print(correlation_matrix)

# Plot heat map
plt.figure(figsize=(8, 6))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')
plt.title('Correlation Heat Map')
plt.show()
```

**SET-7**

1. **Develop a model on Analysis of Variance (ANOVA) and table for the given data.**

```python
import pandas as pd
from scipy.stats import f_oneway

# Load the data
data = pd.read_csv('data.csv')

# Perform one-way ANOVA
groups = [data[data['group'] == 'A']['value'], data[data['group'] == 'B']['value'], data[data['group'] == 'C']['value']]
f_value, p_value = f_oneway(*groups)

print(f'F-value: {f_value:.2f}')
print(f'p-value: {p_value:.4f}')
```

**SET-8**

1. **Calculating the skewness of a data set by Pandas and SciPy.**

```python
import pandas as pd
from scipy.stats import skew

# Load the data
data = pd.read_csv('data.csv')

skewness_pandas = data['value'].skew()
print(f'Skewness (Pandas): {skewness_pandas:.2f}')

skewness_scipy = skew(data['value'])
print(f'Skewness (SciPy): {skewness_scipy:.2f}')
```

**SET-9**

1. **Design a model to calculate Percentile by SciPy and Stats Models.**

```python
import pandas as pd
from scipy.stats import percentileofscore
import statsmodels.api as sm

# Load the data
data = pd.read_csv('data.csv')

# Calculate percentile using SciPy
percentile_scipy = percentileofscore(data['value'], 75)
print(f'Percentile (SciPy): {percentile_scipy}th')

# Calculate percentile using StatsModels
percentile_statsmodels = sm.DistributionDistance().percentile(data['value'], 0.75)
print(f'Percentile (StatsModels): {percentile_statsmodels:.2f}')
```

**SET-10**

1. **Develop a model to find the variance and standard deviation of univariate statistics measures by using Pandas.**

```python
import pandas as pd

# Load the data
data = pd.read_csv('data.csv')

# Calculate variance and standard deviation using Pandas
variance = data['value'].var()
std_dev = data['value'].std()

print(f'Variance: {variance:.2f}')
print(f'Standard Deviation: {std_dev:.2f}')
```

**SET-11**

1. **Demo on Bivariate and Multivariate Descriptive Statistics measures.**

```python
import pandas as pd

# Load the data
data = pd.read_csv('data.csv')

# Calculate bivariate descriptive statistics
bivariate_stats = data[['column1', 'column2']].describe()
print('Bivariate Descriptive Statistics:')
print(bivariate_stats)

# Calculate multivariate descriptive statistics
multivariate_stats = data.describe()
print('\nMultivariate Descriptive Statistics:')
print(multivariate_stats)
```

**SET-12**

1. **Develop a model to measure covariance matrix, correlation matrix, and heat map of the given data set.**

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load the data
data = pd.read_csv('data.csv')

# Calculate covariance matrix
covariance_matrix = data.cov()
print('Covariance Matrix:')
print(covariance_matrix)

# Calculate correlation matrix
correlation_matrix = data.corr()
print('\nCorrelation Matrix:')
print(correlation_matrix)

# Plot heat map
plt.figure(figsize=(8, 6))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')
plt.title('Correlation Heat Map')
plt.show()
```
