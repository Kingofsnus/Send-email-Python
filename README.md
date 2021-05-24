# Send-email-Python
How to send email using python
import smtplib

#Who take u mail
S_reciver = ''
#You gmail data
R_sender = ''
password = ''
#Title
subject = ''
#Text
body = ''

#Text 
message = f'''From: {R_sender}
To: {S_reciver}
Subject: {subject}\n
{body}
'''

#send
try:
    server = smtplib.SMTP('smtp.gmail.com', 587)
    server.starttls()

    #Login
    server.login(R_sender,password)
    print('loged in ')
    server.sendmail(R_sender,S_reciver,message)
    print('U send message')


except smtplib.SMTPNotSupportedError:
    print('Support error')
