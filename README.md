README.md
=====

 * docker/images/basic:miniconda.Dockerfile

     * ubuntu16.04
     * cuda9.0
     * python3.5

* reed98/pytorch:pytorch.Dockerfile

	* ubuntu16.04

	* cuda9.0

	* python3.5

	* pytorch1.1 torchvision0.3
  
* 封装镜像：

	* docker build -t reed98/pytorch:pytorch -f ./pytorch.Dockerfile ./

* 上传镜像：

	* docker login
	
		! [image](http://github.com/ReedZyd/using_images/raw/master/README_images/docker_login.png)
		
	* sudo docker push reed98/pytorch:pytorch
	
* 在集群中使用

	* docker pull reed98/pytorch:pytorch
	
	* docker tag reed98/pytorch:pytorch 192.168.199.100:8888/zyd/pytorch:pytorch
	
	* docker login 192.168.199.100:8888
	
	* docker push 192.168.199.100:8888/reed98/pytorch:pytorch

* 上传数据

	 * scp -r some_data vsislab@192.168.199.100:data/zyd/
	
* 直接使用node53
	
	 * 登录&传输
	 
		* 地址：202.194.203.129:3353
		
		* 账号：vsislab
		
		* 密码：vsislab123
		
	* 直接在node53中更改环境
	
		* 封装镜像：

			* docker build -t 192.168.199.100:8888/zyd/pytorch:pytorch  -f ./pytorch.Dockerfile ./

		* 上传镜像：
		
			* docker login 192.168.199.100:8888
	
            * docker push 192.168.199.100:8888/reed98/pytorch:pytorch
