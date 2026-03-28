
# 4 A Design of FIR Filters using Rectangular Window

# AIM: 
          
  To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
# a. Design of Low Pass FIR Digital filter
```
clc;
close;

M = input('Enter the Odd Filter Length = ');
Wc = input('Enter the Digital Cut off frequency = ');

alpha = (M-1)/2; // Center value

for n = 1:M
    if (n == alpha+1) then
        hd(n) = Wc/%pi;
    else
        hd(n) = sin(Wc*((n-1)-alpha))/(((n-1)-alpha)*%pi);
    end
end

// Rectangular Window
for n = 1:M
    W(n) = 1;
end

// Windowing filter coefficients
h = hd .* W;

disp("Filter Coefficients:");
disp(h);

[hzm,fr] = frmag(h,256);

subplot(2,1,1)
plot(2*fr,hzm)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR LPF using Rectangular Window');

hzm_dB = 20*log10(hzm);

subplot(2,1,2)
plot(2*fr,hzm_dB)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude in dB');
title('Frequency Response of FIR LPF using Rectangular Window');
```
# Design of High Pass FIR Digital filter
```
clc;
close;

M = input('Enter the Odd Filter Length = ');
Wc = input('Enter the Digital Cut off frequency = ');

alpha = (M-1)/2;

for n = 1:M
    if (n == alpha+1) then
        hd(n) = 1 - (Wc/%pi);
    else
        hd(n) = -sin(Wc*((n-1)-alpha))/(((n-1)-alpha)*%pi);
    end
end

// Rectangular Window
for n = 1:M
    W(n) = 1;
end

h = hd .* W;

disp("Filter Coefficients:");
disp(h);

[hzm,fr] = frmag(h,256);

subplot(2,1,1)
plot(2*fr,hzm)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR HPF using Rectangular Window');

hzm_dB = 20*log10(hzm);

subplot(2,1,2)
plot(2*fr,hzm_dB)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude in dB');
title('Frequency Response of FIR HPF using Rectangular Window');
```
#  Design of Band Pass FIR Digital filter
```
clc;
close;

M = input('Enter the Odd Filter Length = ');
Wc1 = input('Enter the Lower Cut off frequency = ');
Wc2 = input('Enter the Upper Cut off frequency = ');

alpha = (M-1)/2;

for n = 1:M
    if (n == alpha+1) then
        hd(n) = (Wc2 - Wc1)/%pi;
    else
        hd(n) = (sin(Wc2*((n-1)-alpha)) - sin(Wc1*((n-1)-alpha)))/(((n-1)-alpha)*%pi);
    end
end

// Rectangular Window
for n = 1:M
    W(n) = 1;
end

h = hd .* W;

disp("Filter Coefficients:");
disp(h);

[hzm,fr] = frmag(h,256);

subplot(2,1,1)
plot(2*fr,hzm)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR BPF using Rectangular Window');

hzm_dB = 20*log10(hzm);

subplot(2,1,2)
plot(2*fr,hzm_dB)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude in dB');
title('Frequency Response of FIR BPF using Rectangular Window');
```
# Design of Band Stop FIR Digital filter
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc1 = input('Enter the Lower Cut off frequency = ');
Wc2 = input('Enter the Upper Cut off frequency = '); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
    if (n ==alpha+1) 
        hd(n) =1-((Wc2-Wc1)/%pi) ; 
    else 
        hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
    end 
end 
// Rectangular Window
 
for n = 1:M 
    W(n) =1; 
end 
//Windowing filter coefficients 

h = hd.*W; 
disp('Filter Coefficients are') 
disp(h) 

[hzm,fr]= frmag (h,256) ; 

subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of  FIR BSF using Rectangular Window ') 

hzm_dB = 20* log10 (hzm); 

subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Rectangular Window');
```
# OUTPUT
a. Design of Low Pass FIR Digital filte

<img width="2879" height="1799" alt="Screenshot 2026-03-27 181028" src="https://github.com/user-attachments/assets/5a9b300f-4d91-4e3c-be33-eb9c53a7f8a5" />

b. Design of High Pass FIR Digital filter

<img width="2879" height="1799" alt="image" src="https://github.com/user-attachments/assets/39e22ee9-f56e-4c21-b4e4-fb89b35a31af" />

c. Design of Band Pass FIR Digital filter

<img width="2868" height="1799" alt="image" src="https://github.com/user-attachments/assets/a4a60b87-f0f9-4604-9ac7-8f50943641c6" />

d. Design of Band Stop FIR Digital filter

<img width="2868" height="1795" alt="image" src="https://github.com/user-attachments/assets/7d5d8606-e75c-464e-9e4f-3815f9563a8d" />

# RESULT
The FIR Filters were successfully designed using rectangular window Technique.
