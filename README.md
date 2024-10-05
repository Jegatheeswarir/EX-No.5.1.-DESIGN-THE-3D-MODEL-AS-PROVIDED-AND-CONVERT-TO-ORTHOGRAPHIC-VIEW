# EX No.5.1.DESIGN THE 3D MODEL AS PROVIDED AND CONVERT TO ORTHOGRAPHIC VIEW
## DATE:

## AIM: 
To create orthographic view of given 3D model

## REQUIREMENTS: 
1. Autodesk fusion 360
2. Windows 10
3. 16 GB of RAM (integrated graphics recommend 1 GB or more)
4. 2.5 Mbps or faster download; 500 Kbps or faster upload 

## PROCEDURE:

### STEP-1:
Open Fusion 360 and select file and click new file

### STEP-2:
Select sketch option and choose create sketch

### STEP-3: 
1. Create the sketch using circle, line, trim operations as shown in figure
2. Apply finish sketch 

### STEP-4:
 Use the extrude option to convert the 2D to 3D.

### STEP-5:
Switch to drawing mode from design mode 
          
### STEP-6:
1. Select the base view and position the model to project from base view 
2. Select the projected view to generate orthographic projections

## INPUT
![image](https://user-images.githubusercontent.com/113594316/199408705-ed302b2a-90c3-41c0-9cc4-791a93366e2a.png)
## PROGRAM
client
```
import socket
s = socket.socket()
host = socket.gethostname()
port = 60000
s.connect((host, port))
s.send("Hello server!".encode())
with open('received_file', 'wb') as f:
   print('receiving data...')
   while True:
      data = s.recv(1024)
      print('data=%s', (data))
      if not data:
        break
      f.write(data)
print('Successfully get the file')
s.close()
print('connection closed')  
```
Server
```
import socket 
port = 60000 
s = socket.socket() 
host = socket.gethostname() 
s.bind((host, port)) 
s.listen(5) 
while True:
    conn, addr = s.accept() 
    data = conn.recv(1024)
    print('Server received', repr(data))
    filename='mytext.txt'
    f = open(filename,'rb')
    l = f.read(1024)
    while (l):
        conn.send(l)
        print('Sent ',repr(l))
        l = f.read(1024)
    f.close()
    print('Done sending')
    conn.send('Thank you for connecting'.encode())
    conn.close()
```
## OUTPUT
![Screenshot 2024-10-05 152827](https://github.com/user-attachments/assets/0dbaf718-6a8f-4acc-aaa1-d78ca72af999)



## RESULT:
Thus, the given 3D model is converted into orthographic view.


