# SIAT_MRIdata200
200 Data for MRI Reconstruction  

% The dataset was provided by Shenzhen Institutes of Advanced Technology, the Chinese Academy of Science.     
% Some of them are used in the following papers:    
% M. Zhang, M. Li, J. Zhou, Y, Zhu, S. Wang, D. Liang, Y. Chen, Q. Liu. High-dimensional embedding network derived prior for compressive sensing MRI reconstruction, Med. Image Anal., vol. xx, pp.1-27, 2020.    
% Q. Liu, Q. Yang, H. Cheng, S. Wang, M. Zhang, D. Liang, Highly undersampled magnetic resonance imaging reconstruction using autoencoding priors, Magn. Reson. Med., vol. 83, no. 1, pp. 322-336, 2020.    
% Y. Liu, Q. Liu, M. Zhang, Q. Yang, S. Wang, D. Liang. IFR-Net: Iterative feature refinement network for compressed sensing MRI, IEEE Trans. Comput. Imag., vol. 6, pp. 434-446, 2020.    
% S. Li, J. Zhou, D. Liang, Q. Liu, MRI denoising using progressively distribution-based neural network, Magn. Reson. Imaging, 2020. https://doi.org/10.1016/j.mri.2020.04.006.    


%% #######%%%%% read test data3 %%%%    
% The original data is the size of 270x256 or 256x270. You need to clip it to be 256x256.      
%load lsq28; Img = imrotate(Img, -90); Img(:,end-6:end) = []; Img(:,1:7) = [];    
%load lsq68;  Img = imrotate(Img, 90); Img(:,end-6:end) = []; Img(:,1:7) = [];    
%load lsq200;  Img = imrotate(Img, 90); Img(:,end-6:end) = []; Img(:,1:7) = [];   
load lsq196; Img = imrotate(Img, 90); Img(:,end-6:end) = []; Img(:,1:7) = [];    
gt = Img./max(abs(Img(:)));    
figure(334);imshow([real(gt),imag(gt),abs(gt)],[]);    
    
    
%% #######%%%%% display data20 %%%%     
index = 1:10:200;    
ddd1 = [];ddd2 = [];        
for ii =1:10        
    load(['lsq',num2str(index(ii)),'.mat']);Img = Img./max(abs(Img(:))); ddd1 = [ddd1,Img];        
    load(['lsq',num2str(index(10+ii)),'.mat']);Img = Img./max(abs(Img(:))); ddd2 = [ddd2,Img];         
end        
ddd1 = [ddd1;ddd2];       
figure(600);imshow(abs(ddd1),[]);     
     
          
%% #######%%%%% read test data200 %%%%    
for ii =1:200      
    load(['lsq',num2str(ii),'.mat']);    
    figure(1000);     
    subplot(1,2,1),imshow(abs(Img),[]);colorbar;    
    Img = Img./max(abs(Img(:)));    
    subplot(1,2,2),imshow(abs(Img),[]);colorbar;    
 end    
 
 
## Visual illustration of the Real and Imaginary component
![](./real_imag_abs.png)  
Left：Real component, Middle: Imaginary component, Right: Magntitude image.   

## Visual illustration of 20 data
![](./display20.png)  

 

## Other Related Projects
  * Multi-Channel and Multi-Model-Based Autoencoding Prior for Grayscale Image Restoration  
[<font size=5>**[Paper]**</font>](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8782831)   [<font size=5>**[Code]**</font>](https://github.com/yqx7150/MEDAEP)   [<font size=5>**[Slide]**</font>](https://github.com/yqx7150/EDAEPRec/tree/master/Slide)

  * Denoising Auto-encoding Priors in Undecimated Wavelet Domain for MR Image Reconstruction  
 [<font size=5>**[Paper]**</font>](https://arxiv.org/ftp/arxiv/papers/1909/1909.01108.pdf)   [<font size=5>**[Code]**</font>](https://github.com/yqx7150/WDAEPRec)

  * Learning Priors in High-frequency Domain for Inverse Imaging Reconstruction  
[<font size=5>**[Paper]**</font>](https://arxiv.org/ftp/arxiv/papers/1910/1910.11148.pdf)   [<font size=5>**[Code]**</font>](https://github.com/yqx7150/HFDAEP)

  * Learning Multi-Denoising Autoencoding Priors for Image Super-Resolution  
[<font size=5>**[Paper]**</font>](https://www.sciencedirect.com/science/article/pii/S1047320318302700)   [<font size=5>**[Code]**</font>](https://github.com/yqx7150/MDAEP-SR)

  * Complex-valued MRI data from SIAT  
[<font size=5>**[Data]**</font>](https://github.com/yqx7150/EDAEPRec/tree/master/test_data_31)

 
 
 
   
   







