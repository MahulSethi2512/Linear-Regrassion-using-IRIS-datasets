# Linear-Regrassion-using-IRIS-datasets
What is linear regression? Linear regression analysis is used to predict the value of a variable based on the value of another variable. The variable you want to predict is called the dependent variable. The variable you are using to predict the other variable's value is called the independent variable.

Before we begin…
Firstly, you will need to have Python installed and an Integrated Development Environment (IDE) of your choice (this is completely up to you, you may or may not want to use an IDE). I am using Jupyter Notebook as it is by far the best IDE for data visualisation/manipulation and Machine Learning in my opinion.

Secondly, you will also need to install pandas, NumPy, scikit-learn (sklearn), matplotlib and finally seaborn. Run pip/pip3/conda install on your command line to install these packages as such.

# Import Dataset from sklearn
from sklearn.datasets import load_iris
# Load Iris Data
iris = load_iris()
# Creating pd DataFrames
iris_df = pd.DataFrame(data= iris.data, columns= iris.feature_names)
target_df = pd.DataFrame(data= iris.target, columns= ['species'])
def converter(specie):
    if specie == 0:
        return 'setosa'
    elif specie == 1:
        return 'versicolor'
    else:
        return 'virginica'
target_df['species'] = target_df['species'].apply(converter)
# Concatenate the DataFrames
iris_df = pd.concat([iris_df, target_df], axis= 1)
