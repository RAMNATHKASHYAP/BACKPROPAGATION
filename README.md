# BACKPROPAGATION


We have the error E=E1+E2 & we will try to minimize the error through backpropagation .
calculating the values we have to use for back propgation:

STEP 1 :   

h1=w1*i1+w2*i2
h2=w3*i1+w4*i2
a_h1=σ(h1)=1/(1+exp(-h1))
a_h2=σ(h2)
o1=w5*a_h1+w6*a_h2
o2=w7*a_h1+w8*a_h2
a_o1=σ(o1)
a_o2=σ(o2)
E_total=E1+E2
E1=1/2*(t1-a_o1)^2
E2=1/2*(t2-a_o2)^2


STEP 2:

∂E_total/∂w5=∂(E1+E2)/∂w5				
∂E_total/∂w5=∂E1/∂w5				
∂E_total/∂w5=∂E1/∂w5=∂E1/∂a_o1*∂a_01/∂o1*∂o1/∂w5				
∂E1/∂a_o1=∂(1/2*(t1-a_o1)^2)/∂a_o1=(a_01-t1)				
∂a_o1/∂o1=∂(σ(o1))/∂o1=a_o1*(1-a_o1)				
∂o1/∂w5=a_h1				

STEP 3:

∂E_total/∂w5=(a_01-t1)*a_01*(1-a_o1)*a_h1		
∂E_total/∂w6=(a_01-t1)*a_01*(1-a_o1)*a_h2		
∂E_total/∂w7=(a_02-t2)*a_02*(1-a_o2)*a_h1		
∂E_total/∂w8=(a_02-t2)*a_02*(1-a_o2)*a_h2		

STEP 4 :

∂E1/∂a_h1=(a_01-t1)*a_01*(1-a_01)*w5					
∂E1/∂a_h1=(a_02-t2)*a_02*(1-a_02)*w7					
∂E_total/∂a_h1=(a_01-t1)*a_o1*(1-a_o1)*w5+(a_02-t2)*a_o2*(1-a_o2)*w7					
∂E_total/∂a_h2=(a_01-t1)*a_o1*(1-a_o1)*w6+(a_02-t2)*a_o2*(1-a_o2)*w8					

STEP 5 :

∂E_total/∂w1=∂E_total/∂a_h1*∂a_h1/∂h1*∂h1/∂w1	
∂E_total/∂w2=∂E_total/∂a_h1*∂a_h1/∂h1*∂h1/∂w2	
∂E_total/∂w3=∂E_total/∂a_h2*∂a_h2/∂h2*∂h2/∂w3	

STEP 6 :

∂E_total/∂w1=((a_01-t1)*a_o1*(1-a_o1)*w5+(a_o2-t2)*a_o2*(1-a_o2)*w7)*a_h1*(1-a_h1)*i1				
∂E_total/∂w2=((a_01-t1)*a_o1*(1-a_o1)*w5+(a_o2-t2)*a_o2*(1-a_o2)*w7)*a_h1*(1-a_h1)*i2				
∂E_total/∂w3=((a_01-t1)*a_o1*(1-a_o1)*w6+(a_o2-t2)*a_o2*(1-a_o2)*w8)*a_h2*(1-a_h2)*i1				
∂E_total/∂w4=((a_01-t1)*a_o1*(1-a_o1)*w6+(a_o2-t2)*a_o2*(1-a_o2)*w8)*a_h2*(1-a_h2)*i2				


CACLCULATION 1ST STEP(1ST ROW OF EXCEL)

Now I have taken some random value of t1=0.01,t2=0.99,i1=0.5,i2=0.1,w1=0.15,w2=0.2,w3=0.25,w4=0.3,w5=0.4,w6=0.45,w7=0.5,w8=0.55  All the other values 
(h1,a_h1,h2,a_h2,o1,a_o1,o2,a_o2,E1,E2,E,∂E/∂w1,∂E/∂w2,∂E/∂w3,∂E/∂w4,∂E/∂w5,∂E/∂w6,∂E/∂w7,∂E/∂w8

CALCULATION 2ND STEO (2ND TO MORE ROWS OF EXCEL)

t1=0.01,t2=0.99,i1=0.5,i2=0.01 shall be fixed
w1,w2,w3,w4,w5,w6,w7,w8 shall change as per formula (w-(learning rate* ∂E/∂w))
accordingly all the other values changes as per above mentioned formula & same  goes for multiple iteration.

SNAPSHOT OF EXCEL :

![image](https://user-images.githubusercontent.com/21935962/212467946-58e17e85-02f2-494f-a787-44a2a81e6a64.png)

loss graph (For lerning rate 0.1,0.2,0.5,0.8,1,2)

![image](https://user-images.githubusercontent.com/21935962/212467996-345b0b7d-6ed4-4d45-b100-f7180545a61e.png)

![image](https://user-images.githubusercontent.com/21935962/212468007-ad3e2e11-6254-4714-a8b2-f1686ca39f37.png)

![image](https://user-images.githubusercontent.com/21935962/212468023-2dfa8d27-4c9d-46b6-8f5e-5be98db8c9ab.png)

![image](https://user-images.githubusercontent.com/21935962/212468040-dcfeb617-3e98-44ff-8976-4250fedb58a3.png)

![image](https://user-images.githubusercontent.com/21935962/212468055-734ba0ba-b462-412c-b246-77574d3c0028.png)

![image](https://user-images.githubusercontent.com/21935962/212468069-55be1df0-96c3-4b44-bdf2-d6e9238f7fbf.png)


With more iteration loss converges to lower.

We can change random value of t1=0.01,t2=0.99,i1=0.5,i2=0.01 & have look.








