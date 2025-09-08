# EXP 1 : Linear and Circular Convolution

## AIM: 

 To perform Linear and Circular Convolution for two given sequence using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM (Linear Convolution): 

// Linear Convolution
```
clc;
clear;

// Input sequences
x = [1 2 3 4];
h = [1 2 3 4];

m = length(x);
n = length(h);
a = 0:1:m-1;
b = 0:1:n-1;

// Plot input signals
subplot(3,1,1);
plot2d(a, x);
xlabel('Time');
ylabel('Amplitude');
title('Graphical Representation of Input Signal X');

subplot(3,1,2);
plot2d(b, h);
xlabel('Time');
ylabel('Amplitude');
title('Graphical Representation of Impulse Signal h');

// Linear convolution using direct formula
y = zeros(1, m1);

for i = 1:m1
    conv_sum = 0;
    for j = 1:i
        if ((i-j <= n) & (j <= m)) then
            conv_sum = conv_sum  x(j) * h(i-j);
        end
    end
    y(i) = conv_sum;
end

disp(y, 'Convolution Sum using Direct Formula Method = ');

// Plot output signal
subplot(3,1,3);
plot2d(0:1:length(y)-1, y);
xlabel('Time');
ylabel('Amplitude');
title('Graphical Representation of Output Signal y');

```

## PROGRAM (Circular Convolution): 

// Circular Convolution
```
clc;
clear;

// ------------------------------
// Input Sequences
// ------------------------------
x = [1 1 1 1];
h = [1 2 3];

// Lengths
N1 = length(x);
N2 = length(h);
N = max(N1, N2);   // Length for circular convolution

// ------------------------------
// Zero-Padding to Equal Length
// ------------------------------
if N1 > N2 then
    h = [h, zeros(1, N1-N2)];
elseif N2 > N1 then
    x = [x, zeros(1, N2-N1)];
end

disp(x, "Padded x(n) = ");
disp(h, "Padded h(n) = ");

// ------------------------------
// Circular Convolution Computation
// ------------------------------
y = zeros(1, N);

for n = 1:N
    sum = 0;
    for i = 1:N
        j = n - i + 1;
        if j <= 0 then
            j = N + j;
        end
        sum = sum + x(i) * h(j);
    end
    y(n) = sum;
end

disp(y, "Circular Convolution Result y(n) = ");

// ------------------------------
// Plotting Discrete-Time Signals
// ------------------------------

// Input sequence x(n)
n1 = 0:N1-1;
subplot(3,1,1);
plot2d3(n1, x(1:N1), -4); // stem plot
xlabel("n");
ylabel("x(n)");
title("Input Sequence x(n)");

// Impulse response h(n)
n2 = 0:N2-1;
subplot(3,1,2);
plot2d3(n2, h(1:N2), -4); // stem plot
xlabel("n");
ylabel("h(n)");
title("Impulse Response h(n)");

// Circular convolution result y(n)
n = 0:N-1;
subplot(3,1,3);
plot2d3(n, y, -4); // stem plot
xlabel("n");
ylabel("y(n)");
title("Circular Convolution y(n)");

```

## OUTPUT (Linear Convolution): 



## OUTPUT (Circular Convolution): 

<img width="1920" height="1080" alt="Screenshot 2025-09-08 152556" src="https://github.com/user-attachments/assets/fc9edfb7-64eb-4a5d-bfec-975f90985daa" />


## RESULT: 
