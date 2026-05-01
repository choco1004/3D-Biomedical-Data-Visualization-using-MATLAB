# 3D-Biomedical-Data-Visualization-using-MATLAB
3D Biomedical Data Visualization using MATLAB

- Visualized systolic blood pressure, glucose level, and cholesterol data
- Generated a 3D scatter plot for patient-level biomedical feature analysis
- Demonstrated exploratory data visualization for AI-driven healthcare analytics


clc;
clear;
close all;

% Sample medical data
blood_pressure = [120; 130; 125; 140; 135; 150; 128; 132; 145; 138];
glucose        = [90; 110; 100; 130; 125; 140; 95; 105; 135; 120];
cholesterol    = [180; 200; 190; 220; 210; 230; 185; 195; 225; 205];

% Create table
T = table(blood_pressure, glucose, cholesterol);

% Save as CSV
writetable(T, 'blood_pressure_data.csv');

% 3D scatter plot
figure;
scatter3(T.blood_pressure, T.glucose, T.cholesterol, ...
    80, T.cholesterol, 'filled');

grid on;
xlabel('Systolic Blood Pressure');
ylabel('Glucose Level');
zlabel('Cholesterol');
title('3D Scatter Plot of Patient Medical Data');
colorbar;
view(45, 30);
