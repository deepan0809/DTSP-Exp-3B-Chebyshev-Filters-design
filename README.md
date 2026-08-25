# EXP 3B: IIR-CHEBYSHEV-FITER-DESIGN

## AIM: 

 To design an IIR Chebyshev filter  using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM (LPF): 
```
clc;
clear;
close;

Fs = 1000;       
Fc = 100;       
N = 5;          
Rp = 0.2;        

Wc = Fc/Fs;


Hz = iir(N, "lp", "cheb1", [Wc, 0], [Rp, 0]);

[H, f] = frmag(Hz, 512);


plot(f, 20*log10(abs(H)));
xlabel("Normalized Frequency");
ylabel("Magnitude (dB)");
title("IIR Chebyshev Type-I Low Pass Filter");
xgrid();

```


## PROGRAM (HPF): 
```
clc;
clear;
close;


Fs = 1000;      
Fc = 200;        
N = 5;          
Rp = 0.2;       

Wc = Fc/Fs;


Hz = iir(N, "hp", "cheb1", [Wc, 0], [Rp, 0]);


[H, f] = frmag(Hz, 512);


plot(f, 20*log10(abs(H)));
xlabel("Normalized Frequency");
ylabel("Magnitude (dB)");
title("IIR Chebyshev Type-I High Pass Filter");
xgrid();


```

## PROGRAM (BPF):
```
clc;
clear;
close;

Fs = 1000;       // Sampling frequency
Fc1 = 200;       // Lower cut-off frequency
Fc2 = 400;       // Upper cut-off frequency
N = 5;           // Filter order
Rp = 0.2;        // Passband ripple in dB


Wc1 = Fc1/Fs;
Wc2 = Fc2/Fs;


Hz = iir(N, "bp", "cheb1", [Wc1, Wc2], [Rp, 0]);



[H, f] = frmag(Hz, 512);


plot(f, 20*log10(abs(H)));
xlabel("Normalized Frequency");
ylabel("Magnitude (dB)");
title("IIR Chebyshev Type-I Band Pass Filter");
xgrid();
```


## PROGRAM (BSF): 
```
clc;
clear;
close;

Fs = 1000;       // Sampling frequency
Fc1 = 200;       // Lower stopband frequency
Fc2 = 400;       // Upper stopband frequency
N = 5;           // Filter order
Rp = 0.2;        // Passband ripple in dB

Wc1 = Fc1/Fs;
Wc2 = Fc2/Fs;

Hz = iir(N, "sb", "cheb1", [Wc1, Wc2], [Rp, 0]);



[H, f] = frmag(Hz, 512);

// Plot frequency response
plot(f, 20*log10(abs(H)));
xlabel("Normalized Frequency");
ylabel("Magnitude (dB)");
title("IIR Chebyshev Type-I Band Stop Filter");
xgrid();
```


## OUTPUT (LPF) : 
<img width="767" height="712" alt="image" src="https://github.com/user-attachments/assets/a50522c0-b414-41ec-9a62-cb68d1379449" />


## OUTPUT (HPF) : 
<img width="774" height="752" alt="image" src="https://github.com/user-attachments/assets/9b726006-2113-43b2-aafb-f0541bffff7e" />

## OUTPUT (BPF) : 
<img width="755" height="693" alt="image" src="https://github.com/user-attachments/assets/686b4f6f-f8d6-4391-8c86-c9e642f6e712" />


## OUTPUT (BSF) : 
<img width="761" height="697" alt="image" src="https://github.com/user-attachments/assets/7d677ec5-a082-49cf-a248-35bfc7beabf7" />


## RESULT: 
The IIR Chebyshev Type-I digital filters namely Low Pass Filter (LPF), High Pass Filter (HPF), Band Pass Filter (BPF), and Band Stop Filter (BSF) were successfully designed using Scilab. The corresponding frequency responses were obtained and plotted. The LPF passes low-frequency components, HPF passes high-frequency components, BPF passes a selected range of frequencies, and BSF attenuates a selected range of frequencies.
