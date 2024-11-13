

This command will convert to Root User
```shell
sudo su
```

```shell
yum update
```

```shell
yum install git
```

```shell
git clone 'github/repo/link'
```


### **Installing Python2-pip in EC2 instance**
```shell
yum install python3-pip
```

```shell
python3 -m pip install -r requirements.txt
```

### **To overcome this Error we have to Explicitly install the `streamlit`**

![[Pasted image 20241026231440.png]]


```shell
python3 -m pip install --ignore-installed streamlit
```

### **Install some packages individually**

```
pip install selenium
pip install bs4
pip install python-dotenv
pip install langchain-ollama
```

### **Run the `streamlit` application**

```shell
python3 -m streamlit run main.py
```


```shell
sudo chmod +x /home/ec2-user/ecp-project-ai-webscarper/chromedriver-linux64/chromedriver
```



