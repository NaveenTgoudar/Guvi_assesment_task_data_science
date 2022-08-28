# Guvi_assesment_task_data_science
def registration():
  import re
  db = open("email_register.txt","r")
 
  username = input("enter the username: ")
  username = username+"@gmail.com"
  
  format = r'\b[A-Za-z.]+@[a-zA-Z]+.[a-zA-Z]{2,}\b'
  if (re.fullmatch(format,username)):
     print("format successfull")
     print(username)
  else:
      print ("invalid")
      registration()

  password = input("enter password: ")
  password1 = input("confirm password:")
  if password != password1:
        print("password doesn't match")
        registration()
  for passowrd in password:
    if len(password)>6 and len(password)<15:
      continue
    else:
      print("password length not matching")
      registration()

  for passowrd in password:
    if re.search("[a-z]",password):
       continue
    else:
      print("password not in lower case")
      registration()

  for passowrd in password:
    if re.search("[A-Z]",password):
       continue
    else:
      print("password dosen't have upper case")
      registration()

  for passowrd in password:
    if re.search("[0-9]",password):
       continue
    else:
      print("password not having numeric")
      registration()
    
  for passowrd in password:
    if re.search("[@#$%^&*()_]",password):
      continue
    else:
      print("password not having Special characters")
      registration()
  print("success")

  db = open("email_register.txt","a")
  db.write(username+" "+password+"\n")
registration()
