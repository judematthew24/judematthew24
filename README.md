from tkinter import*
import sqlite3

root=Tk()
root.title('jude Project')
root.geometry("500x500")
root.mainloop()
conn.commit()
conn.close()

f_name=Entry(root,width=30)
f_name.grid(row=0,column=1,padx=20)
l_name=Entry(root,width=30)
l_name.grid(row=1,column=1,padx=20)
age=Entry(root,width=30)
age.grid(row=2,column=1,padx=20)
address=Entry(root,width=30)
address.grid(row=3,column=1,padx=20)
email=Entry(root,width=30)
email.grid(row=4,column=1,padx=20)

f_name_label=Label(root,text="jude")
f_name_label.grid(row=0,column=0)
l_name_label=Label(root,text="dionio")
l_name_label.grid(row=1,column=0)
age_label=Label(root,text="20")
age_label.grid(row=2,column=0)
address_label=Label(root=3,column=0)
address_label.grid(row=3,column=0)
email_label=Label(root,text="judematthewdionio14@gmail.com")
email_label.grid(row=4,column=0)

submit_btn=Button(root,text="Add Record to Database",command=submit)
submit_btn.grid(row=6,column=0,columnspan=2,pady=10,padx=10,ipadx=100)

query_btn=Button(root,text="Show records",command=query)
query_btn.grid(row=7,column=0,columnspan=2,pady=10,padx=10,ipadx=137)

conn=sqlite3.connect('C:/Users/STUDENT2')
c=conn.cursor()
c.execute("""CREATE TABLE "myinfo"
	("f name"	TEXT,
	"l name"	TEXT,
	"age"	INTEGER,
	"address"	TEXT,
	"email"	TEXT
         )"""
)

def submit():
    #database
    conn=sqlite3.connect('C:/Users/CICT/data.db')

    #create cursor

    c=conn.cursor()
    insert into Table
    c.execute("INSERT INTO studentinfo
    VALUES(:F_name,:L_name,:age,:address,:email)",



              {
                  'f_name':f_name.get(),
                  'l_name':l_name.get(),
                  'age':age.get(),
                  'address':address.get(),
                  'email':email.get(),

         })
    #commit changes
    conn.commmit

    #close connection
    conn.commit

    #cclear thetaxt boxes
    f_name.delete(0,END)
    l_name.delete(0,END)
    age.delete(0,END)
    address.delete(0,END)
    email.delete(0,END)
