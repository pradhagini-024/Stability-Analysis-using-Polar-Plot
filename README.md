# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
<img width="930" height="1280" alt="image" src="https://github.com/user-attachments/assets/3cd11b1b-a141-44dc-b4d9-76782abecb82" />
<img width="944" height="1280" alt="image" src="https://github.com/user-attachments/assets/140861e1-b9d2-414b-84ba-96300528bc16" />


## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[1]
den=[conv(1,0),conv(1,0.5),conv(1,0.2)]
sys=tf(num,den)
w=logspace(-1,2,1000)
[mag phase]=bode(sys,w)
mag=squeeze(mag)
phase=squeeze(phase)
theta=deg2rad(phase)
polarplot(theta,mag,'LineWidth',1.5)
[gm pm wpc wgc]=margin(sys)
if (wpc>wgc)
    disp('stable')
elseif (wpc==wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```

## Output:
<img width="713" height="640" alt="image" src="https://github.com/user-attachments/assets/6a00cb9d-b6c0-4bbc-a401-dfe12abd0a89" />

## Result:
```
Thus the polar plot for the given transfer function was drawn and verified using MATLAB.
Gain margin = 0.7
Phase Margin = -8.8865
Gain crossover frequency = 3.7565
Phase crossover frequency = 3.1623
The system is unstable.
```
