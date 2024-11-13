


### **Step 2: Generate a new SSH key**

Use the following command to create a new SSH key (replace `your_email@example.com` with your GitHub email).

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

- If `ed25519` isn't supported, use RSA (less secure but widely supported):
    
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
    

You’ll see a prompt asking where to save the key. Press **Enter** to accept the default location:
```c
Enter file in which to save the key (/home/you/.ssh/id_ed25519):
```

Next, you’ll be prompted to set a **passphrase** (optional but recommended). This adds an extra layer of security.




### **Step 3 : Copy the SSH public key to your clipboard.**

If your SSH public key file has a different name than the example code, modify the filename to match your current setup. When copying your key, don't add any newlines or whitespace.

```shell
# Copies the contents of the id_ed25519.pub file to your clipboard
$ clip < ~/.ssh/id_ed25519.pub

```