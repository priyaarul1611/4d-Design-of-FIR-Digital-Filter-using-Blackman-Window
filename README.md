# FIR-FILTER-DESIGN
# EXP 4 d: Design-of-FIR-Digital-Filter-using-Blackman-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Blackman-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = Wc/ %pi ; else 
hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Blackman Window 
for n = 1:M 
W(n) = 0.42-(0.5*cos((2*%pi*(n-1))/(M-1)))+(0.08*cos((4*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR LPF using Blackman Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR LPF using Blackman Window');
```
**CALCULATION:**
<img width="940" height="624" alt="image" src="https://github.com/user-attachments/assets/94872eb9-24a9-42e6-8ba5-9ccaa64ff39d" />
<img width="940" height="944" alt="image" src="https://github.com/user-attachments/assets/577f0942-7629-47a5-b93b-29b89726b4e5" />


# OUTPUT: 
<img width="491" height="457" alt="LPF-Blackman calculation" src="https://github.com/user-attachments/assets/1b06a0ab-ccef-41c5-97ce-1a92766ad8c2" />
<img width="759" height="719" alt="LPF-Blackman graph" src="https://github.com/user-attachments/assets/453db0f3-b62f-483f-a634-0de2344d0949" />

# RESULT: 

Thus design of low pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = 1-Wc/ %pi ; 
else 
hd(n) = -sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Blackman Window 
for n = 1:M 
W(n) = 0.42-(0.5*cos((2*%pi*(n-1))/(M-1)))+(0.08*cos((4*%pi*(n-1))/(M-1))); 
end
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR HPF using Blackman Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR HPF using Blackman Window');
```
**CALCULATION:**
<img width="940" height="1254" alt="image" src="https://github.com/user-attachments/assets/ac5a26eb-8dd6-44c4-9497-9c0650333117" />

# OUTPUT: 
<img width="451" height="479" alt="HPF-Blackman calculation" src="https://github.com/user-attachments/assets/4addd579-4e03-4e2f-9573-373cd1a7c8c1" />
<img width="756" height="718" alt="HPF-Blackman Graph" src="https://github.com/user-attachments/assets/980d25f9-25c3-45c4-8dbb-a3132336b29b" />

# RESULT: 
Thus design of HIGH pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =(Wc2-Wc1)/%pi ; 
else 
hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Blackman Window 
for n = 1:M 
W(n) = 0.42-(0.5*cos((2*%pi*(n-1))/(M-1)))+(0.08*cos((4*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Blackman Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB);  
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Blackman Window'); 
```
**CALCULATION:**
<img width="940" height="1254" alt="image" src="https://github.com/user-attachments/assets/61d7014e-986f-4a0e-bc92-83f2f340a3b7" />

# OUTPUT: 
<img width="556" height="458" alt="BPF-Blackman Calculation" src="https://github.com/user-attachments/assets/741f1f83-ba9a-4814-9b3b-6973b9bd1a9f" />
<img width="771" height="715" alt="BPF-Blackman Graph" src="https://github.com/user-attachments/assets/78bf197c-3543-4f4c-b353-825dcd349780" />

# RESULT: 
Thus design of BAND pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =1-((Wc2-Wc1)/%pi); 
else 
hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Blackman Window 
for n = 1:M 
W(n) = 0.42-(0.5*cos((2*%pi*(n-1))/(M-1)))-(0.08*cos((4*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BSF using Blackman Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Blackman Window');
```
**CALCULATION:**
<img width="940" height="1254" alt="image" src="https://github.com/user-attachments/assets/8187cf88-e51f-4864-b3b6-1b8c4b5bf565" />

# OUTPUT: 
<img width="582" height="512" alt="BSF-Blackman Calculation" src="https://github.com/user-attachments/assets/297f2cfe-4e63-4bb1-87ae-bd833e6ddaec" />
<img width="759" height="723" alt="BSF-Blackman Graph" src="https://github.com/user-attachments/assets/7a445046-6758-4cac-9d21-a8360d5b305f" />

# RESULT: 
Thus design of BAND STOP FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.
