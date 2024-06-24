SET-1
1. Develop a model on Analysis of Variance (ANOVA) and table for the given data.
```python
from sklearn.datasets import load_iris
import pandas as pd
import statsmodels.api as sm
from statsmodels.formula.api import ols

data = load_iris()
df = pd.DataFrame(data.data, columns=data.feature_names)
df['species'] = data.target

model = ols('sepal length (cm) ~ C(species)', data=df).fit()
anova_table = sm.stats.anova_lm(model, typ=2)
print(anova_table)
```

2. Write a unit test cases with example.
```python
import unittest

class TestANOVA(unittest.TestCase):
    def test_anova(self):
        self.assertTrue(anova_table['PR(>F)'][0] < 0.05)

if __name__ == '__main__':
    unittest.main()
```

SET-2
1. Calculating the skewness of a data set by Pandas and SciPy.
```python
from scipy.stats import skew
import pandas as pd

data = pd.Series([1, 2, 2, 3, 4, 5, 6, 6, 6, 7])
pandas_skew = data.skew()
scipy_skew = skew(data)
print(pandas_skew, scipy_skew)
```

2. Write integration test cases with an example.
```python
import unittest

class TestSkewness(unittest.TestCase):
    def test_skewness(self):
        self.assertAlmostEqual(pandas_skew, scipy_skew, places=5)

if __name__ == '__main__':
    unittest.main()
```

SET-3
1. Design a model to calculate Percentile by SciPy and Stats Models.
```python
from scipy.stats import scoreatpercentile
import numpy as np

data = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
percentile_25 = scoreatpercentile(data, 25)
percentile_75 = scoreatpercentile(data, 75)
print(percentile_25, percentile_75)
```

2. Develop white box testing cases with example.
```python
import unittest

class TestPercentile(unittest.TestCase):
    def test_percentile(self):
        self.assertEqual(percentile_25, 3.25)
        self.assertEqual(percentile_75, 7.75)

if __name__ == '__main__':
    unittest.main()
```

SET-4
1. Develop a model to find the variance and standard deviation of univariate statistics measures by using Pandas.
```python
import pandas as pd

data = pd.Series([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
variance = data.var()
std_dev = data.std()
print(variance, std_dev)
```

2. Develop black box testing cases with example.
```python
import unittest

class TestUnivariateStatistics(unittest.TestCase):
    def test_statistics(self):
        self.assertAlmostEqual(variance, 9.166666666666666)
        self.assertAlmostEqual(std_dev, 3.0276503540974917)

if __name__ == '__main__':
    unittest.main()
```

SET-5
1. Demo on Bivariate and Multivariate Descriptive Statistics measures.
```python
import pandas as pd
from sklearn.datasets import load_iris

data = load_iris()
df = pd.DataFrame(data.data, columns=data.feature_names)

bivariate = df.corr()
multivariate = df.describe()
print(bivariate)
print(multivariate)
```

2. Draw a Sequence diagram for Library Management system.
```plaintext
Title: Sequence Diagram for Library Management System

Participant User
Participant LibrarySystem
Participant Book
Participant Database

User->LibrarySystem: Request for a book
LibrarySystem->Database: Check book availability
Database-->LibrarySystem: Book available
LibrarySystem->Book: Issue book
Book-->LibrarySystem: Book issued
LibrarySystem->User: Book issued confirmation
```

SET-6
1. Develop a model to measure covariance matrix, correlation matrix, and heat map of the given data set.
```python
import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.datasets import load_iris

data = load_iris()
df = pd.DataFrame(data.data, columns=data.feature_names)

cov_matrix = df.cov()
corr_matrix = df.corr()

sns.heatmap(corr_matrix, annot=True, cmap='coolwarm')
plt.show()
```

2. Draw a Use case diagram to withdraw amount from ATM.
```plaintext
Title: Use Case Diagram for ATM Withdrawal

Actor: User
Use Case: Authenticate User
Use Case: Select Transaction
Use Case: Withdraw Cash
Use Case: Print Receipt

User->(Authenticate User)
User->(Select Transaction)
User->(Withdraw Cash)
User->(Print Receipt)
```
