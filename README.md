# Machine Learning Trading Bot

This prototype application demonstrates machine learning using and improving existing algorithmic trading systems to maintain a firm's competitive advantage in the market. It is important to improve the algorithm because the speed of its transactions gives firms a competitive advantage early on. But, people still need to specifically program these systems, which limits their ability to adapt to new data. This notebook shows steps to accomplish this in each of the following sections:

* Establish a Baseline Performance 
* Tune the Baseline Trading Algorithm
* Evaluate a New Machine Learning Classifier
* Create an Evaluation Report


## Technologies
Click on the links below for documentation on each of the technologies used. This project uses the following libraries and dependencies:
+ [**Anaconda**](https://docs.anaconda.com/): an open source package and environment management system.
+ [**JupyterLab**](https://jupyterlab.readthedocs.io/en/stable/): an extensive environment using web-based user interface designed for data analysis. 
+ [**Pandas**](https://pandas.pydata.org/docs/getting_started/index.html): (included in Anaconda) a Python package data analysis toolkit.
+ [**Numpy**](https://numpy.org/doc/stable/) for scientific computing such as mathematical, basic statistical operations, and much more. 
+ [**scikitlearn**](https://scikit-learn.org/stable/install.html) an open source machine learning library that supports supervised and unsupervised learning. It also provides various tools for model fitting, data preprocessing, model selection, model evaluation, and many other utilities. 
+ [**matplotlib inline**](https://pandas.pydata.org/pandas-docs/version/0.13.1/install.html): library to create static, animated, and interactive visualizations in JupyterLab.


## Installation Guide
Check to ensure that Jupyterlab is installed on your machine by entering the following into your environment using `conda list`. If any of these techologies are not installed into your environment, use the corresponding codes in your terminal: 

```
pip install -U scikit-learn
```


### Instructions to Use JupyterLab

To launch JupyterLab:
  1. Open terminal window, and type `conda activate dev`.
  2. Type `jupyter lab`. JupyterLab user interface should open in your browser. 
      a. Or copy and paste one of the URLs: "http://localhost:8888/lab?token=..." into web browser. 

To exit JupyterLab:
  1. On your web browser, use the Run button to shut down any running kernel sessions.
  2. On the menu bar, on the File menu, select Shut Down. 
  3. Okay to close tabs once a dialog box with "Server stopped" message indicates the server has stopped. 
  4. Navigate to terminal window, where you launched JupyterLab and type `conda deactivate`. This will return you to your `base` environment. 


## Usage 

1. Clone the repository `https://github.com/leighbadua/machine_learning_trading_bot.git`
2. Using your terminal, activate the environment and launch jupyter lab (instructions mentioned above). 
3. Launch `machine_learning_trading_bot.ipynb` in JupyterLab

### Import other required libraries and dependencies: 

![image](https://user-images.githubusercontent.com/96001018/162666608-c4b0daf7-46ae-416e-a95b-387dda184676.png)

### Establish a Baseline Performance 
Generate trading signals using short- (4) and long-window (100) SMA values:
![image](https://user-images.githubusercontent.com/96001018/162666708-3779dccc-0b13-4d35-b0cc-0d4e7ef74030.png)

Initialize a new Signal column for actual returns. Indicates to buy stock long = 1, sell stock short = -1.
![image](https://user-images.githubusercontent.com/96001018/162666786-9bf76c1c-58b1-4ea0-8855-790bd7d1aa12.png)

Calculate strategy returns and added data to new column in DataFrame:
![image](https://user-images.githubusercontent.com/96001018/162666891-cabc04c2-3e58-4315-9683-25b6f085aa30.png)


Train and test dataset. Select ending period from the training data with an offset of 3 months:
![image](https://user-images.githubusercontent.com/96001018/162666998-67f7416f-5b2e-482b-a871-adc50359b93b.png)

Classification Report associated with the SVC model predictions. 
![image](https://user-images.githubusercontent.com/96001018/162667038-047f80bf-c34c-4955-8bb7-d547e54c2bfd.png)


### Tune the Baseline Trading Algorithm
### Step 1: Tune the training algorithm by adjusting the size of the training dataset. We set various DateOffset values to adjust the size of the training dataset.**  
**What impact resulted from increasing or decreasing the training window?**
As we change the size of the training dataset, we observe that the actual return line and the strategy return line move closer together and eventually crosses over with a smaller training dataset window (with the 24 month DateOffset).  

![actual_vs_strategy_returns_6months](https://user-images.githubusercontent.com/96001018/162657921-06131c80-f137-416d-9a28-9e2ffb65d301.png)
![actual_vs_strategy_returns_18months](https://user-images.githubusercontent.com/96001018/162657975-887ca83a-4ab1-4674-8468-ff5a31baec3f.png)
![actual_vs_strategy_returns_24months](https://user-images.githubusercontent.com/96001018/162658052-2efafbd1-5982-408d-8f40-778e4ed08150.png)


### Step 2: Tune the trading algorithm by adjusting the SMA input features.

**What impact resulted from increasing or decreasing either or both of the SMA windows?**
The actual returns were highest with SMA30 and SMA200 windows, giving 1.6 times return.  
Whereas, the SMA4 and SMA200, had the highest strategy returns of 1.8 and the actual return was around 1.6. Increasing the short-window (SMA4 to SMA30) shows the actual return is higher. Versus increasing the long-window from baseline (SMA100 to SMA200) shows to return a higher strategy return and not necessarily a higher actual return. 

**Short window=30, Long window=200:**
In 2021, actual return show about 1.6 times vs strategy return shows about 0.8. 
![actual_vs_strategy_returns_3months_increased_windows](https://user-images.githubusercontent.com/96001018/162663310-da74e88a-9213-4fa4-938b-0c2159570d2f.png)

**Short window=30, Long window=100:**
In 2021, actual and strategy returns are about 1.4 and 0.7, respectively.  
![actual_vs_strategy_returns_3months_short30long100](https://user-images.githubusercontent.com/96001018/162663360-fa8f8cd8-2886-4085-bf25-2a89202f993f.png)

**Short window=4, Long window=200:**
In 2021, strategy returns 1.8 times while the actual resulted around 1.6 times return. 
![actual_vs_strategy_returns_3months_short4long200](https://user-images.githubusercontent.com/96001018/162663377-85cd9287-948d-4a5d-a40e-1905b9cca9f6.png)


### Evaluate a New Machine Learning Classifier (Using Logistic Regression)
The image shows that the strategy returns about 1.5 times and the actual returns about 1.4. Those who are risk loving would could consider this with the greater potential for profit but also for great loss. 
![lr_actual_vs_strategy](https://user-images.githubusercontent.com/96001018/162663953-0a72805b-1cd6-423d-8861-395d76236920.jpg)


### Evaluation Report
SVC Actual vs. Strategy Returns baseline features (Short Window=4, Long Window=100, DateOffset 3 months)
![actual_vs_strategy_returns](https://user-images.githubusercontent.com/96001018/162646575-2f685515-2f0e-477f-ad0a-90cf2ee34049.png)
![image](https://user-images.githubusercontent.com/96001018/162666197-c6414978-60fa-4a46-bfad-2dc5e3c764b5.png)


Logistic Regression 
![lr_actual_vs_strategy](https://user-images.githubusercontent.com/96001018/162647625-d6146c5b-c9ea-4034-8662-26e12e91551f.jpg)
![image](https://user-images.githubusercontent.com/96001018/162666242-16f9fdec-2330-4c71-ad84-2ffc66c94ce9.png)


**Conclusion**
In comparison between a SVC and a Logistic Regression model, the accuracy on the SVC model is higher than the Logistic Regression model. A low risk tolerance individual should select using the SVC. The SVC model returns approximately 1.4 in actual returns and 0.8 in strategy returns in 2021. 

## Contributors

Leigh Anne Badua leighbadua@gmail.com 


## License

MIT
