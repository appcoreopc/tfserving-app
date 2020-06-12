# tfserving-app



sudo echo "deb http://storage.googleapis.com/tensorflow-serving-apt stable tensorflow-model-server tensorflow-model-server-universal" | tee /etc/apt/sources.list.d/tensorflow-serving.list && curl https://storage.googleapis.com/tensorflow-serving-apt/tensorflow-serving.release.pub.gpg | apt-key add -


If you get permission denied, then try executing the following command
 

#### sudo apt-get update

Next, you will get the followings :- 

Hit:1 http://azure.archive.ubuntu.com/ubuntu bionic InRelease
Get:2 http://azure.archive.ubuntu.com/ubuntu bionic-updates InRelease [88.7 kB]
Get:3 http://azure.archive.ubuntu.com/ubuntu bionic-backports InRelease [74.6 kB]
Hit:4 http://storage.googleapis.com/tensorflow-serving-apt stable InRelease
Get:5 http://security.ubuntu.com/ubuntu bionic-security InRelease [88.7 kB]

Next run the following to intall it.

#### sudo apt-get install tensorflow-model-server

Execute your tensorflow model server

#######


nohup tensorflow_model_server \
  --rest_api_port=8501 \
  --model_name=fashion_model \
  --model_base_path="/tmp/1" >server.log 2>&1

