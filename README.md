# Flask and Heroku machine learning app deployment

## Objective
* Using Flask and Heroku, deploy a machine learning model using a network traffic dataset inorder to predict whether or not the traffic is malicious or benign.

## Code Preview
``` python
from dotenv import load_dotenv
load_dotenv()

from flask import Flask, request, render_template
app = Flask(__name__)


with open(os.getenv('MODEL_NAME'), 'rb') as f:
    model = pkl.load(f)


model_n_features = np.asarray(model.named_steps['preprocessor']._n_features)
```
```python
#https://flask.palletsprojects.com/en/1.1.x/quickstart/#the-request-object
@app.route('/predict', methods=['GET','POST'])
def predict():
    error = None
    y_pred = None
    if request.method == 'POST':
        predict_me = {feature_name: None for feature_name in original_dataset_features}
```

## Website Image
![alt text](https://github.com/8Jun/lab4-Flask-Heroku-Deployment/blob/master/predict%20if%20malicious.PNG)
