README.md
======

* reed98/pytorch:pytorch.Dockerfile

	* ubuntu16.04
	* cuda9.0
	* python3.5
	* pytorch1.1 torchvision0.3
  
  
* 封装镜像：

	* docker build -t reed98/pytorch:pytorch -f ./pytorch.Dockerfile ./

* 上传镜像：
	* docker login
	
		![image](http://github.com/ReedZyd/using_images/raw/master/README_images/docker_login.png)
		
	* sudo docker push reed98/pytorch:pytorch
	

