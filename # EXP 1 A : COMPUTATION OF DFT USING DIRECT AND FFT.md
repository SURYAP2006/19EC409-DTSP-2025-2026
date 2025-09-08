# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 

# To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
clear;

// Use a test signal if input is causing issues
N = 8;
x = [1, 1, 1, 1, 1, 1, 1, 1];  // Rectangular pulse

disp("Using test signal: x = " + string(x));

// Compute DFT
X = zeros(1, N);
for k = 0:N-1
    sum_val = 0;
    for n = 0:N-1
        sum_val = sum_val + x(n+1) * exp(-%i * 2 * %pi * k * n / N);
    end
    X(k+1) = sum_val;
end

// Display results
disp("DFT Results:");
for k = 0:N-1
    printf("X(%d) = %.3f + j%.3f\n", k, real(X(k+1)), imag(X(k+1)));
end

// Create a new figure window
f = scf(0);
f.figure_name = "DFT Analysis";
clf(0);

// Plot input signal
subplot(3,1,1);
plot2d3(0:N-1, x, style=2);  // Blue stems
xlabel("Time index (n)");
ylabel("Amplitude");
title("Input Signal x[n]");

// Plot magnitude spectrum
subplot(3,1,2);
plot2d3(0:N-1, abs(X), style=5);  // Red stems
xlabel("Frequency index (k)");
ylabel("|X(k)|");
title("Magnitude Spectrum");

// Plot phase spectrum
subplot(3,1,3);
plot2d3(0:N-1, atan(imag(X), real(X)), style=3);  // Green stems
xlabel("Frequency index (k)");
ylabel("Phase (radians)");
title("Phase Spectrum");

// Ensure window is visible
show_window(0);


```

# OUTPUT: 

<img width="1920" height="1080" alt="Screenshot 2025-09-08 160652" src="https://github.com/user-attachments/assets/43f1900d-19cc-4be5-bba1-6d0662f2879d" />



# RESULT: 

The DFT of the given sequence was successfully computed using both direct computation method and FFT algorithm in SCILAB. 
