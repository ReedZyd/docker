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

* 安装镜像：

	* https://yeasy.gitbooks.io/docker_practice/install/ubuntu.html
	
	* 如果用dockerhub 需要设置加速器
* 封装镜像：

	* docker build -t reed98/pytorch:pytorch -f ./pytorch.Dockerfile ./
	
* 偷懒tips:

	* 封装好一个空环境，准备好`requiremente.txt`，带着conda环境路径运行
	
	* 准备`requiremente.txt`：pip freeze > requirements.txt
	
	* 进入docker后：conda create -n torch --clone `path2env` && conda activate torch && pip install -r requirements.txt

* 上传镜像：

	* docker login
	
		![image](http://github.com/ReedZyd/using_images/raw/master/README_images/docker_login.png)
		
	* sudo docker push reed98/pytorch:pytorch
* 其他操作：

	* sudo docker images / sudo docker image ls
	
	* sudo docker rm \[镜像1\] \[镜像2\]
* 在集群中使用

	* docker pull reed98/pytorch:pytorch
	
	* docker tag reed98/pytorch:pytorch 192.168.199.100:8888/zyd/pytorch:pytorch
	
	* docker login 192.168.199.100:8888
	
	* docker push 192.168.199.100:8888/reed98/pytorch:pytorch

* 上传数据

	 * scp -r some_data vsislab@192.168.199.100:data/zyd/
	
* 直接使用node53
	
	 * 登录&传输
	 
		* 地址：202.194.203.129:3353 (传文件时去掉:3353 端口号填2253)
		
		* 账号：vsislab
		
		* 密码：vsislab123
		
	* 直接在node53中更改环境
	
		* 封装镜像：

			* docker build -t 192.168.199.100:8888/zyd/pytorch:pytorch  -f ./pytorch.Dockerfile ./

		* 上传镜像：
		
			* docker login 192.168.199.100:8888
	
            * docker push 192.168.199.100:8888/reed98/pytorch:pytorch
