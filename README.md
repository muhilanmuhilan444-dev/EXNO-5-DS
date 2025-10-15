# EXNO-5-DS-DATA VISUALIZATION USING MATPLOT LIBRARY

# Aim:
  To Perform Data Visualization using matplot python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
 import matplotlib.pyplot as plt
import numpy as np
x=[0,1,2,3,4,5]
y=[0,1,4,9,16,25]
plt.plot(x,y)
plt.show()
<img width="676" height="464" alt="Screenshot 2025-10-15 222042" src="https://github.com/user-attachments/assets/dfc9900f-c1c0-49fd-b9ab-950878c3c122" />


x1=[1,2,3]
y1=[2,4,1]
plt.plot(x1,y1,label="line 1")
x2=[1,2,3]
y2=[4,1,3]
plt.plot(x2,y2,label="line 2")
plt.xlabel('x-axis')
plt.ylabel('y-axis')
plt.title('Multi-Line Chart')
plt.legend()
plt.show()
<img width="779" height="513" alt="Screenshot 2025-10-15 222318" src="https://github.com/user-attachments/assets/9235aa7b-1636-4ce4-bde7-5c18d4aa0cf6" />


x=[1,2,3,4,5]
y1=[10,12,14,16,18]
y2=[5,7,9,11,13]
y3=[2,4,6,8,10]
plt.fill_between(x,y1,color='blue')
plt.fill_between(x,y2,color='green')
plt.plot(x,y1,color='red')
plt.plot(x,y2,color='black')
plt.legend(['y1','y2'])
plt.show()
<img width="772" height="481" alt="Screenshot 2025-10-15 222459" src="https://github.com/user-attachments/assets/04244034-c326-41a5-b899-ef0c907801a8" />

plt.stackplot(x,y1,y2,y3,labels=['Line 1','Line 2','Line 3'])
plt.legend(loc='upper left')
plt.title('Stacked Line Chart')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.show()
<img width="788" height="521" alt="Screenshot 2025-10-15 222553" src="https://github.com/user-attachments/assets/32d408fd-95c5-48cd-a892-ea027285d222" />

from scipy.interpolate import make_interp_spline
x=np.array([1,2,3,4,5,6,7,8,9,10])
y=np.array([2,4,5,7,8,8,9,10,11,12])
spl=make_interp_spline(x,y)
x1=np.linspace(x.min(),x.max(),100)
y1=spl(x1)
plt.plot(x,y,'*',label='data')
plt.plot(x1,y1,'-',label="spline")
plt.legend()
plt.show()
<img width="654" height="481" alt="Screenshot 2025-10-15 222659" src="https://github.com/user-attachments/assets/df5e8d8f-215d-4357-a1e8-e88237f4cbaf" />

val=[5,6,3,7,2]
names=["A","B","C","D","E"]
plt.bar(names,val,color="blue")
plt.show()
<img width="704" height="464" alt="Screenshot 2025-10-15 222751" src="https://github.com/user-attachments/assets/8345007e-8889-4658-8c77-aa1fa5bdaead" />

x=[0,1,2,3,4,5]
y=[0,1,4,9,16,25]
plt.scatter(x,y,s=30,color="red")
plt.show()
<img width="647" height="472" alt="Screenshot 2025-10-15 222909" src="https://github.com/user-attachments/assets/8b3803a7-4291-4f4b-b9d6-b407990fe7f0" />

x = [1, 2, 3, 4, 5]
y = [10, 15, 20, 25, 30]
sizes = [100, 200, 300, 400, 500]
plt.scatter(x, y, s=sizes, alpha=0.5)
plt.xlabel('x_values')
plt.ylabel('y_values')
plt.title('Bubble Chart')
plt.show()
<img width="810" height="522" alt="Screenshot 2025-10-15 223028" src="https://github.com/user-attachments/assets/02e3d186-dff7-4b4d-87bc-87e64f1a9d94" />

ages=[2,5,70,40,30,45,50,45,43,40,44,60,7,13,57,18,90,77,32,21,20,40]
range=(0,100)
bins=10
plt.hist(ages,bins,range,color='purple',histtype='bar',rwidth=0.8)
plt.xlabel('age')
plt.ylabel('No. Of People')
plt.title('Histogram')
plt.show()
<img width="739" height="526" alt="Screenshot 2025-10-15 223142" src="https://github.com/user-attachments/assets/0a17defb-6d87-4117-8c3d-e5b3f53a3b6b" />


np.random.seed(0)
data=np.random.normal(loc=0,scale=1,size=100)
data
fig,ax=plt.subplots()
ax.boxplot(data)
ax.set_xlabel('Data')
ax.set_ylabel('Values')
ax.set_title('Box Plot')
<img width="812" height="554" alt="Screenshot 2025-10-15 223304" src="https://github.com/user-attachments/assets/ad93ed6e-220c-42a4-be46-4ec1cac27e3e" />

data = [np.random.normal(loc=0, scale=1, size=100),
        np.random.normal(loc=2, scale=1, size=100),
        np.random.normal(loc=1, scale=2, size=100)]
plt.violinplot(data)
plt.xlabel('Groups')
plt.ylabel('Values')
plt.title('Violin Plot')
plt.xticks([1, 2, 3], ['Group 1', 'Group 2', 'Group 3'])
plt.show()
<img width="741" height="531" alt="Screenshot 2025-10-15 223411" src="https://github.com/user-attachments/assets/5ec57ffb-b3e9-4950-b44f-1d937d6c21aa" />


data = np.random.normal(0, 1, 1000)
plt.hist(data, bins=30, density=True, alpha=0.5)
plt.title('Density Plot Example')
plt.xlabel('Values')
plt.ylabel('Density')
from scipy.stats import gaussian_kde
kde = gaussian_kde(data)
x_vals = np.linspace(min(data), max(data), 1000)
plt.plot(x_vals, kde(x_vals), 'r')
plt.show()
<img width="711" height="535" alt="Screenshot 2025-10-15 223534" src="https://github.com/user-attachments/assets/02ebfee9-8147-4990-8180-83d2617ec5f3" />

act=['eat','sleep','work','play']
slices=[3,7,8,6]
color=['r','y','g','b']
plt.pie(slices,labels=act,colors=color,startangle=90,shadow=True,explode=(0.1,0.1,0.1,0.1),radius=1.2,
autopct='%1.1f%%')
plt.legend()
plt.show()
<img width="588" height="483" alt="Screenshot 2025-10-15 223635" src="https://github.com/user-attachments/assets/4e693233-6270-4a5a-a3db-144598eb9175" />

# Result:
The above programm is successfully verified
