# Design-of-FIR-Filters-using-hamming-window

# DESIGN OF LOW PASS FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of high pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
# LPF
```

clc;
clear;
close;

N = input("Enter filter length (odd) = ");
Wc = input("Enter cutoff frequency (0 to %pi) = ");

alpha = (N-1)/2;

for n = 0:N-1
    
    if n == alpha then
        hd(n+1) = Wc/%pi;
    else
        hd(n+1) = sin(Wc*(n-alpha))/(%pi*(n-alpha));
    end
    
    // Hamming Window
    w(n+1) = 0.54 - 0.46*cos((2*%pi*n)/(N-1));
    
    h(n+1) = hd(n+1)*w(n+1);

end

[H,f] = frmag(h,256);

subplot(2,1,1)
plot2d(f/%pi,H)
title("Magnitude Response of LPF (Hamming Window)")

subplot(2,1,2)
plot2d(f/%pi,20*log10(H))
title("Magnitude in dB")

```
# HPF
```
clc;
clear;
close;

N = input("Enter filter length (odd) = ");
Wc = input("Enter cutoff frequency = ");

alpha = (N-1)/2;

for n = 0:N-1
    
    if n == alpha then
        hd(n+1) = 1 - Wc/%pi;
    else
        hd(n+1) = -sin(Wc*(n-alpha))/(%pi*(n-alpha));
    end
    
    w(n+1) = 0.54 - 0.46*cos((2*%pi*n)/(N-1));
    h(n+1) = hd(n+1)*w(n+1);

end

[H,f] = frmag(h,256);

subplot(2,1,1)
plot2d(f/%pi,H)
title("Magnitude Response HPF")

subplot(2,1,2)
plot2d(f/%pi,20*log10(H))
Title("Magnitude in dB")

```
# BPF
```
clc;
clear;
close;

N = input("Enter filter length = ");
Wc1 = input("Enter lower cutoff = ");
Wc2 = input("Enter upper cutoff = ");

alpha = (N-1)/2;

for n = 0:N-1
    
    if n == alpha then
        hd(n+1) = (Wc2-Wc1)/%pi;
    else
        hd(n+1) = (sin(Wc2*(n-alpha)) - sin(Wc1*(n-alpha)))/(%pi*(n-alpha));
    end
    
    w(n+1) = 0.54 - 0.46*cos((2*%pi*n)/(N-1));
    h(n+1) = hd(n+1)*w(n+1);

end

[H,f] = frmag(h,256);

subplot(2,1,1)
plot2d(f/%pi,H)
title("Magnitude Response BPF")

subplot(2,1,2)
plot2d(f/%pi,20*log10(H))
title("Magnitude in dB")

```
# BSF
```
clc;
clear;
close;

N = input("Enter filter length = ");
Wc1 = input("Enter lower cutoff = ");
Wc2 = input("Enter upper cutoff = ");

alpha = (N-1)/2;

for n = 0:N-1
    
    if n == alpha then
        hd(n+1) = 1 - (Wc2-Wc1)/%pi;
    else
        hd(n+1) = (sin(Wc1*(n-alpha)) - sin(Wc2*(n-alpha)))/(%pi*(n-alpha));
    end
    
    w(n+1) = 0.54 - 0.46*cos((2*%pi*n)/(N-1));
    h(n+1) = hd(n+1)*w(n+1);

end

[H,f] = frmag(h,256);

subplot(2,1,1)
plot2d(f/%pi,H)
title("Magnitude Response BSF")

subplot(2,1,2)
plot2d(f/%pi,20*log10(H))
title("Magnitude in dB")

```

# OUTPUT
<img width="607" height="133" alt="image" src="https://github.com/user-attachments/assets/8983bce7-d0b3-4a76-876d-fbbec64cd581" />
<img width="1010" height="545" alt="image" src="https://github.com/user-attachments/assets/8a39afab-4a53-4cfd-8bf1-69b0736bf50a" />
<img width="607" height="133" alt="image" src="https://github.com/user-attachments/assets/6d6e7bd8-7475-413a-81ef-437f5616b517" />
<img width="918" height="566" alt="image" src="https://github.com/user-attachments/assets/511a8a3f-257d-450d-94af-5ab904060ee1" />
<img width="406" height="157" alt="image" src="https://github.com/user-attachments/assets/e2848031-b47a-4d39-8cc6-98f240fec910" />
<img width="964" height="503" alt="image" src="https://github.com/user-attachments/assets/d662af38-3a38-47a3-9124-2eb6009ad712" />
<img width="406" height="157" alt="image" src="https://github.com/user-attachments/assets/a9bf25bf-e7b0-4154-8250-817911bcdac7" />
<img width="953" height="489" alt="image" src="https://github.com/user-attachments/assets/a4405b2c-d939-4138-bba0-4d970aedb043" />


# RESULT
