Machine Learning Trading Bot


This file is an algorithmic trading bot that learns and adapts to new data and evolving markets.
---

## Technologies

This project leverages python 3.7 with the following packages:

* [pandas](https://pandas.pydata.org/) - For data manipulation and analysis.
* [hvplot](https://hvplot.holoviz.org/) - For interactive user prompts and dialogs
* [pathlib](https://docs.python.org/3/library/pathlib.html) - To provide for an easier method to interact with the filesystem no matter what the operating system is.
* [numpy](https://numpy.org/) -  A fundamental package for scientific computing with Python.
* [pystan](https://mc-stan.org/users/interfaces/pystan) - A software for facilitating statistical inference at the frontiers of applied statistics.
* [matplotlib](https://matplotlib.org/) - Matplotlib is a comprehensive library for creating static, animated, and interactive visualizations in Python.
* [scikit-learn](https://scikit-learn.org/stable/) - Simple and efficient tools for predictive data analysis



---

## Installation Guide

Before running the application first install the following dependencies.

``` pyviz
  conda install -c pyviz hvplot geoviews
```

``` prophet
    python -m pip install prophet
```

``` pystan(must be 2.19.1.1)
    pip install pystan==2.19.1.1
```

``` numpy
    pip install numpy
```

``` scikit-learn
    pip install -U scikit-learn
```

``` matplotlib
    python -m pip install -U pip
    python -m pip install -U matplotlib
```


---

## 

In order to run this analysis, we use various tools from the prophet, numpy and hvplot library. Please use the following libraries to operate this notebook:

    # Imports
    import pandas as pd
    import numpy as np
    from pathlib import Path
    import hvplot.pandas
    import matplotlib.pyplot as plt
    from sklearn import svm
    from sklearn.preprocessing import StandardScaler
    from pandas.tseries.offsets import DateOffset
    from sklearn.metrics import classification_reportfrom prophet import Prophet

---

## Summary Evaluation

### Baseline Algorithm and Adjustments

The baseline algorithm with a 3 month date offset for the training data, SMA short window of 4days and a SMA long window of 100days produces similar strategy returns compared to actual returns up until mid 2019 -- where the strategy returns begins to produce better results over the time period observed.

![Alt text](./Pictures/"SVM_Baseline_Model.png")

When adjusting the SVM model training data to have a shorter date offset (1 Month), the strategy returns constistently produces higher returns compared to the actual returns throughout the time period observed.

![Alt text](./Pictures/"SVM_1M_Model.png")

When adjusting the SVM model training data to have a longer date offset (6 Month), the strategy returns produces similar returns compared to the actual returns until late 2018, then produces worse results until early 2020, where the algorithm spikes and produces much higher returns for the time period observed.

![Alt text](./Pictures/"SVM_6M_Model.png")

When reducing the SVM Model training data's SMA short window to 2, the strategy returns consistently produces slightly higher returns compared to actual returns, this is slightly more considerate by the end of 2017 and onwards in the dataset.

![Alt text](./Pictures/"SVM_SMA_Short_2.png")

When increasing the SVM Model training data's SMA long window to 126, the strategy returns inconsistent strategy returns compared to actual returns throughout the entirety of the time period observed.

![Alt text](./Pictures/"SVM_SMA_Long_126.png")

When increasing the SVM Model training data's SMA long window to 126, the strategy returns inconsistent strategy returns compared to actual returns throughout the entirety of the time period observed.

![Alt text](./Pictures/"SVM_SMA_Long_126.png")

When increasing the SVM Model training data's SMA long window (126) and decreasing the SMA's short window (2), the strategy returns inconsistent strategy returns compared to actual returns throughout the entirety of the time period observed. The data set shows slight short term losses but slight long term gains.

![Alt text](./Pictures/"SVM_SMA_Short_Long_2_126.png")

### ADA Boost Classifier

When using the ADA Boost Classifier as an alternative of the SVM model, the strategy returns performed poorly until early 2020 where the returns began to outpace actual returns for the remainder of the dataset observed.

![Alt text](./Pictures/"ADA_Boost_Model.png")

### Conclusion

The trading algorithm has potential to create better returns than actual returns with some fine tuning. The benefits of these this model faster and more efficient data analysis that can create a competitive edge against traditional trading by humans.

This particular algorothm with this dataset did better with a SVM Model which has the following time parameters: 

- SMA Short Window: 4
- SMA Long Window: 100
- Training Date Offset: 3 months.

This particular model is recommended for future advising.



---

## Contributors

Brought to you by PShum FinTech Consulting

---

## License

+ Prophet
MIT

Copyright (c) Facebook, Inc. and its affiliates.

+ MatPlotLib

Matplotlib only uses BSD compatible code, and its license is based on the PSF license.

© Copyright 2002–2012 John Hunter, Darren Dale, Eric Firing, Michael Droettboom and the Matplotlib development team; 2012–2023 The Matplotlib development team.

+ Scikit-Learn

BSD 3-Clause License

Copyright (c) 2007-2023 The scikit-learn developers.
All rights reserved.

+ Numpy

Copyright (C) 2008-2022 Stefan van der Walt <stefan@mentat.za.net>, Pauli Virtanen <pav@iki.fi>

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are
met:

 1. Redistributions of source code must retain the above copyright
    notice, this list of conditions and the following disclaimer.
 2. Redistributions in binary form must reproduce the above copyright
    notice, this list of conditions and the following disclaimer in
    the documentation and/or other materials provided with the
    distribution.
    
+ HvPlot    

License: BSD License (BSD)

+ Pandas

BSD 3-Clause License

Copyright (c) 2008-2011, AQR Capital Management, LLC, Lambda Foundry, Inc. and PyData Development Team
All rights reserved.

Copyright (c) 2011-2023, Open source contributors.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this
  list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above copyright notice,
  this list of conditions and the following disclaimer in the documentation
  and/or other materials provided with the distribution.

* Neither the name of the copyright holder nor the names of its
  contributors may be used to endorse or promote products derived from
  this software without specific prior written permission.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.