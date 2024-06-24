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

![Alt text](https://images.app.goo.gl/5Pzfs2oKfGdTVLUL8)

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

![Alt test](https://www.google.com/search?client=ms-android-oppo-rvo3&sca_esv=fdded5f414667f33&sxsrf=ADLYWIL3Y0UGmDROqvmXk0P2s3cpEw6LBQ:1719232522094&q=Use+case+diagram+to+withdraw+amount+from+ATM.&udm=2&fbs=AEQNm0BKxFXqFZETuC92mLOmXO9xTuwl7LTqpjEikSHB2sNnAo_Nt6_jBoO5j_EG4ZXs8aQCufxT5WhqKxk_t3EFVMM67rI6i01ADbZ-a5wYaAsalDcO6S1GH-LO2-BpNO0GjKIvvxoXnjjP08V8RmhXnS3ZTYi7mGxclhyNM7kU-cEZojmfYb66zxZupqQ3TpTT-qjAIEt1CwlZuUTZOKSe8wS1nEmI6w&sa=X&ved=2ahUKEwia3Y-eoPSGAxUXUWcHHXN5CrEQtKgLegQIERAB&biw=360&bih=708&dpr=3#vhid=K9okCfF7P6HACM&vssid=mosaic)

SET-7
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

2. Draw an Activity diagram for Online Course Management System.
```plaintext
Title: Activity Diagram for Online Course Management System

Start
    -> Browse Courses
    -> Select Course
    [if Registered] 
        -> Access Course Material
        -> Take Assessments
        [if Pass] 
            -> Receive Certificate
            -> End
        [else] 
            -> Retry Assessments
            -> End
    [else] 
        -> Register for Course
        -> End
```

SET-8
1. Calculating the skewness of a data set by Pandas and SciPy.
```python
from scipy.stats import skew
import pandas as pd

data = pd.Series([1, 2, 2, 3, 4, 5, 6, 6, 6, 7])
pandas_skew = data.skew()
scipy_skew = skew(data)
print(pandas_skew, scipy_skew)
```

2. Draw a Class Diagram for Railway Management System.
```plaintext
Title: Class Diagram for Railway Management System

Class Train
    + trainNumber: int
    + name: String
    + type: String
    + capacity: int
    + getDetails(): void

Class Station
    + stationCode: String
    + name: String
    + location: String
    + getSchedule(): void

Class Ticket
    + ticketNumber: int
    + passengerName: String
    + trainNumber: int
    + seatNumber: String
    + bookTicket(): void
    + cancelTicket(): void

Class Passenger
    + passengerID: int
    + name: String
    + contactInfo: String
    + bookTicket(): void
    + cancelTicket(): void

Train "1" -- "*" Station
Passenger "1" -- "*" Ticket
```

SET-9
1. Design a model to calculate Percentile by SciPy and Stats Models.
```python
from scipy.stats import scoreatpercentile
import numpy as np

data = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
percentile_25 = scoreatpercentile(data, 25)
percentile_75 = scoreatpercentile(data, 75)
print(percentile_25, percentile_75)
```

2. Draw a State Machine Diagram for Course Selection.
```plaintext
Title: State Machine Diagram for Course Selection

[Initial State]
    -> Start
    -> Browse Courses
    [if Course Available] -> Select Course
    [if Registered] -> Access Course
    [else] -> Register
    -> [End State]
```

SET-10
1. Develop a model to find the variance and standard deviation of univariate statistics measures by using Pandas.
```python
import pandas as pd

data = pd.Series([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
variance = data.var()
std_dev = data.std()
print(variance, std_dev)
```

2. Draw a Collaboration Diagram for Hospital Management System.
```plaintext
Title: Collaboration Diagram for Hospital Management System

Patient -> Reception: Register
Patient -> Doctor: Consultation
Doctor -> Lab: Request Tests
Lab -> Doctor: Send Results
Doctor -> Patient: Prescribe Medication
Patient -> Pharmacy: Get Medication
```

SET-11
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

2. Draw an Activity diagram for Library Management System.
```plaintext
Title: Activity Diagram for Library Management System

Start
    -> Search Books
    [if Available] -> Borrow Book
        -> Issue Book
        -> Read Book
        -> Return Book
        -> End
    [else] -> Request Book
        -> Wait for Availability
        -> Borrow Book
        -> End
```

SET-12
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

2. Develop test cases for unit testing.
```python
import unittest

class TestStatistics(unittest.TestCase):
    def test_cov_matrix(self):
        self.assertEqual(cov_matrix.shape, (4, 4))
    
    def test_corr_matrix(self):
        self.assertEqual(corr_matrix.shape, (4, 4))

if __name__ == '__main__':
    unittest.main()
```
