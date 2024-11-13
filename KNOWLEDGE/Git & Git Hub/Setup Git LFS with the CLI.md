
## Install Git-LFS
`
```
git lfs install
```

## Declare File Types to track

```
git lfs track ".*ext"
```


## Untracking Files

To stop tracking a file type, you can use the `git lfs untrack` command:

```
git lfs untrack "*.psd"
```
Now make sure `.gitattributes` is tracked:
```
git add .gitattributes
```



## Fetching and Cloning

When cloning a repository that uses Git LFS, the large files will be fetched automatically. If you already have the repository and want to pull the latest large files, use:

```
git lfs fetch
```


## Track the File with Git LFS

```
git lfs track "large_image.png"

```


## List Tracked Files with Git LFS

```
git lfs ls-files
```



# Generate SSH Key on AWS EC2 Instance

### **Connect to the EC2 Instance**

1. Open your terminal or command prompt.
    
2. Use the following command to connect to your EC2 instance:

```shell
ssh -i /path/to/your-private-key.pem ec2-user@<public-dns-or-ip-address>
```

**Replace:**
- `/path/to/your-private-key.pem` with the path to your PEM file.
- `ec2-user` with your instance's user (e.g., `ubuntu` or `ec2-user` depending on the AMI).
- `<public-dns-or-ip-address>` with the public IP or DNS of your instance.

### **Generate the SSH Key Pair on EC2**

Once connected to the EC2 instance, run:

1. **Create the SSH key pair**:
```shell
ssh-keygen -t rsa -b 4096 -C "your-email@example.com"
```
 
**This command:**

- Uses the RSA algorithm with a 4096-bit key size.
- Adds a comment (`-C`) to help you identify the key.


### **Copy Public Key Manually**

1. **Display the Public Key** on the EC2 instance:
```shell
cat ~/.ssh/id_rsa.pub
```
