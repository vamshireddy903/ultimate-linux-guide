The tee command reads input from stdin and writes it to both:

1.Standard output (terminal)  
2. One or more files

👉 Like a T-junction pipe.

Basic syntax

    command | tee file.txt

**Simple example**

    echo "Hello DevOps" | tee output.txt

Prints Hello DevOps on terminal  
Saves it to output.txt  

**Why tee is useful (real DevOps use cases)**

1️⃣ Save logs while seeing output

    kubectl get pods | tee pods.txt

- See output  
- Keep record for later

2️⃣ Log script output (very common)
   
    ./deploy.sh | tee deploy.log

- Monitor progress live  
- Debug later if failure occurs

3️⃣ Append instead of overwrite
 
     command | tee -a app.log

4️⃣ Write to multiple files
 
    df -h | tee disk.txt disk_backup.txt

5️⃣ Use with sudo (important trick)

     echo "data" | sudo tee /etc/app.conf
