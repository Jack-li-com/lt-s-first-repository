# lt-s-first-repository
this repository is used to test.
#coding=utf-8
import smtplib
from email.mime.text import MIMEText
msg_from='1981129322@qq.com'        #发送方邮箱
passwd= 'kvxugiwdzocfcehg'      #填入发送方邮箱的授权码
msg_to='57820048@qq.com'#    收件人邮箱

subject="20191441Today_TEST"      #主题
content="i'am2019144159李挺/n  手机ip:10.133.207.169  106.61.158.172/n 校园网ip:10.128.91.111  220.164.161.127/n "
msg = MIMEText (content)
msg[ 'Subject' ] = subject
msg['From'] = msg_from
msg['To'] = msg_to
try:
   s=smtplib.SMTP_SSL("smtp.qq.com", 465)
   s.login(msg_from, passwd)
   s.sendmail (msg_from, msg_to, msg.as_string() )
   print("发送成功")
except (s.SMTPException,e) :
   print ("发送失败")
finally:
   s.quit  ()
