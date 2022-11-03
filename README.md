###### Step-1: Install Python (3.7 or later)

![1](https://user-images.githubusercontent.com/74168188/199009475-658cdf5c-8f16-41c0-a5e6-5cd2c07188aa.png)

###### Step-2: Install the package

```sh
pip3 install locust
```
![2](https://user-images.githubusercontent.com/74168188/199010641-b50e36b9-cebb-4767-a121-6ef4c12393fd.png)

###### Step-3: Validate your installation

```sh
locust -V
```
![3](https://user-images.githubusercontent.com/74168188/199010738-897d96df-84ef-4017-a3d9-c3bd44f7fa24.png)

###### Step-4: Done! Now create your first test

A Locust test is essentially a Python program. Create python program according to your requirements. I have used two endpoints /index.html and /test.html

Put the code in a file named locustfile.py in your current directory and run :
```sh
locust -f locustfile.py
```

![4](https://user-images.githubusercontent.com/74168188/199708543-3f7e9f16-0968-4a41-8ff6-19c59741baa4.png)

![5](https://user-images.githubusercontent.com/74168188/199708706-796ad442-3416-4146-b6fd-3a3c40458bd7.png)

Now hit InstancePublicIP:8089 after adding rule for 8089 port in security group. Enter number of users, Spawn rate, and Host.

![6](https://user-images.githubusercontent.com/74168188/199709198-0ddad8ac-8882-49d9-a97e-e9d416eaad96.png)

Now, click on start swarming. And get the statistics, charts, failures, exceptions, current ratio, and download data.

![7](https://user-images.githubusercontent.com/74168188/199709636-52c08f52-0cd8-41a9-a0cc-82b035bcecd0.png)
![8](https://user-images.githubusercontent.com/74168188/199709960-8d4851b6-630a-4d13-887a-01276a9fdefc.png)
![9](https://user-images.githubusercontent.com/74168188/199710055-01a002ae-162f-4926-abd5-ebf59529d49a.png)
![10](https://user-images.githubusercontent.com/74168188/199710263-3bc312b0-0abb-4903-99d0-12e9b8b256aa.png)
![11](https://user-images.githubusercontent.com/74168188/199710270-473c450f-996b-4e91-a175-1a0be30582de.png)
![12](https://user-images.githubusercontent.com/74168188/199710290-4d39f757-2bc7-4ee2-b30a-d2e8b96a2df2.png)
