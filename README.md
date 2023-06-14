# Admin-Base
This project manages an index of admin names and dates with the use of databse.
from dateutil import parser
import sys
import datetime
list12=[]
import getpass
min=datetime.datetime(2099,12,31)
password="kijflo"
datetod=datetime.datetime.now()
adminnames=['Jill','Harry','Aditya','Tommy','Okay','Sir','will','Apple']
dict12={"Jill":"01/22/12",'Harry':" 12/12/12",'Aditya':" 12/11/12",'Tommy':" 03/02/11","Okay":"08/23/21","Sir":"11/11/25 ","Will":"02/03/04","Apple":" 08/02/07"}
name=input("what is your name")
name=name.capitalize()
string1=dict12[name]
date123=parser.parse(string1)
print(date123)
if date123>datetod:
  sys.exit()
if name in adminnames:
  mypass1=getpass.getpass("what is the password")
  if mypass1==password:
    answer=input(("do you want to edit"))
    if answer=="yes":
      answer1=input("what name do you want to remove")
      answer1=answer1.capitalize()
      adminnames.remove(answer1)
    else:
      quit()
  else:
    quit()
else:
  quit()
for i in dict12:
 list12.append(parser.parse((dict12[i])))
print(list12)
for i in list12:
  if i<min:
    min=i
for i in dict12:
  if min==parser.parse(dict12[i]):
    print(i)
