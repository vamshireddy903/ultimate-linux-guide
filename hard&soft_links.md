# 1️⃣ Hard Link  
A hard link is another name for the same file on disk

- Points directly to the inode (actual data)  
- Original file + hard link = same data  
- Deleting one does not delete the data (as long as one link exists)

# Key rules

- Cannot link directories  
- Cannot cross file systems  
- Works only on same disk

**Example**  

    ln file1.txt file1_hard.txt

Both files are the same data.

<img width="521" height="727" alt="image" src="https://github.com/user-attachments/assets/d3e96aba-e305-42ca-a37e-8709bc197554" />

<img width="1017" height="513" alt="image" src="https://github.com/user-attachments/assets/f11f4004-86df-4321-a163-d8222dba5f07" />

Example (real)

File is in:

    /mnt/data/app.log (mounted disk)

You try to create a link in:

    /var/log/app.log (root disk)

That is cross filesystem.

Hard link ❌ (not allowed)

    ln /mnt/data/app.log /var/log/app.log


❌ Error: Invalid cross-device link

Because hard links must be on the same filesystem.

Soft link ✅ (allowed)  

     ln -s /mnt/data/app.log /var/log/app.log

✅ Works, because soft links store only the path, not the data.

# 2️⃣ Soft Link (Symbolic Link)

A soft link is like a shortcut pointing to another file or directory.

Points to path, not data  
If original file is deleted → link breaks  
Can link directories  
Can cross file systems  

**Example**
```
ln -s /var/log/nginx/access.log nginx.log

```
**Example**

1️⃣ Config file linking (very common)  
Instead of copying config files everywhere:

    ln -s /opt/configs/app.conf /etc/app/app.conf

Why used

- Single source of truth  
- Update config once → app uses new config  
- Avoids duplicate files  

<img width="530" height="657" alt="image" src="https://github.com/user-attachments/assets/aa744096-08d8-4657-950f-30d3206955c9" />

<img width="489" height="664" alt="image" src="https://github.com/user-attachments/assets/dafcf619-8e17-4941-993e-113875faaccb" />

<img width="816" height="630" alt="image" src="https://github.com/user-attachments/assets/a0ac4c40-7129-4267-8298-7bdf5a5b7f5d" />

<img width="740" height="538" alt="image" src="https://github.com/user-attachments/assets/b3bea1d0-d078-48b7-9571-d12994d7a4ca" />


<img width="645" height="595" alt="image" src="https://github.com/user-attachments/assets/b68e3deb-7389-4cc3-a5ad-f001adf126ed" />


<img width="1184" height="602" alt="image" src="https://github.com/user-attachments/assets/7752a7d9-8fb3-4f9b-a8b3-47a231b120ab" />



