#当当阅读银铃铛最大累积量
========================
#通过阅读每天最大获取银铃铛750（保质期为7天）  
#每天可取出100进行转换，转换为116左右不等（保质期为91天），次日到账，采用正态分布  
import numpy as np  
days=1    #第n天  
balance=650    #总余额  
lt_bal=[650]    #每日余额所构成的数列  
lt_e=enumerate(lt_bal,1)  
def earnings():      
>>>>global balance  
balance+=650  
def transform():  
global balance,tfd  
generator=np.random.RandomState(0)  
tfd=generator.normal(116,0.6,days)  
balance+=int(tfd[days-1])  
for day,bal in lt_e:    #从第二天开始进入循环  
if day<=7:  
earnings()  
transform()  
elif day<=(91+1):  
transform()  
else:  
transform()  
balance-=int(tfd[day-92])  
lt_bal.append(balance)  
days+=1  
if lt_bal[days-1]<=lt_bal[days-2]:  
break  
print('第{0}天：总余额为{1}'.format(day,bal))  
#得到最大累计值为15713  
#可以购买157.13元以下的电子书  
