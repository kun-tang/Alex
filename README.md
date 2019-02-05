# Alex Matlab
clc;
clear all;
a=[1 0 0 -1 0 1 -1];
fangbo(1:20,a)
function [tt yy]=fangbo(t,y)
R=length(y);            %矩阵的长度决定循环次数
dt=t(2)-t(1);           %一个电平的宽度
for i=1:R
    tt((i-1)*101+1:i*101)=t(i):0.01*dt:t(i)+dt; %给tt赋值，精确到0.01，x轴
    yy((i-1)*101+1:i*101)=y(i);                 %给yy赋值，精确到0.01，y轴
end
plot(tt,yy)             %画图并设置y轴范围
ma=max(yy);mi=min(yy);
ylim([mi-1,ma+1]);
end
