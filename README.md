# example-banch

### เลข has อาจไม่เหมือนกัน เนื่องจากความแตกต่างของเครื่อง


1. ทำการ ใช้ git Clone `https://github.com/nethuhu33799/ex-banch.git` repository ใน cmd หน้า desktop
    ```bash
    $ git clone https://github.com/nethuhu33799/ex-banch.git
    ```
    เข้าไปหา โฟรเดอร์ที่เรา clone มา
    ```bash
    $ cd ex-banch
    ```
2. ใช้ ``` git log --all --oneline --graph```
    ```bash
    $ git log --all --oneline --graph
    * bd8be80 (HEAD -> main, origin/main, origin/HEAD) commit-2
    * 5907e96 commit-1
    * a68d0f2 Initial commit
    ```


3. ทำการตั้งค่า Configure 
    ```bash
    $ git config --global user.name "<ชื่อน้องไงก็ได้>" 
    $ git config --global user.email "<xxx+nethuhu33799@users.noreply.github.com.>"
    ```

4. สร้าง branch ใหม่ชื่อ `from_commit-2` 
    
    * ก่อนสร้าง
    ```bash
    $ git log --all --oneline --graph
    * bd8be80 (HEAD -> main, origin/main, origin/HEAD) commit-2
    * 5907e96 commit-1
    * a68d0f2 Initial commit
    ```
    ใช้คำสั่งสร้าง branch ``` git branch from_commit-2```
    * หลังสร้าง
    ```bash
    $ git log --all --oneline --graph
    * bd8be80 (HEAD -> main, origin/main, origin/HEAD, from_commit-2) commit-2
    * 5907e96 commit-1
    * a68d0f2 Initial commit
    ``` 

    ***อย่าลืม `git switch from_commit-2`***
    ```bash
    $ git log --all --oneline --graph
    * bd8be80 (HEAD -> from_commit-2, origin/main, origin/HEAD, main) commit-2
    * 5907e96 commit-1
    * a68d0f2 Initial commit
    ```
5. สร้าง 1 commit โดยใช้ข้อความว่า `commit-2.1` ที่ branch `from_commit-2` โดยสร้างไฟล์ `test2-1.md`
    ```bash
    $ git log --all --oneline --graph
    * b6b2afd (HEAD -> from_commit-2) commit-2.1
    * bd8be80 (origin/main, origin/HEAD, main) commit-2
    * 5907e96 commit-1
    * a68d0f2 Initial commit
    ```
6. ใช้ `git switch ` ไป `main` branch.
    ```bash
    git switch main
    ```
    จะเห็นแบบนี้ *สังเกตุความแตกต่าง
    ```bash
    $ git log --all --oneline --graph
    * b6b2afd (from_commit-2) commit-2.1
    * bd8be80 (HEAD -> main, origin/main, origin/HEAD) commit-2
    * 5907e96 commit-1
    * a68d0f2 Initial commit
    ```

7. สร้าง 1 commit โดยใช้ข้อความว่า commit-3 ที่ branch mian โดยสร้างไฟล์ test3.md และเมื่อ log โดยเฉพาะใช้ --all จะได้แบบด้านล่าง
    ```bash
    $ git log --all --oneline --graph
    * 27fbc2c (HEAD -> main) commit-3
    | * b6b2afd (from_commit-2) commit-2.1
    |/  
    * bd8be80 (origin/main, origin/HEAD) commit-2
    * 5907e96 commit-1
    * a68d0f2 Initial commit
    ```

16. ทำการ `push` remote repository.
    ```bash
    $ git push -u origin main
    ```
ถ้าทำการ push ครั้งแรก จะใช้แบบ `$ git push -u origin main` เพื่อทำหมด เส้นทางครั้งแรกที่จะส่งไป ครั้งต่อไปทำแค่ `git push`

***สิ่งที่ต้องการให้น้องเห็นคือ เราทำการสร้าง branch และ มองเห็นเส้นทางที่แยกออกมา สามารถ `git switch เห็นถึงความแตกต่าง` เมื่อใช้ `git log --oneline --graph` กับ `git log --oneline --graph --all` ***