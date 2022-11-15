###### Step-1: Install Python (3.7 or later)

![1](https://user-images.githubusercontent.com/74168188/199009475-658cdf5c-8f16-41c0-a5e6-5cd2c07188aa.png)

###### Step-2: Install the package

```sh
pip3 install locust
```

![2](https://user-images.githubusercontent.com/74168188/201894190-b144c7c1-655d-4597-8b06-34cf72aedffd.png)

###### Step-3: Validate your installation

```sh
locust -V
```
![3](https://user-images.githubusercontent.com/74168188/201893962-8625ddbd-64ff-44a8-bab2-3c926609e655.png)

It gives an command not found error. If you see the locust installation screenshot its asking to add ```/home/ubuntu/.local/bin``` in PATH. So, for this run ```export PATH=/home/ubuntu/.local/bin/:$PATH```

![4](https://user-images.githubusercontent.com/74168188/201895145-4195ac59-370d-457f-84ea-051706523650.png)

Now, again run ```locust -V```

![5](https://user-images.githubusercontent.com/74168188/201896141-eb6fc6a1-0ff3-4a65-8245-154dca0dd9cd.png)

This time it works...

###### Step-4: Done! Now create your first test

A Locust test is essentially a Python program. Create python program according to your requirements. [Here](https://docs.locust.io/en/stable/writing-a-locustfile.html#writing-a-locustfile) is the official documentation link to create locust file.

Let's understand the architecture:

### Approach-1: Without worker

I had used 1 EC2 instance in which locust and nginx server running with two endpoints /index.html and /test.html

Put the code in a file named locustfile.py in your current directory and run :
```sh
locust -f locustfile.py
```

![6](https://user-images.githubusercontent.com/74168188/199708543-3f7e9f16-0968-4a41-8ff6-19c59741baa4.png)

![7](https://user-images.githubusercontent.com/74168188/199708706-796ad442-3416-4146-b6fd-3a3c40458bd7.png)

Now hit InstancePublicIP:8089 after adding rule for 8089 port in security group. Enter number of users, Spawn rate, and Host.

![8](https://user-images.githubusercontent.com/74168188/199709198-0ddad8ac-8882-49d9-a97e-e9d416eaad96.png)

Now, click on start swarming. And get the statistics, charts, failures, exceptions, current ratio, and download data.

![9](https://user-images.githubusercontent.com/74168188/199709636-52c08f52-0cd8-41a9-a0cc-82b035bcecd0.png)
![10](https://user-images.githubusercontent.com/74168188/199709960-8d4851b6-630a-4d13-887a-01276a9fdefc.png)
![11](https://user-images.githubusercontent.com/74168188/199710055-01a002ae-162f-4926-abd5-ebf59529d49a.png)
![12](https://user-images.githubusercontent.com/74168188/199710263-3bc312b0-0abb-4903-99d0-12e9b8b256aa.png)
![13](https://user-images.githubusercontent.com/74168188/199710270-473c450f-996b-4e91-a175-1a0be30582de.png)
![14](https://user-images.githubusercontent.com/74168188/199710290-4d39f757-2bc7-4ee2-b30a-d2e8b96a2df2.png)

### Approach-2: With worker

I had used 3 EC2 instances, one for locust master, second for locust worker and last for nginx server with two endpoints /index.html and /test.html

[Here](https://docs.locust.io/en/stable/running-distributed.html#running-distributed) is the official documentation for distributed load generation.

Put the code (same as used in Approach-1) in a file named locustfile.py in your current directory and run:

#### From master:

```sh
locust -f locustfile.py --master
```
                
![15](https://user-images.githubusercontent.com/74168188/201899121-f0836b04-0c0a-419d-8e18-5be865a5e64b.png)

#### From worker:

```sh
locust -f locustfile.py --worker --master-host=<MASTER_INSTANCE_IP>
```
                
![16](https://user-images.githubusercontent.com/74168188/201900340-1e78f868-ccdf-4fca-84fd-a4e3b0b3d474.png)
                
If getting error then allow port no. in security group of master.
                
Now hit MASTER_INSTANCE_IP:8089 from browser.

![17](https://user-images.githubusercontent.com/74168188/201902035-cf740db0-ccdc-49c9-94e0-bad72445e107.png)

Enter No. of user, spawn rate and host(don't forget to add http://) then click on start swarming and get the statistics.

![18](https://user-images.githubusercontent.com/74168188/201903141-9ba5dd8d-1d11-48dc-88c3-6875ed0c24fc.png)
![19](https://user-images.githubusercontent.com/74168188/201903206-7b54e440-bb37-435f-8f33-0d481b678ff7.png)
![20](https://user-images.githubusercontent.com/74168188/201903357-3f4413f2-9c79-477e-b35f-e6a12af0738e.png)
![21](https://user-images.githubusercontent.com/74168188/201903454-efa86d03-f2b7-4026-93fb-c926f1be2e60.png)
![22](https://user-images.githubusercontent.com/74168188/201903492-33e9bc7e-5207-47ee-9f45-6d06e8423616.png)
![23](https://user-images.githubusercontent.com/74168188/201903544-8e77d853-250a-4d2a-9a82-67209fc18797.png)
![24](https://user-images.githubusercontent.com/74168188/201903590-f8a70728-36ea-4cf2-a08f-3e11d677cec2.png)
![25](https://user-images.githubusercontent.com/74168188/201903628-7d1e2695-5f75-4d59-a181-9d70cbf68ecc.png)

## Thank you...
