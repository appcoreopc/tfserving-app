# tfserving-app

Start creating your simple image recognition model by running the following command 

#### python simple-mnist.py

This will create a simple model, train and then save it, into /tmp/1. 

But when you server your app, make sure it is to /tmp and not /tmp/1

#### Setting up your server

Next, run the following command from the command line after your install your tensorflow-serving component via apt-get install. Please note, 8501 is the default REST API port and 8500 is gRPC port.


 nohup tensorflow_model_server \
  --rest_api_port=8501 \
  --model_name=fashion_model \
  --model_base_path="${MODEL_DIR}" >server.log 2>&1

 Please take a look at your server.log to ensure everything is working well. 

### To make a simple request

Run the following command to make a simple request to your smarter and well trained model. 

#### python request.py


Noticed that this is the default URL that we are posting our data into: 

    requests.post('http://localhost:8501/v1/models/fashion_model:predict', data=data, headers=headers)

Noticed the --model_name=fashion_model with the REST API /v1/models/fashion_model. :) 
Yeap that's no coincidence. 

### Installing your server 

 --------------------------------------------------------------------------

If you have not install tensorflow run the following 2 commands below :- 

### To add a repo 

echo "deb http://storage.googleapis.com/tensorflow-serving-apt stable tensorflow-model-server tensorflow-model-server-universal" | tee /etc/apt/sources.list.d/tensorflow-serving.list && curl https://storage.googleapis.com/tensorflow-serving-apt/tensorflow-serving.release.pub.gpg | apt-key add -


### Let's install this baby

If you get like "tensorflow-model-server" not found, try restarting your bash shell. 

apt-get update && apt-get install tensorflow-model-server

--------------------------------------------------------------------------
