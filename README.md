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

![image](https://user-images.githubusercontent.com/96001018/162644438-bad497a8-ebde-4cb2-92e4-1a4375261a42.png)

### Establish a Baseline Performance 
Generate trading signals using short- (4) and long-window (100) SMA values:
![image](https://user-images.githubusercontent.com/96001018/162645394-28fdfaec-be4e-47e9-9fc4-fe3c24cf25d5.png)

Initialize a new Signal column for actual returns. Indicates to buy stock long = 1, sell stock short = -1.
![image](https://user-images.githubusercontent.com/96001018/162645485-ce043fd5-4ca3-420b-a806-35c7d2bba20c.png)

Calculate strategy returns and added data to new column in DataFrame:
![image](https://user-images.githubusercontent.com/96001018/162645566-fe12da16-d9a7-4181-9bb2-a22b6ec27227.png)

Train and test dataset. Select ending period from the training data with an offset of 3 months:
![image](https://user-images.githubusercontent.com/96001018/162645700-832345d3-59ff-4f3c-b6b4-d8fcda336864.png)

Classification Report associated with the SVC model predictions. 
![image](https://user-images.githubusercontent.com/96001018/162645605-f077b96a-1b3c-4c21-b1ad-26e55b7add79.png)


### Tune the Baseline Trading Algorithm

### Evaluate a New Machine Learning Classifier (Using Logistic Regression)

### Create an Evaluation Report




## Contributors

Leigh Anne Badua leighbadua@gmail.com 


## License

MIT
