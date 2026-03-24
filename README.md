 FIR-FILTER-DESIGN
# EXP 4e: Design-of-FIR-Digital-Filter-using-Barlett-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Barlett-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```asm
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = Wc/ %pi ; 
else 
hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Bartlett Window 
for n = 1:M 
W(n)=1-((2*abs((n-1)-((M-1)/2))/(M-1)); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR LPF using Bartlett Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR LPF using Bartlett Window');
```

# OUTPUT: 

<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/40994cde-eb96-45a4-a754-272fc4377996" />

<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/eacc55a6-b65b-4be9-b61a-7cff19904507" />

<img width="767" height="721" alt="image" src="https://github.com/user-attachments/assets/608b8310-6ed6-48d3-beb8-1cccbbd945db" />
<img width="454" height="440" alt="image" src="https://github.com/user-attachments/assets/104ac2b3-d9f8-4661-8958-6d0db993b8df" />


# RESULT: 

Thus design of low pass FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```asm
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
// Bartlett Window 
for n = 1:M 
W(n)=1-((2*abs((n-1)-((M-1)/2)))/(M-1));  
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR HPF using Bartlett Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR HPF using Bartlett Window');
```

# OUTPUT: 
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/7483feda-ad04-4d0c-9e28-d2198e70a30e" />

<img width="770" height="723" alt="image" src="https://github.com/user-attachments/assets/179ef36f-ee75-4a2f-9ddb-bd9915180c5b" />

<img width="471" height="474" alt="image" src="https://github.com/user-attachments/assets/2c7f380a-1d42-481b-9021-f346ac73bd2e" />

# RESULT: 
Thus design of HIGH pass FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```asm
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
// Bartlett Window 
for n = 1:M 
W(n)=1-((2*abs((n-1)-((M-1)/2)))/(M-1)); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Bartlett Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Bartlett Window');
```

# OUTPUT: 
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/cdf6e30f-b46b-49b2-9fa6-f6f44ce4d5e4" />#
<img width="757" height="721" alt="image" src="https://github.com/user-attachments/assets/ea586119-93b4-441c-ab52-d28136e64039" />
<img width="528" height="456" alt="image" src="https://github.com/user-attachments/assets/7184690e-bd9b-4e16-98c4-74365eb4c33d" />



# RESULT: 
Thus design of BAND pass FIR digital filter using-Barlettr-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```asm
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
// Bartlett Window 
for n = 1:M 
W(n)=1-((2*abs((n-1)-((M-1)/2)))/(M-1));  
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BSF using Bartlett Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Bartlett Window');
```

# OUTPUT: 

<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/c90afde3-ff43-47a8-86f1-87629c6e6b95" />

<img width="755" height="716" alt="image" src="https://github.com/user-attachments/assets/883f4eb8-bf91-4dc0-b1fb-ba1debbb9294" />
<img width="594" height="509" alt="image" src="https://github.com/user-attachments/assets/e046e2cf-e168-42fc-af14-411778a60612" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Barlett-Window waveforms were plotted and output was verified.
