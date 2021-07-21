# Welcome to AWS-Training-Task-2


## Task 2
1. Create a key pair 
2. Create a security group
3. Launch an instance using the above created key pair and security group.
4. Create an EBS volume of 1 GB.
5. The final step is to attach the above created EBS volume to the instance you created in the previous steps.


### Stepwise Implementation:

#### Step 1: Create a key pair

 Key name: Task2Key
 
``` aws ec2 create-key-pair --key-name Task2Key```

#### Output:

![image](https://user-images.githubusercontent.com/75135128/126039189-77a3547b-d8fa-4692-895f-4d6d3ce696e1.png)

#### Step 2: Create a security group

 security group name: aws-task2-allowall
 
``` aws ec2 create-security-group --group-name aws-task2-allowall --description "Allow all traffic"```

#### Output:

![image](https://user-images.githubusercontent.com/75135128/126039263-88d1cfe5-d4d0-46af-8163-6484fe10e19e.png)

#### Note: There is no rule in above Security Group.

![image](https://user-images.githubusercontent.com/75135128/126039337-fffec66e-4966-40ee-819c-bfa7bfc9e425.png)

#### Create rule that allow all traffic

``` aws ec2 authorize-security-group-ingress --group-name aws-task2-allowall --protocol all --cidr 0.0.0.0/0```

#### Output:

![image](https://user-images.githubusercontent.com/75135128/126039384-66736f2e-3fa7-43f8-a756-a7b7e91efaba.png)

#### Step 3: Launch an instance using the above created key pair and security group.

``` aws ec2 run-instances --image-id ami-00bf4ae5a7909786c --instance-type t2.micro --count 1 --key-name Task2Key --security-group-ids sg-02f0d54f37070f560```
#### Output:

![image](https://user-images.githubusercontent.com/75135128/126039566-38ccc42a-a0fc-4cdd-89a0-f1224c630c23.png)

#### Step 4: Create an EBS volume of 1 GB.

``` aws ec2  create-volume --volume-type gp2  --size 1  --availability-zone ap-south-1b```

#### Output:

![image](https://user-images.githubusercontent.com/75135128/126039693-5302f4fb-e57a-43c4-a87d-5b4d1cb42b80.png)

#### Attach the above created EBS volume to the instance you created in the previous steps.

```aws ec2 attach-volume --instance-id i-0af875947f5e766f5 --volume-id vol-0389acab0065c118c --device /dev/xvdh```

#### Output:

![image](https://user-images.githubusercontent.com/75135128/126040317-9cf3e70b-cffb-4d4a-b1d2-89c62fe7ce9b.png)




Link for other tasks

[Task 1]()  [Task 2]()  [Task 3]()  [Task 4]()  [Task 5]()
