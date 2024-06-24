

<br>
<div align="center">
<img src="assets/bench.svg" width="400px"></img>
<h2></h2>
<h3>A Comprehensive Benchmark of Structural Pruning<h3>
<img src="assets/intro.svg" width="100%">
</div>

<p align="center">
  <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/License-MIT-4caf50.svg" alt="License"></a>
  <a href="http://pruning.vipazoo.cn/">
  <img src="assets/button.svg" width="23%" alt="Online Platform">
</a>
  <a href="https://arxiv.org/abs/2301.12900" target="_blank"><img src="https://img.shields.io/badge/arXiv-2301.12900-009688.svg" alt="arXiv"></a>
</p>


[[Platform & Tutorials of PruningBench](http://pruning.vipazoo.cn/)]

PruningBench is a comprehensive benchmark of structural pruning with the following features:



* **Unified Evaluation Framework:** PruningBench employs a unified framework to evaluate existing diverse structural pruning techniques, ensuring more equitable and comprehensible comparisons.
* **Leaderboards**: PruningBench systematically evaluates 16 existing structural pruning methods, encompassing a wide array of models (ResNet18, ResNet50, VGG19, ViT, YOLOv8) and tasks (classification on CIFAR and ImageNet, detection on COCO). PruningBench has now yielded 13 leaderboards and a handful of interesting findings which are not explored previously.  
* **Interfaces**: PruningBench is designed as an expandable package that standardizes experimental settings and eases the integration of new algorithmic implementations. PruningBench provides straightforward interfaces for implementing importance criteria methods and sparsity regularizers, facilitating the development and evaluation of future pruning algorithms. 


For more technical details, please refer to our paper:
> [**PruningBench: A Comprehensive Benchmark of Structural Pruning**](TBD)   
> *Haoling Li, Changhao Li, Mengqi Xue, Gongfan Fang, Sheng Zhou, Zunlei Feng, Huiqiong Wang, Yong Wang, Lechao Cheng, Mingli Song, Jie Song*
> (*[VIPA Lab](https://www.vipazoo.cn/), ZheJiang University* & *[Learning and Vision Lab](http://lv-nus.org/), National University of Singapore*)


Our online [[platform](http://pruning.vipazoo.cn/)] enables users to customize pruning tasks by selecting models, datasets, methods, and hyperparameters, facilitating the reproducibility of the results presented in the paper.

Codes will be made available soon!

### Evaluated Methods

PruningBench has now systematically evaluated 16 structural pruning methods, including importance criteria and sparsity regularizers:  

### Current Leaderboards

The following leaderboards adopt "global pruning with 10% group-wise protection" as the pruning strategy, which is the base setting for each task. For more leaderboards, please visit our [[platform](http://pruning.vipazoo.cn/)].

#### ...

| **Importance** | **Regularizer** | **Rank** | **Base** | **Pruned** | **Δ Acc** | **Pruning Ratio** | **Step Time** | **Reg Time** | **Speed Up**|
|----------------|------------------|----------|----------|------------|----------|-------------------|---------------|--------------| --------------|     
   | OBD-C\*       | N/A                                   | 1  | 78\.35 | 78\.68 | \+0\.33 | 16\.45 M (69\.39%) | 7\.559s  | N/A   | 2x |
   | Taylor\*    | N/A                                   | 2  | 78\.35 | 78\.51 | \+0\.16 | 16\.65 M (70\.24%) | 3\.740s  | N/A   | 2x |
   | FPGM                          | N/A                                   | 3  | 78\.35 | 78\.37 | \+0\.02 | 15\.37 M (64\.84%) | 0\.163s  | N/A   | 2x |
   | MagnitudeL2                | N/A                                   | 4  | 78\.35 | 78\.32 | \-0\.03 | 16\.63 M (70\.17%) | 0\.136s  | N/A   | 2x |
   | BNScale                  | N/A                                   | 5  | 78\.35 | 78\.30 | \-0\.05 | 15\.96 M (67\.32%) | 0\.141s  | N/A   | 2x |
   | ThiNet\*              | N/A                                 | 6  | 78\.35 | 78\.14 | \-0\.21 | 15\.19 M (64\.06%) | 33\.619s | N/A   | 2x |
   | Random\*      | N/A                                   | 7  | 78\.35 | 77\.97 | \-0\.38 | 11\.78 M (49\.70%) | 0\.104s  | N/A   | 2x |
   | CP\*                  | N/A                                   | 8  | 78\.35 | 77\.80 | \-0\.55 | 7\.15 M (30\.15%)  | 2m51s    | N/A   | 2x |
   | MagnitudeL1                | N/A                                   | 9  | 78\.35 | 77\.62 | \-0\.73 | 16\.91 M (71\.34%) | 0\.137s  | N/A   | 2x |
   | OBD-Hessian\*    | N/A                                   | 10 | 78\.35 | 77\.26 | \-1\.09 | 7\.83 M (33\.03%)  | 5m5s     | N/A   | 2x |
   | LAMP                       | N/A                                   | 11 | 78\.35 | 76\.26 | \-2\.09 | 16\.21 M (68\.37%) | 0\.150s  | N/A   | 2x |
   | HRank\*           | N/A                                   | 12 | 78\.35 | 76\.13 | \-2\.22 | 6\.47 M (27\.29%)  | 34m32s   | N/A   | 2x |
   | MagnitudeL2               | GroupLASSO | 1  | 78\.35 | 78\.73 | \+0\.38 | 16\.51 M (69\.66%) | 0\.136s  | 3m5s  | 2x |
   | BNScale                    | BNScale    | 2  | 78\.35 | 78\.36 | \+0\.01 | 15\.97 M (67\.37%) | 0\.141s  | 2m14s | 2x |
   | MagnitudeL2                 | GroupNorm  | 3  | 78\.35 | 78\.30 | \-0\.05 | 15\.03 M (63\.41%) | 0\.136s  | 3m7s  | 2x |
   | BNScale                 | GroupLASSO | 4  | 78\.35 | 78\.24 | \-0\.11 | 15\.86 M (66\.90%) | 0\.141s  | 2m38s | 2x |
   | MagnitudeL2               | GrowingReg  | 5  | 78\.35 | 77\.99 | \-0\.36 | 16\.61 M (70\.06%) | 0\.136s  | 3m1s  | 2x |
   |FPGM                                                 | N/A                                   | 1  | 78\.35 | 78\.02 | \-0\.33 | 10\.23 M (43\.16%) | 0\.163s  | N/A   | 4x |
   | MagnitudeL2                  | N/A                                   | 2  | 78\.35 | 77\.98 | \-0\.37 | 10\.71 M (45\.19%) | 0\.136s  | N/A   | 4x |
   | BNScale                   | N/A                                   | 3  | 78\.35 | 77\.90 | \-0\.45 | 10\.53 M (44\.41%) | 0\.141s  | N/A   | 4x |
   | MagnitudeL1                 | N/A                                   | 4  | 78\.35 | 77\.82 | \-0\.53 | 11\.10 M (46\.81%) | 0\.137s  | N/A   | 4x |
   | Taylor    | N/A                                   | 5  | 78\.35 | 77\.69 | \-0\.66 | 5\.47 M (23\.09%)  | 3\.740s  | N/A   | 4x |
   | OBD\-C\*        | N/A                                   | 6  | 78\.35 | 77\.51 | \-0\.84 | 5\.84 M (24\.64%)  | 7\.559s  | N/A   | 4x |
   | Random\*      | N/A                                   | 7  | 78\.35 | 77\.41 | \-0\.94 | 5\.95 M (25\.11%)  | 0\.104s  | N/A   | 4x |
   | ThiNet\*             | N/A                                   | 8  | 78\.35 | 77\.23 | \-1\.12 | 4\.72  M (19\.91%) | 33\.619s | N/A   | 4x |
   | CP\*                 | N/A                                   | 9  | 78\.35 | 75\.68 | \-2\.67 | 2\.65 M(11\.18%)   | 2m51s    | N/A   | 4x |
   | LAMP                        | N/A                                   | 10 | 78\.35 | 75\.52 | \-2\.83 | 5\.93 M (25\.03%)  | 0\.150s  | N/A   | 4x |
   | OBD\-Hessian\*     | N/A                                   | 11 | 78\.35 | 75\.49 | \-2\.86 | 3\.26 M (13\.75%)  | 5m5s     | N/A   | 4x |
   | HRank\*            | N/A                                   | 12 | 78\.35 | 73\.76 | \-4\.59 | 1\.69 M(7\.11%)    | 34m32s   | N/A   | 4x |
   | BNScale                   | BNScale    | 1  | 78\.35 | 78\.16 | \-0\.19 | 10\.37 M (43\.75%) | 0\.141s  | 2m14s | 4x |
   | MagnitudeL2                  | GroupLASSO | 2  | 78\.35 | 78\.01 | \-0\.34 | 10\.79 M (45\.53%) | 0\.136s  | 3m5s  | 4x |
   | BNScale                   | GroupLASSO | 3  | 78\.35 | 77\.90 | \-0\.45 | 10\.76 M (45\.38%) | 0\.141s  | 2m38s | 4x |
   | MagnitudeL2                  | GroupNorm  | 4  | 78\.35 | 77\.88 | \-0\.47 | 9\.84 M (41\.51%)  | 0\.136s  | 3m7s  | 4x |
   | MagnitudeL2                  | GrowingReg   | 5  | 78\.35 | 77\.86 | \-0\.49 | 10\.77 M (45\.43%) | 0\.136s  | 3m1s  | 4x |   
   | MagnitudeL1                 | N/A                                   | 1  | 78\.35 | 76\.99 | \-1\.36 | 6\.82 M (28\.77%)  | 0\.137s  | N/A   | 8x |
   | MagnitudeL2                  | N/A                                   | 2  | 78\.35 | 76\.38 | \-1\.97 | 6\.89 M (29\.05%)  | 0\.136s  | N/A   | 8x |
   | Random\*      | N/A                                   | 3  | 78\.35 | 76\.13 | \-2\.22 | 2\.98 M (12\.57%)  | 0\.104s  | N/A   | 8x |
   | FPGM                                               | N/A                                   | 4  | 78\.35 | 75\.93 | \-2\.42 | 7\.16 M (30\.20%)  | 0\.163s  | N/A    | 8x | 
   | BNScale                   | N/A                                   | 5  | 78\.35 | 75\.81 | \-2\.54 | 6\.69 M (28\.22%)  | 0\.141s  | N/A   | 8x |
   | OBD\-C\*        | N/A                                   | 6  | 78\.35 | 75\.78 | \-2\.57 | 2\.35 M (9\.92%)   | 7\.559s  | N/A   | 8x |
   | Taylor    | N/A                                   | 7  | 78\.35 | 75\.38 | \-2\.97 | 1\.98 M (8\.34%)   | 3\.740s  | N/A   | 8x |
   | ThiNet\*             | N/A                                   | 8  | 78\.35 | 75\.29 | \-3\.06 | 1\.58 M (6\.68%)   | 33\.619s | N/A   | 8x |
   | OBD\-Hessian\*     | N/A                                   | 9  | 78\.35 | 74\.49 | \-3\.86 | 1\.66 M (7\.02%)   | 5m5s     | N/A   | 8x |
   | LAMP                        | N/A                                   | 10 | 78\.35 | 73\.48 | \-4\.87 | 3\.62 M (15\.27%)  | 0\.150s  | N/A   | 8x |
   | CP\*                 | N/A                                   | 11 | 78\.35 | 72\.39 | \-5\.96 | 0\.97 M (4\.07%)   | 2m51s    | N/A   | 8x |
   | HRank\*            | N/A                                   | 12 | 78\.35 | 70\.54 | \-7\.81 | 0\.64 M (2\.69%)   | 34m32s   | N/A   | 8x |
   | MagnitudeL2                  | GrowingReg   | 1  | 78\.35 | 76\.39 | \-1\.96 | 7\.00 M (29\.52%)  | 0\.136s  | 3m1s  | 8x |
   | MagnitudeL2                  | GroupLASSO | 2  | 78\.35 | 76\.27 | \-2\.08 | 7\.09 M (29\.90%)  | 0\.136s  | 3m5s  | 8x |
   | MagnitudeL2                  | GroupNorm  | 3  | 78\.35 | 75\.93 | \-2\.42 | 7\.18 M (30\.28%)  | 0\.136s  | 3m7s  | 8x |
   | BNScale                   | GroupLASSO | 4  | 78\.35 | 75\.60 | \-2\.75 | 7\.19 M (30\.32%)  | 0\.141s  | 2m38s | 8x |
   | BNScale                   | BNScale    | 5  | 78\.35 | 75\.47 | \-2\.88 | 6\.90 M (29\.12%)  | 0\.141s  | 2m14s | 8x |






| **Importance** | **Regularizer** | **Rank** | **Base** | **Pruned** | **Δ Acc** | **Pruning Ratio** | **Step Time** | **Reg Time** | **Speed Up**|
|----------------|------------------|----------|----------|------------|----------|-------------------|---------------|--------------| --------------|    
   | FPGM                          | N/A                                   | 1 | 78\.588 | 69\.248 | \-9\.34   | 10\.365 M (47\.01\%)  | 0\.937s  | N/A   | 2x |   
   | Random\*      | N/A                                   | 2 | 78\.588 | 68\.810 | \-9\.778  | 9\.305 M (42\.20\%)   | 0\.888s  | N/A      | 2x | 
   | LAMP                         | N/A                                   | 3 | 78\.588 | 68\.724 | \-9\.864  | 10\.169  M (46\.12\%) | 1\.284s  | N/A   | 2x |    
   | MagnitudeL1                 | N/A                                   | 4 | 78\.588 | 68\.602 | \-9\.986  | 10\.375 M (47\.05\%)  | 1\.005s  | N/A     |  2x  |  2x |  
   | MagnitudeL2                 | N/A                                   | 5 | 78\.588 | 68\.316 | \-10\.272 | 10\.346 M (46\.92\%)  | 0\.995s  | N/A     |  2x  |  2x |  
   | OBD\-Hessian\*    | N/A                                   | 6 | 78\.588 | 67\.514 | \-11\.074 | 10\.334  M (46\.87\%) | 6m40s    | N/A      | 2x | 
   | Taylor\*    | N/A                                   | 7 | 78\.588 | 67\.400 | \-11\.188 | 10\.468 M (47\.47\%)  | 27\.634s | N/A      | 2x | 
   | CP\*                 | N/A                                   | 7 | 78\.588 | 67\.400 | \-11\.188 | 10\.334 M (46\.87\%)  | 15m4s    | N/A     |  2x  |  2x |  
   | ThiNet\*             | N/A                                   | 8 | 78\.588 | 63\.914 | \-14\.674 | 6\.439 M (29\.20\%)   | 3m17s    | N/A    | 2x |   
   | MagnitudeL2                 | GrowingReg   | 1 | 78\.588 | 68\.715 | \-9\.873  | 10\.359 M (46\.98\%)  | 0\.995s  | 5h10m31s | 2x | 
   | MagnitudeL2                 | GroupNorm  | 2 | 78\.588 | 68\.594 | \-9\.994  | 10\.363 M (47\.00\%)  | 0\.995s  | 5h21m21s | 2x | 
   | MagnitudeL2                 | GroupLASSO | 3 | 78\.588 | 68\.350 | \-10\.238 | 10\.360 M (46\.98\%)  | 0\.995s  | 5h15m13s | 2x | 
   | MagnitudeL1                 | N/A                                   | 1 | 78\.588 | 63\.120 | \-15\.468 | 6\.57 M (29\.79\%)    | 1\.005s  | N/A    | 4x |   
   | LAMP                         | N/A                                   | 2 | 78\.588 | 62\.538 | \-16\.050 | 6\.08 M (27\.57\%)    | 1\.284s  | N/A    | 4x |   
   | MagnitudeL2                 | N/A                                   | 3 | 78\.588 | 62\.342 | \-16\.246 | 6\.37 M (28\.89\%)    | 0\.995s  | N/A   | 4x |    
   | Taylor\*    | N/A                                   | 4 | 78\.588 | 61\.582 | \-17\.006 | 6\.62 M (30\.01\%)    | 27\.634s | N/A      | 4x | 
   | FPGM                          | N/A                                   | 5 | 78\.588 | 60\.660 | \-17\.928 | 5\.701 M (25\.85\%)   | 0\.937s  | N/A    | 4x |   
   | CP\*                 | N/A                                   | 6 | 78\.588 | 56\.626 | \-21\.962 | 6\.778 M (30\.74\%)   | 15m4s    | N/A      | 4x | 
   | OBD\-Hessian\*    | N/A                                   | 7 | 78\.588 | 54\.796 | \-23\.792 | 6\.39 M (28\.98\%)    | 6m40s    | N/A      | 4x | 
   | ThiNet\*             | N/A                                   | 8 | 78\.588 | 49\.654 | \-28\.934 | 5\.113 M (23\.19\%)   | 3m17s    | N/A     |  2x  |  4x |  
   | Random\*      | N/A                                   | 9 | 78\.588 | 44\.654 | \-33\.954 | 4\.95 M (22\.45\%)    | 0\.888s  | N/A     |  2x  |  4x |  
   | MagnitudeL2                 | GrowingReg   | 1 | 78\.588 | 62\.608 | \-15\.980 | 6\.57 M (29\.81\%)    | 0\.995s  | 5h10m31s | 4x | 
   | MagnitudeL2                 | GroupNorm  | 2 | 78\.588 | 61\.716 | \-16\.872 | 6\.88 M (31\.20\%)    | 0\.995s  | 5h21m21s | 4x | 
   | MagnitudeL2                 | GroupLASSO | 3 | 78\.588 | 61\.340 | \-17\.248 | 6\.57 M (29\.13\%)    | 0\.995s  | 5h15m13s | 4x | 
   | MagnitudeL1                 | N/A                                   | 1 | 78\.588 | 59\.950 | \-18\.638 | 5\.06 M (22\.93\%)    | 1\.005s  | N/A     |  2x  |  8x |  
   | MagnitudeL2                 | N/A                                   | 2 | 78\.588 | 59\.082 | \-19\.506 | 4\.89 M (22\.15\%)    | 0\.995s  | N/A     |  2x  |  8x | 
   | Taylor\*    | N/A                                   | 3 | 78\.588 | 57\.650 | \-20\.938 | 4\.80 M (21\.76\%)    | 27\.634s | N/A      | 8x |
   | LAMP                         | N/A                                   | 4 | 78\.588 | 55\.750 | \-22\.838 | 4\.32 M (19\.57\%)    | 1\.284s  | N/A   | 8x |   
   | FPGM                          | N/A                                   | 5 | 78\.588 | 48\.258 | \-30\.33  | 3\.25 M (14\.74\%)    | 0\.937   | N/A    | 8x |  
   | OBD\-Hessian\*    | N/A                                   | 6 | 78\.588 | 36\.600 | \-41\.988 | 4\.25 M (19\.27\%)    | 6m40s    | N/A   | 8x |   
   | CP\*                 | N/A                                   | 7 | 78\.588 | 42\.574 | \-36\.014 | 5\.253 M (23\.82\%)   | 15m4s    | N/A     |  2x  |  8x | 
   | ThiNet\*             | N/A                                   | 8 | 78\.588 | 28\.422 | \-50\.166 | 2\.669 M (12\.10\%)   | 3m17s    | N/A   | 8x |   
   | Random\*      | N/A                                   | 9 | 78\.588 | 27\.722 | \-50\.866 | 2\.76 M (12\.54\%)    | 0\.888s  | N/A      | 8x |
   | MagnitudeL2                 | GrowingReg   | 1 | 78\.588 | 59\.630 | \-18\.958 | 4\.56 M (20\.66\%)    | 0\.995s  | 5h10m31s | 8x |
   | MagnitudeL2                 | GroupLASSO | 2 | 78\.588 | 57\.312 | \-21\.276 | 4\.59 M (20\.81\%)    | 0\.995s  | 5h15m13s | 8x |
   | MagnitudeL2                 | GroupNorm  | 3 | 78\.588 | 56\.446 | \-22\.142 | 4\.77 M (21\.62\%)    | 0\.995s  | 5h21m21s | 8x |




Resnet-18
| **Importance** | **Regularizer** | **Rank** | **Base** | **Pruned** | **Δ Acc** | **Pruning Ratio** | **Step Time** | **Reg Time** | **Speed Up**|
|----------------|------------------|----------|----------|------------|----------|-------------------|---------------|--------------| --------------|  
 Taylor\* | N/A                                | 1  | 75.61 | 75.93 | +0.32 | 7.79 M (69.42%)  | 1.598s  | N/A      |  2x  |  
 MagnitudeL1            | N/A                              | 2  | 75.61 | 75.80 | +0.19 | 7.47 M (66.62%)  | 0.058s  | N/A     |  2x  | 
 OBD-Hessian\*   | N/A                                | 3  | 75.61 | 75.79 | +0.18 | 4.69 M (41.76%)  | 1m46s   | N/A     |  2x  |
 MagnitudeL2          | N/A                                | 4  | 75.61 | 75.72 | +0.11 | 7.55 M (67.25%)  | 0.261s  | N/A     |  2x  |
 ThiNet\*           | N/A                                | 5  | 75.61 | 75.72 | +0.11 | 7.56 M (67.38%)  | 7.815s  | N/A     |  2x  | 
 BNScale             | N/A                                | 6  | 75.61 | 75.51 | -0.10 | 7.72 M (68.81%)  | 0.263s  | N/A     |  2x  |
 CP\*              | N/A                                | 7  | 75.61 | 75.49 | -0.12 | 7.44 M (66.33%)  | 42.944s | N/A     |  2x  | 
 OBD-C\*     | N/A                                | 8  | 75.61 | 75.32 | -0.29 | 7.61 M (67.81%)  | 4.942s  | N/A     |  2x  | 
 FPGM                   | N/A                                | 9  | 75.61 | 75.16 | -0.45 | 8.21 M (73.20%)  | 0.049s  | N/A     |  2x  | 
 HRank\*            | N/A                                | 10 | 75.61 | 74.90 | -0.69 | 5.12 M (45.63%)  | 9m8s    | N/A     |  2x  | 
 Random\*    | N/A                                | 11 | 75.61 | 74.20 | -1.41 | 5.52 M (49.22%)  | 0.047s  | N/A     |  2x  | 
 LAMP                   | N/A                                | 12 | 75.61 | 73.95 | -1.66 | 6.84 M (60.99%)  | 0.059s  | N/A     |  2x  | 
 BNScale             | GroupLASSO | 1  | 75.61 | 76.05 | +0.44 | 7.77 M (69.29%)  | 0.263s  | 1m19s   |  2x  | 
 BNScale             | BNScale    | 2  | 75.61 | 76.01 | +0.40 | 7.70 M (68.64%)  | 0.263s  | 49.425s |  2x  | 
 MagnitudeL2          | GrowingReg   | 3  | 75.61 | 75.76 | +0.15 | 7.88 M (70.23%)  | 0.261s  | 1m 35s  |  2x  | 
 MagnitudeL2          | GroupLASSO | 4  | 75.61 | 75.57 | -0.04 | 7.55 M (67.30%)  | 0.261s  | 1m33s   |  2x  | 
 MagnitudeL2          | GroupNorm  | 5  | 75.61 | 75.56 | -0.05 | 7.76 M (69.19%)  | 0.261s  | 1m36s   |  2x  | 
 MagnitudeL2          | N/A                                | 1  | 75.61 | 74.01 | -1.60 | 4.43 M (39.51%)  | 0.261s  | N/A     |  4x  | 
 ThiNet\*           | N/A                                | 2  | 75.61 | 73.99 | -1.62 | 2.59 M (23.12%)  | 7.815s  | N/A     |  4x  | 
 OBD-C\*     | N/A                                | 3  | 75.61 | 73.94 | -1.67 | 4.23  M (37.70%) | 4.942s  | N/A     |  4x  | 
 Taylor\* | N/A                                | 4  | 75.61 | 73.83 | -1.78 | 2.98 M (26.52%)  | 1.598s  | N/A     |  4x  | 
 BNScale             | N/A                                | 5  | 75.61 | 73.68 | -1.93 | 5.15 M (45.90%)  | 0.263s  | N/A     |  4x  | 
 MagnitudeL1            | N/A                                | 6  | 75.61 | 73.53 | -2.08 | 4.62 M (41.17%)  | 0.058s  | N/A     |  4x  | 
 FPGM                   | N/A                                | 7  | 75.61 | 73.49 | -2.12 | 5.04  M (44.91%) | 0.049s  | N/A     |  4x  | 
 CP\*              | N/A                                | 8  | 75.61 | 73.18 | -2.43 | 3.13 M (27.94%)  | 42.944s | N/A     |  4x  | 
 OBD-Hessian\*   | N/A                                | 9  | 75.61 | 72.72 | -2.89 | 1.30 M (11.61%)  | 1m46s   | N/A     |  4x  | 
 HRank\*            | N/A                                | 10 | 75.61 | 72.17 | -3.44 | 1.17  M (10.42%) | 9m8s    | N/A     |  4x  | 
 Random\*    | N/A                                | 11 | 75.61 | 71.85 | -3.76 | 2.69 M (23.94%)  | 0.047s  | N/A     |  4x  | 
 LAMP                   | N/A                                | 12 | 75.61 | 70.81 | -4.80 | 3.39 M (30.20%)  | 0.059s  | N/A     |  4x  | 
 MagnitudeL2          | GroupNorm  | 1  | 75.61 | 74.37 | -1.24 | 4.07 M (36.29%)  | 0.261s  | 1m36s   |  4x  | 
 MagnitudeL2          | GrowingReg   | 2  | 75.61 | 74.16 | -1.45 | 4.44 M (39.59%)  | 0.261s  | 1m35s   |  4x  | 
 MagnitudeL2          | GroupLASSO | 3  | 75.61 | 74.15 | -1.46 | 4.45 M (39.67%)  | 0.261s  | 1m33s   |  4x  | 
 BNScale             | GroupLASSO | 4  | 75.61 | 73.99 | -1.62 | 5.12 M (45.63%)  | 0.263s  | 1m19s   |  4x  | 
 BNScale             | BNScale    | 5  | 75.61 | 73.81 | -1.80 | 4.85 M (43.23%)  | 0.263s  | 49.425s |  4x  | 
 MagnitudeL2          | N/A                                | 1  | 75.61 | 71.87 | -3.74 | 2.32 M (20.65%)  | 0.261s  | N/A     |  8x  | 
 BNScale             | N/A                                | 2  | 75.61 | 71.31 | -4.30 | 2.37 M (21.17%)  | 0.263s  | N/A     |  8x  | 
 OBD-C\*     | N/A                                | 3  | 75.61 | 71.27 | -4.34 | 1.43 M (12.71%)  | 4.942s  | N/A     |  8x  | 
 MagnitudeL1            | N/A                                | 4  | 75.61 | 70.51 | -5.10 | 2.27 M (20.20%)  | 0.058s  | N/A     |  8x  | 
 Taylor\* | N/A                                | 5  | 75.61 | 70.34 | -5.27 | 0.78 M (6.92%)   | 1.598s  | N/A     |  8x  | 
 CP\*              | N/A                                | 6  | 75.61 | 70.23 | -5.38 | 1.05 M (9.34%)   | 42.944s | N/A     |  8x  | 
 FPGM                   | N/A                                | 7  | 75.61 | 69.87 | -5.74 | 2.82 M (25.17%)  | 0.049s  | N/A     |  8x  | 
 LAMP                   | N/A                                | 8  | 75.61 | 69.68 | -5.93 | 0.46 M (4.07%)   | 0.059s  | N/A     |  8x  | 
 Random\*    | N/A                                | 9  | 75.61 | 69.48 | -6.13 | 1.34 M (11.93%)  | 0.047s  | N/A     |  8x  | 
 ThiNet\*           | N/A                                | 10 | 75.61 | 69.03 | -6.58 | 0.52 M (4.64%)   | 7.815s  | N/A     |  8x  | 
 OBD-Hessian\*   | N/A                                | 11 | 75.61 | 68.55 | -7.06 | 0.46 M (4.08%)   | 1m46s   | N/A     |  8x  | 
 HRank\*            | N/A                                | 12 | 75.61 | 68.53 | -7.08 | 0.50 M (4.48%)   | 9m8s    | N/A     |  8x  | 
 MagnitudeL2          | GroupNorm  | 1  | 75.61 | 72.10 | -3.51 | 2.20 M (19.65%)  | 0.261s  | 1m36s   |  8x  | 
 MagnitudeL2          | GroupLASSO | 2  | 75.61 | 71.66 | -3.95 | 2.38 M (21.23%)  | 0.261   | 1m33s   |  8x  | 
 MagnitudeL2          | GrowingReg   | 3  | 75.61 | 71.57 | -4.04 | 2.34 M (20.87%)  | 0.261   | 1m35s   |  8x  | 
 BNScale             | GroupLASSO | 4  | 75.61 | 71.50 | -4.11 | 2.49 M (22.18%)  | 0.263   | 1m19s   |  8x  | 
 BNScale             | BNScale    | 5  | 75.61 | 71.44 | -4.17 | 2.36 M (21.00%)  | 0.263   | 49.425s |  8x  | 


VGG-19

| **Importance** | **Regularizer** | **Rank** | **Base** | **Pruned** | **Δ Acc** | **Pruning Ratio** | **Step Time** | **Reg Time** | **Speed Up**|
|----------------|------------------|----------|----------|------------|----------|-------------------|---------------|--------------| --------------|  
 CP\*              | N/A  |                                | 1  | 73.87 | 74.16 | +0.29  | 4.93 M (24.54%)  | 1m2s    | N/A     |   2x  |
 HRank\*            | N/A                                | 2  | 73.87 | 73.63 | -0.24  | 6.24 M (31.08%)  | 13m59s  | N/A     |   2x  |
 MagnitudeL1            | N/A                                | 3  | 73.87 | 73.62 | -0.25  | 7.22 M (35.95%)  | 0.156s  | N/A     |   2x  |
 FPGM                   | N/A                                | 4  | 73.87 | 73.42 | -0.45  | 7.05 M (35.09%)  | 0.346s  | N/A     |   2x  |
 LAMP                    | N/A                                | 5  | 73.87 | 73.32 | -0.55  | 6.26 M (31.18%)  | 0.063s  | N/A     |   2x  |
 ThiNet\*           | N/A                                | 6  | 73.87 | 73.32 | -0.55  | 8.86 M (44.11%)  | 13.528s | N/A     |   2x  |
 OBD-C\*      | N/A                                | 7  | 73.87 | 73.25 | -0.62  | 7.60 M (37.84%)  | 5.813s  | N/A     |   2x  |
 MagnitudeL2            | N/A                                | 8  | 73.87 | 73.22 | -0.65  | 7.14  M (35.55%) | 0.199s  | N/A     |   2x  |
 BNScale              | N/A                                | 9  | 73.87 | 73.12 | -0.75  | 7.15 M (35.62%)  | 0.062s  | N/A     |   2x  |
 Taylor | N/A                                | 10 | 73.87 | 73.08 | -0.79  | 9.09 M (45.24%)  | 1.440s  | N/A     |   2x  |
 Random\*    | N/A                                | 11 | 73.87 | 72.75 | -1.12  | 9.98 M (49.70%)  | 0.172s  | N/A     |   2x  |
 OBD-Hessian\*   | N/A                                | 12 | 73.87 | 71.79 | -2.08  | 8.23 M (40.96%)  | 1m15s   | N/A     |   2x  |
 BNScale              | BNScale     | 1  | 73.87 | 74.27 | +0.40  | 6.80 M (33.84%)  | 0.062s  | 37.060s |   2x  |
 MagnitudeL2            | GroupNorm  | 2  | 73.87 | 74.12 | +0.25  | 6.08  M (30.26%) | 0.199s  | 1m31s   |   2x  |
 MagnitudeL2            | GrowingReg   | 3  | 73.87 | 73.86 | -0.01  | 7.07 M (35.18%)  | 0.199s  | 1m24s   |   2x  |
 MagnitudeL2            | GroupLASSO | 4  | 73.87 | 73.42 | -0.45  | 7.09 M (35.29%)  | 0.199s  | 1m28s   |   2x  |
 BNScale              | GroupLASSO | 5  | 73.87 | 73.14 | -0.73  | 7.09 M (35.29%)  | 0.062s  | 58.990s |   2x  |
 FPGM                   | N/A                                | 1  | 73.87 | 72.38 | -1.49  | 3.11 M (15.49%)  | 0.346s  | N/A     |   4x  |
 LAMP                    | N/A                                | 2  | 73.87 | 72.30 | -1.57  | 1.91 M (9.49%)   | 0.063s  | N/A     |   4x  |
 MagnitudeL2            | N/A                                | 3  | 73.87 | 71.95 | -1.92  | 2.74 M (13.66%)  | 0.199s  | N/A     |   4x  |
 MagnitudeL1            | N/A                                | 4  | 73.87 | 71.89 | -1.98  | 2.64 M (13.12%)  | 0.156s  | N/A     |   4x  |
 OBD-C\*      | N/A                                | 5  | 73.87 | 71.67 | -2.20  | 2.83  M (14.07%) | 5.813s  | N/A     |   4x  |
 HRank\*            | N/A                                | 6  | 73.87 | 71.61 | -2.26  | 1.47 M (7.34%)   | 13m59s  | N/A     |   4x  |
 Taylor | N/A                                | 7  | 73.87 | 71.37 | -2.50  | 3.76 M (18.73%)  | 1.440s  | N/A     |   4x  |
 BNScale              | N/A                                | 8  | 73.87 | 71.33 | -2.54  | 3.04 M (15.16%)  | 0.062s  | N/A     |   4x  |
 ThiNet\*           | N/A                                | 9  | 73.87 | 71.17 | -2.70  | 3.95 M (19.65%)  | 13.528s | N/A     |   4x  |
 CP\*              | N/A                                | 10 | 73.87 | 70.85 | -3.02  | 1.45 M (7.21%)   | 1m2s    | N/A     |   4x  |
 Random\*    | N/A                                | 11 | 73.87 | 70.51 | -3.36  | 4.82 M (23.99%)  | 0.172s  | N/A     |   4x  |
 OBD-Hessian\*   | N/A                                | 12 | 73.87 | 69.12 | -4.75  | 3.82 M (19.04%)  | 1m15s   | N/A     |   4x  |
 BNScale              | BNScale     | 1  | 73.87 | 72.34 | -1.53  | 2.67  M (13.30%) | 0.062s  | 37.060s |   4x  |
 BNScale              | GroupLASSO | 2  | 73.87 | 72.25 | -1.62  | 2.64 M (13.14%)  | 0.062s  | 58.990s |   4x  |
 MagnitudeL2            | GrowingReg   | 3  | 73.87 | 71.84 | -2.03  | 2.58  M (12.86%) | 0.199s  | 1m24s   |   4x  |
 MagnitudeL2            | GroupLASSO | 4  | 73.87 | 71.68 | -2.19  | 2.59 M (12.90%)  | 0.199s  | 1m28s   |   4x  |
 MagnitudeL2            | GroupNorm  | 5  | 73.87 | 68.59 | -5.28  | 3.31 M (16.49%)  | 0.199s  | 1m31s   |   4x  |
 LAMP                    | N/A                                | 1  | 73.87 | 69.72 | -4.15  | 0.84 M (4.17%)   | 0.063s  | N/A     |   8x  |
 MagnitudeL1            | N/A                                | 2  | 73.87 | 68.82 | -5.05  | 1.49 M (7.41%)   | 0.156s  | N/A     |   8x  |
 OBD-C\*      | N/A                                | 3  | 73.87 | 67.88 | -5.99  | 1.51 M (7.50%)   | 5.813s  | N/A     |   8x  |
 Taylor | N/A                                | 4  | 73.87 | 67.35 | -6.52  | 2.00 M (9.96%)   | 1.440s  | N/A     |   8x  |
 HRank\*            | N/A                                | 5  | 73.87 | 67.01 | -6.86  | 0.63 M (3.15%)   | 13m59s  | N/A     |   8x  |
 ThiNet\*           | N/A                                | 6  | 73.87 | 66.40 | -7.47  | 1.75 M (8.70%)   | 13.528s | N/A     |   8x  |
 BNScale              | N/A                                | 7  | 73.87 | 66.08 | -7.79  | 1.54 M (7.65%)   | 0.062s  | N/A     |   8x  |
 Random\*    | N/A                                | 8  | 73.87 | 65.69 | -8.18  | 2.48 M (12.37%)  | 0.172s  | N/A     |   8x  |
 MagnitudeL2            | N/A                                | 9  | 73.87 | 64.96 | -8.91  | 1.57 M (7.83%)   | 0.199s  | N/A     |   8x  |
 FPGM                   | N/A                                | 10 | 73.87 | 63.97 | -9.90  | 1.78  M (8.87%)  | 0.346s  | N/A     |   8x  |
 CP\*              | N/A                                | 11 | 73.87 | 63.55 | -10.32 | 0.67 M (3.34%)   | 1m2s    | N/A     |   8x  |
 OBD-Hessian\*   | N/A                                | 12 | 73.87 | 63.53 | -10.34 | 1.94 M (9.64%)   | 1m15s   | N/A     |   8x  |
 BNScale              | BNScale     | 1  | 73.87 | 68.57 | -5.30  | 1.33 M (6.62%)   | 0.062s  | 37.060s |   8x  |
 BNScale              | GroupLASSO | 2  | 73.87 | 68.55 | -5.32  | 1.33 M (6.60%)   | 0.062s  | 58.990s |   8x  |
 MagnitudeL2            | GroupNorm  | 3  | 73.87 | 67.29 | -6.58  | 2.06 M (10.24%)  | 0.199s  | 1m31s   |   8x  |
 MagnitudeL2            | GrowingReg   | 4  | 73.87 | 63.91 | -9.96  | 1.23  M (6.15%)  | 0.199s  | 1m24s   |   8x  |
 MagnitudeL2            | GroupLASSO | 5  | 73.87 | 63.44 | -10.43 | 1.23 M (6.13%)   | 0.199s  | 1m28s   |   8x  |


YOLO

| **Importance** | **Regularizer** | **Rank** | **Base** | **Pruned** | **Δ Acc** | **Pruning Ratio** | **Step Time** | **Reg Time** | **Speed Up**|
|----------------|------------------|----------|----------|------------|----------|-------------------|---------------|--------------| --------------|  
 ThiNet\*           | N/A                                | 1  | 49.993 | 44.637 | -5.356  | 8.74 M (33.72%)  | 8m43s   | N/A      |   2x  |
 LAMP                    | N/A                                | 2  | 49.993 | 44.464 | -5.529  | 6.81 M (26.27%)  | 3.216s  | N/A      |   2x  |
 MagnitudeL2            | N/A                                | 3  | 49.993 | 44.380 | -5.613  | 15.08 M (58.24%) | 2.606s  | N/A      |   2x  |
 OBD-Hessian\*   | N/A                                | 4  | 49.993 | 44.327 | -5.666  | 8.62 M (33.28%)  | 15.442s | N/A      |   2x  |
 BNScale                                     | N/A                                | 5  | 49.993 | 44.160 | -5.833  | 12.98 M (50.11%) | 2.992s  | N/A      |   2x  |
 MagnitudeL1            | N/A                                | 6  | 49.993 | 44.004 | -5.989  | 12.98 M (50.11%) | 2.884s  | N/A      |   2x  |
 Taylor | N/A                                | 7  | 49.993 | 43.398 | -6.595  | 11.48 M (44.32%) | 13.485s | N/A      |   2x  |
 FPGM                   | N/A                                | 8  | 49.993 | 43.167 | -6.826  | 11.88 M (45.87%) | 2.145s  | N/A      |   2x  |
 HRank\*            | N/A                                | 9  | 49.993 | 42.976 | -7.017  | 6.04 M (23.32%)  | 13m24s  | N/A      |   2x  |
 Random\*    | N/A                                | 10 | 49.993 | 42.804 | -7.189  | 12.21 M (47.15%) | 0.666s  | N/A      |   2x  |
 CP\*              | N/A                                | 11 | 49.993 | 42.407 | -7.586  | 7.72 M (29.80%)  | 1m7s    | N/A      |   2x  |
 BNScale              | BNScale     | 1  | 49.993 | 44.781 | -5.212  | 12.16 M (46.94%) | 2.992s  | 1h24m44s |   2x  |
 MagnitudeL2            | GroupLASSO | 2  | 49.993 | 44.753 | -5.24   | 14.68 M (56.69%) | 2.606s  | 2h5m45s  |   2x  |
 BNScale              | GroupLASSO | 3  | 49.993 | 44.541 | -5.452  | 12.41 M (47.91%) | 2.992s  | 1h41m36s |   2x  |
 MagnitudeL2            | GrowingReg   | 4  | 49.993 | 44.440 | -5.553  | 14.71 M (56.78%) | 2.606s  | 1h59m27s |   2x  |
 MagnitudeL2            | GroupNorm  | 5  | 49.993 | 44.290 | -5.703  | 14.70 M (56.75%) | 2.606s  | 2h3m45s  |   2x  |
 MagnitudeL2            | N/A                                | 1  | 49.993 | 40.644 | -9.349  | 9.91 M (38.24%)  | 2.606s  | N/A      |   4x  |
 LAMP                    | N/A                                | 2  | 49.993 | 40.112 | -9.881  | 4.03 M (15.55%)  | 3.216s  | N/A      |   4x  |
 BNScale              | N/A                                | 3  | 49.993 | 39.349 | -10.664 | 8.63 M (33.30%)  | 2.992s  | N/A      |   4x  |
 ThiNet\*           | N/A                                | 4  | 49.993 | 39.319 | -10.674 | 8.23 M (31.77%)  | 8m43s   | N/A      |   4x  |
 MagnitudeL1            | N/A                                | 5  | 49.993 | 39.257 | -10.736 | 8.63 M (33.30%)  | 2.884s  | N/A      |   4x  |
 Taylor | N/A                                | 6  | 49.993 | 39.237 | -10.756 | 6.65 M (25.68%)  | 13.485s | N/A      |   4x  |
 HRank\*            | N/A                                | 7  | 49.993 | 38.955 | -11.038 | 4.02 M (15.50%)  | 13m24s  | N/A      |   4x  |
 OBD-Hessian\*   | N/A                                | 8  | 49.993 | 38.901 | -11.192 | 5.48 M (21.17%)  | 15.442s | N/A      |   4x  |
 CP\*              | N/A                                | 9  | 49.993 | 38.509 | -11.484 | 5.85 M (22.60%)  | 1m7s    | N/A      |   4x  |
 Random\*    | N/A                                | 10 | 49.993 | 37.868 | -12.125 | 7.83 M (30.23%)  | 0.666s  | N/A      |   4x  |
 FPGM                   | N/A                                | 11 | 49.993 | 37.523 | -12.470 | 5.07 M (19.57%)  | 2.145s  | N/A      |   4x  |
 MagnitudeL2            | GroupNorm  | 1  | 49.993 | 40.853 | -9.140  | 9.56 M (36.91%)  | 2.606s  | 2h3m45s  |   4x  |
 MagnitudeL2            | GrowingReg   | 2  | 49.993 | 40.735 | -9.258  | 9.65 M (37.25%)  | 2.606s  | 1h59m27s |   4x  |
 MagnitudeL2            | GroupLASSO | 3  | 49.993 | 40.526 | -9.467  | 9.58 M (36.98%)  | 2.606s  | 2h5m45s  |   4x  |
 BNScale              | BNScale     | 4  | 49.993 | 40.101 | -9.892  | 8.23 M (31.77%)  | 2.992s  | 1h24m44s |   4x  |
 BNScale              | GroupLASSO | 5  | 49.993 | 39.635 | -10.358 | 8.46 M (32.65%)  | 2.992s  | 1h41m36s |   4x  |
 MagnitudeL1            | N/A                                | 1  | 49.993 | 38.575 | -11.418 | 6.36 M (24.57%)  | 2.884s  | N/A      |   8x  |
 MagnitudeL2            | N/A                                | 2  | 49.993 | 38.361 | -11.632 | 5.52 M (21.30%)  | 2.606s  | N/A      |   8x  |
 BNScale              | N/A                                | 3  | 49.993 | 38.132 | -11.861 | 6.36 M (24.57%)  | 2.992s  | N/A      |   8x  |
 LAMP                    | N/A                                | 4  | 49.993 | 37.951 | -12.042 | 2.90 M (11.20%)  | 3.216s  | N/A      |   8x  |
 ThiNet\*           | N/A                                | 5  | 49.993 | 37.418 | -12.575 | 5.60 M (21.61%)  | 8m43s                                       | N/A                                |   8x  |
 OBD-Hessian\*   | N/A                                | 6  | 49.993 | 36.721 | -13.272 | 3.95 M (15.23%)  | 15.442s | N/A      |   8x  |
 CP\*              | N/A                                | 7  | 49.993 | 35.408 | -14.585 | 4.86 M (18.76%)  | 1m7s    | N/A      |   8x  |
 Taylor | N/A                                | 8  | 49.993 | 34.749 | -15.244 | 4.60 M (17.76%)  | 13.485s | N/A      |   8x  |
 HRank\*            | N/A                                | 9  | 49.993 | 34.265 | -15.728 | 2.59 M (10.01%)  | 13m24s  | N/A      |   8x  |
 FPGM                   | N/A                                | 10 | 49.993 | 33.997 | -15.996 | 3.20 M (12.33%)  | 2.145s  | N/A      |   8x  |
 Random\*    | N/A                                | 11 | 49.993 | 33.205 | -16.788 | 5.63 M (21.72%)  | 0.666s  | N/A      |   8x  |
 MagnitudeL2            | GroupNorm  | 1  | 49.993 | 38.669 | -11.324 | 6.28 M (25.25%)  | 2.606s  | 2h3m45s  |   8x  |
 MagnitudeL2            | GroupLASSO | 2  | 49.993 | 38.705 | -11.288 | 6.57 M (25.38%)  | 2.606s  | 2h5m45s  |   8x  |
 MagnitudeL2            | GrowingReg   | 3  | 49.993 | 38.505 | -11.488 | 6.60 M (25.48%)  | 2.606s  | 1h59m27s |   8x  |
 BNScale              | GroupLASSO | 4  | 49.993 | 38.499 | -11.494 | 5.66 M (21.85%)  | 2.992s  | 1h41m36s |   8x  |
 BNScale              | BNScale     | 5  | 49.993 | 38.375 | -11.618 | 5.98 M (23.09%)  | 2.992s  | 1h24m44s |   8x  |




Resnet-18_Imagenet

| **Importance** | **Regularizer** | **Rank** | **Base** | **Pruned** | **Δ Acc** | **Pruning Ratio** | **Step Time** | **Reg Time** | **Speed Up**|
|----------------|------------------|----------|----------|------------|----------|-------------------|---------------|--------------| --------------| 
 MagnitudeL2            | N/A                                | 1  | 69.758 | 67.724 | -2.034  | 10.52 M (90.01%)  | 0.038s  | N/A      |   2x  |
 MagnitudeL1            | N/A                                | 2  | 69.758 | 67.652 | -2.106  | 10.22 M (87.41%)  | 0.023s  | N/A      |   2x  |
 FPGM                   | N/A                                | 3  | 69.758 | 67.642 | -2.116  | 9.54 M (81.59%)   | 0.029s  | N/A      |   2x  |
 BNScale              | N/A                                | 4  | 69.758 | 67.542 | -2.216  | 8.31 M (71.07%)   | 0.026s  | N/A      |   2x  |
 OBD-C\*      | N/A                                | 5  | 69.758 | 67.319 | -2.439  | 3.95 M (33.79%)   | 24.096s | N/A      |   2x  |
 Taylor | N/A                                | 6  | 69.758 | 67.220 | -2.538  | 4.59 M (39.26%)   | 22.487S | N/A      |   2x  |
 ThiNet\*           | N/A                                | 7  | 69.758 | 67.211 | -2.547  | 2.81 M (24.05%)   | 15.645s | N/A      |   2x  |
 CP\*              | N/A                                | 8  | 69.758 | 67.139 | -2.619  | 1.89 M (16.19%)   | 2m21s   | N/A      |   2x  |
 OBD-Hessian\*   | N/A                                | 9  | 69.758 | 66.934 | -2.824  | 1.49 M (12.76%)   | 1m45s   | N/A      |   2x  |
 Random\*    | N/A                                | 10 | 69.758 | 64.788 | -4.970  | 5.44 M (46.57%)   | 0.020s  | N/A      |   2x  |
 HRank\*            | N/A                                | 11 | 69.758 | 63.834 | -5.924  | 3.20  M (27.40%)  | 49m53s  | N/A      |   2x  |
 LAMP                    | N/A                                | 12 | 69.758 | 58.308 | -11.45  | 1.56 M (13.37%)   | 0.030s  | N/A      |   2x  |
 MagnitudeL2            | GroupLASSO | 1  | 69.758 | 67.765 | -1.993  | 10.31 M (88.20%)  | 0.038s  | 3h10m44s |   2x  |
 BNScale              | BNScale     | 2  | 69.758 | 67.734 | -2.024  | 17.56 M (68.70%)  | 0.026s  | 1h54m9s  |   2x  |
 BNScale              | GroupLASSO | 3  | 69.758 | 67.376 | -2.382  | 10.47  M (89.57%) | 0.026s  | 2h41m15s |   2x  |
 MagnitudeL2            | GroupNorm  | 4  | 69.758 | 67.210 | -2.548  | 8.68 M (74.21%)   | 0.038s  | 3h4m27s  |   2x  |
 MagnitudeL2            | GrowingReg   | 5  | 69.758 | 67.112 | -2.646  | 10.66 M (24.71%)  | 0.038s  | 3h12m21s |   2x  |
 BNScale              | N/A                                | 1  | 69.758 | 63.684 | -6.074  | 6.97 M (59.59%)   | 0.026s  | N/A      |   4x  |
 OBD-C\*      | N/A                                | 2  | 69.758 | 63.312 | -6.446  | 1.50 M (12.87%)   | 24.096s | N/A      |   4x  |
 ThiNet\*           | N/A                                | 3  | 69.758 | 63.297 | -6.461  | 0.99 M (8.49%)    | 15.645s | N/A      |   4x  |
 MagnitudeL1            | N/A                                | 4  | 69.758 | 63.284 | -6.474  | 9.20  M (78.66%)  | 0.023s  | N/A      |   4x  |
 MagnitudeL2            | N/A                                | 5  | 69.758 | 62.936 | -6.822  | 9.32 M (79.69%)   | 0.038s  | N/A      |   4x  |
 CP\*              | N/A                                | 6  | 69.758 | 62.902 | -6.856  | 0.58 M (4.97%)    | 2m21s   | N/A      |   4x  |
 FPGM                   | N/A                                | 7  | 69.758 | 62.881 | -6.877  | 8.09 M (69.18%)   | 0.029s  | N/A      |   4x  |
 Taylor | N/A                                | 8  | 69.758 | 62.877 | -6.881  | 1.85 M (15.79%)   | 22.487S | N/A      |   4x  |
 OBD-Hessian\*   | N/A                                | 9  | 69.758 | 61.022 | -8.736  | 0.73 M (6.26%)    | 1m45s   | N/A      |   4x  |
 Random\*    | N/A                                | 10 | 69.758 | 57.102 | -12.656 | 3.40 M (29.10%)   | 0.020s  | N/A      |   4x  |
 HRank\*            | N/A                                | 11 | 69.758 | 56.901 | -12.857 | 1.77 M (15.14%)   | 49m53s  | N/A      |   4x  |
 LAMP                    | N/A                                | 12 | 69.758 | 54.368 | -15.390 | 1.05 M (8.95%)    | 0.030s  | N/A      |   4x  |
 BNScale              | GroupLASSO | 1  | 69.758 | 63.729 | -6.029  | 6.77 M (57.91%)   | 0.026s  | 2h41m15s |   4x  |
 BNScale              | BNScale     | 2  | 69.758 | 63.671 | -6.087  | 6.98 M (59.71%)   | 0.026s  | 1h54m9s  |   4x  |
 MagnitudeL2            | GroupNorm  | 3  | 69.758 | 63.117 | -6.641  | 8.17 M (69.89%)   | 0.038s  | 3h4m27s  |   4x  |
 MagnitudeL2            | GrowingReg   | 4  | 69.758 | 63.042 | -6.716  | 9.04 M (77.33%)   | 0.038s  | 3h12m21s |   4x  |
 MagnitudeL2            | GroupLASSO | 5  | 69.758 | 62.814 | -6.944  | 9.27 M (83.54%)   | 0.038s  | 3h10m44s |   4x  |
 BNScale              | N/A                                | 1  | 69.758 | 61.212 | -8.546  | 5.73 M (49.06%)   | 0.026s  | N/A      |   8x  |
 MagnitudeL1            | N/A                                | 2  | 69.758 | 60.760 | -8.998  | 8.14 M (69.65%)   | 0.023s  | N/A      |   8x  |
 Taylor | N/A                                | 3  | 69.758 | 60.502 | -9.256  | 0.97 M (8.27%)    | 22.487S | N/A      |   8x  |
 MagnitudeL2            | N/A                                | 4  | 69.758 | 60.438 | -9.320  | 8.25 M (70.54%)   | 0.038s  | N/A      |   8x  |
 OBD-C\*      | N/A                                | 5  | 69.758 | 60.431 | -9.327  | 1.16 M (9.96%)    | 24.096s | N/A      |   8x  |
 ThiNet\*           | N/A                                | 6  | 69.758 | 60.279 | -9.479  | 0.61 M (5.26%)    | 15.645s | N/A      |   8x  |
 CP\*              | N/A                                | 7  | 69.758 | 60.110 | -9.648  | 0.40  M (3.45%)   | 2m21s   | N/A      |   8x  |
 FPGM                   | N/A                                | 8  | 69.758 | 59.539 | -10.219 | 6.79 M (58.12%)   | 0.029s  | N/A      |   8x  |
 OBD-Hessian\*   | N/A                                | 9  | 69.758 | 55.478 | -14.280 | 0.59 M (5.02%)    | 1m45s   | N/A      |   8x  |
 HRank\*            | N/A                                | 10 | 69.758 | 51.703 | -18.055 | 0.99  M (8.48%)   | 49m53s  | N/A      |   8x  |
 LAMP                    | N/A                                | 11 | 69.758 | 51.348 | -18.410 | 0.79 M (6.77%)    | 0.030s  | N/A      |   8x  |
 Random\*    | N/A                                | 12 | 69.758 | 49.994 | -19.764 | 2.73 M (23.38%)   | 0.020s  | N/A      |   8x  |
 MagnitudeL2            | GroupNorm  | 1  | 69.758 | 61.106 | -8.652  | 7.77 M (66.47%)   | 0.038s  | 3h4m27s  |   8x  |
 MagnitudeL2            | GroupLASSO | 2  | 69.758 | 60.771 | -8.987  | 8.12 M (69.46%)   | 0.038s  | 3h10m44s |   8x  |
 BNScale              | GroupLASSO | 3  | 69.758 | 60.221 | -9.537  | 5.41 M (46.28%)   | 0.026s  | 2h41m15s |   8x  |
 MagnitudeL2            | GrowingReg   | 4  | 69.758 | 60.127 | -9.631  | 8.31 M (71.09%)   | 0.038s  | 3h12m21s |   8x  |
 BNScale              | BNScale     | 5  | 69.758 | 60.043 | -9.715  | 5.32 M (45.51%)   | 0.026s  | 1h54m9s  |   8x  |




Resnet-50__Imagenet


| **Importance** | **Regularizer** | **Rank** | **Base** | **Pruned** | **Δ Acc** | **Pruning Ratio** | **Step Time** | **Reg Time** | **Speed Up**|
|----------------|------------------|----------|----------|------------|----------|-------------------|---------------|--------------| --------------| 
 FPGM                   | N/A                                | 1  | 76.128 | 75.406 | -0.722  | 14.84 M (58.08%)  | 0.538s  | N/A      |   2x  |
 OBD-C\*      | N/A                                | 2  | 76.128 | 74.361 | -1.767  | 12.94 M (50.65%)  | 25.448s | N/A      |   2x  |
 MagnitudeL1            | N/A                                | 3  | 76.128 | 74.118 | -2.01   | 18.17 M (71.09%)  | 0.183s  | N/A      |   2x  |
 MagnitudeL2            | N/A                                | 4  | 76.128 | 73.684 | -2.444  | 18.26 M (71.44%)  | 0.081s  | N/A      |   2x  |
 ThiNet\*           | N/A                                | 5  | 76.128 | 72.969 | -3.159  | 9.44 M (36.96%)   | 43.444s | N/A      |   2x  |
 Taylor | N/A                                | 6  | 76.128 | 72.101 | -4.027  | 13.26 M (51.87%)  | 25.590s | N/A      |   2x  |
 OBD-Hessian\*   | N/A                                | 7  | 76.128 | 71.664 | -4.464  | 6.59  M (25.78%)  | 6m9s    | N/A      |   2x  |
 BNScale              | N/A                                | 8  | 76.128 | 71.812 | -4.316  | 17.29 M (67.66%)  | 0.118s  | N/A      |   2x  |
 CP\*              | N/A                                | 9  | 76.128 | 71.410 | -4.718  | 4.75 M (18.57%)   | 6m43s   | N/A      |   2x  |
 Random\*    | N/A                                | 10 | 76.128 | 71.399 | -4.729  | 12.86 M (50.30%)  | 0.091s  | N/A      |   2x  |
 LAMP                    | N/A                                | 11 | 76.128 | 71.248 | -4.88   | 5.98 M (23.40%)   | 0.103s  | N/A      |   2x  |
 HRank\*            | N/A                                | 12 | 76.128 | 69.865 | -6.263  | 9.53 M (37.27%)   | 1h7m20s | N/A      |   2x  |
 MagnitudeL2            | GroupLASSO | 1  | 76.128 | 73.661 | -2.467  | 17.68 M (69.16%)  | 0.081s  | 3h45m17s |   2x  |
 BNScale              | BNScale     | 2  | 76.128 | 73.343 | -2.785  | 17.68 M (69.17%)  | 0.118s  | 2h41m56s |   2x  |
 MagnitudeL2            | GroupNorm  | 3  | 76.128 | 73.297 | -2.831  | 11.51 M (45.02%)  | 0.081s  | 3h43m21s |   2x  |
 BNScale              | GroupLASSO | 4  | 76.128 | 73.176 | -2.952  | 17.43 M (68.21%)  | 0.118s  | 3h7m44s  |   2x  |
 MagnitudeL2            | GrowingReg   | 5  | 76.128 | 73.110 | -3.018  | 17.57 M (68.74%)  | 0.081s  | 3h51m10s |   2x  |
 MagnitudeL2            | N/A                                | 1  | 76.128 | 71.804 | -4.324  | 14.37 M (56.23%)  | 0.081s  | N/A      |   4x  |
 MagnitudeL1            | N/A                                | 2  | 76.128 | 71.685 | -4.443  | 14.30 M (55.94%)  | 0.183s  | N/A      |   4x  |
 BNScale              | N/A                                | 3  | 76.128 | 71.453 | -4.675  | 14.30  M (55.94%) | 0.118s  | N/A      |   4x  |
 Taylor | N/A                                | 4  | 76.128 | 71.233 | -4.895  | 6.17 M (24.15%)   | 25.590s | N/A      |   4x  |
 OBD-C\*      | N/A                                | 5  | 76.128 | 71.121 | -5.007  | 7.74 M (30.29%)   | 25.448s | N/A      |   4x  |
 CP\*              | N/A                                | 6  | 76.128 | 71.003 | -5.125  | 1.90 M (7.43%)    | 6m43s   | N/A      |   4x  |
 ThiNet\*           | N/A                                | 7  | 76.128 | 70.994 | -5.134  | 4.77 M (18.68%)   | 43.444s | N/A      |   4x  |
 FPGM                   | N/A                                | 8  | 76.128 | 70.010 | -6.118  | 15.44 M (60.41%)  | 0.538s  | N/A      |   4x  |
 LAMP                    | N/A                                | 9  | 76.128 | 67.056 | -9.072  | 2.79  M (10.92%)  | 0.103s  | N/A      |   4x  |
 OBD-Hessian\*   | N/A                                | 10 | 76.128 | 66.945 | -9.183  | 3.38 M (13.24%)   | 6m9s    | N/A      |   4x  |
 HRank\*            | N/A                                | 11 | 76.128 | 66.134 | -9.994  | 6.65  M (26.02%)  | 1h7m20s | N/A      |   4x  |
 Random\*    | N/A                                | 12 | 76.128 | 65.314 | -10.814 | 8.91 M (34.87%)   | 0.091s  | N/A      |   4x  |
 MagnitudeL2            | GroupLASSO | 1  | 76.128 | 71.811 | -4.317  | 14.01 M (54.81%)  | 0.081s  | 3h45m17s |   4x  |
 MagnitudeL2            | GroupNorm  | 2  | 76.128 | 71.551 | -4.577  | 14.77 M (57.79%)  | 0.081s  | 3h43m21s |   4x  |
 BNScale              | GroupLASSO | 3  | 76.128 | 71.507 | -4.621  | 14.25 M (55.75%)  | 0.118s  | 3h7m44s  |   4x  |
 BNScale              | BNScale     | 4  | 76.128 | 71.399 | -4.729  | 14.81 M (57.94%)  | 0.118s  | 2h41m56s |   4x  |
 MagnitudeL2            | GrowingReg   | 5  | 76.128 | 71.259 | -4.869  | 14.91 M (58.33%)  | 0.081s  | 3h51m10s |   4x  |
 MagnitudeL2            | N/A                                | 1  | 76.128 | 69.866 | -6.262  | 11.88 M (46.49%)  | 0.081s  | N/A      |   8x  |
 MagnitudeL1            | N/A                                | 2  | 76.128 | 69.471 | -6.657  | 11.94 M (46.72%)  | 0.183s  | N/A      |   8x  |
 Taylor | N/A                                | 3  | 76.128 | 69.063 | -7.065  | 3.48 M (13.63%)   | 25.590s | N/A      |   8x  |
 OBD-C\*      | N/A                                | 4  | 76.128 | 69.010 | -7.118  | TBD M (TBD%)      | 25.448s | N/A      |   8x  |
 BNScale              | N/A                                | 5  | 76.128 | 68.851 | -7.277  | 11.94 M (46.72%)  | 0.118s  | N/A      |   8x  |
 ThiNet\*           | N/A                                | 6  | 76.128 | 68.351 | -7.777  | 2.79  M (10.91%)  | 43.444s | N/A      |   8x  |
 CP\*              | N/A                                | 7  | 76.128 | 67.995 | -8.133  | 1.36 M (5.33%)    | 6m43s   | N/A      |   8x  |
 FPGM                   | N/A                                | 8  | 76.128 | 67.106 | -9.022  | 13.37 M (52.33%)  | 0.538s  | N/A      |   8x  |
 OBD-Hessian\*   | N/A                                | 9  | 76.128 | 65.106 | -11.022 | 2.93 M (11.45%)   | 6m9s    | N/A      |   8x  |
 LAMP                    | N/A                                | 10 | 76.128 | 63.102 | -13.026 | 2.77 M (24.71%)   | 0.103s  | N/A      |   8x  |
 HRank\*            | N/A                                | 11 | 76.128 | 62.964 | -13.164 | 4.39 M (17.16%)   | 1h7m20s | N/A      |   8x  |
 Random\*    | N/A                                | 12 | 76.128 | 61.244 | -14.884 | 6.73 M (26.33%)   | 0.091s  | N/A      |   8x  |
 MagnitudeL2            | GroupLASSO | 1  | 76.128 | 69.897 | -6.231  | 12.17 M (47.61%)  | 0.081   | 3h45m17s |   8x  |
 MagnitudeL2            | GroupNorm  | 2  | 76.128 | 69.137 | -6.991  | 12.31 M (48.16%)  | 0.081   | 3h43m21s |   8x  |
 BNScale              | BNScale     | 3  | 76.128 | 68.914 | -7.214  | 11.97 M (46.83%)  | 0.118   | 2h41m56s |   8x  |
 MagnitudeL2            | GrowingReg   | 4  | 76.128 | 68.759 | -7.369  | 11.94 M (46.71%)  | 0.081   | 3h51m10s |   8x  |
 BNScale              | GroupLASSO | 5  | 76.128 | 68.446 | -7.682  | 12.06 M (47.18%)  | 0.118   | 3h7m44s  |   8x  |


<!-- | Method | Base (%) | Pruned (%) | $\Delta$ Acc (%) | Speed Up |
|:--    |:--:  |:--:    |:--: |:--:      |
| NIPS [[1]](#1)  | -    | -      |-0.03 | 1.76x    |
| Geometric [[2]](#2) | 93.59 | 93.26 | -0.33 | 1.70x |
| Polar [[3]](#3)  | 93.80 | 93.83 | +0.03 |1.88x |
| CP  [[4]](#4)   | 92.80 | 91.80 | -1.00 |2.00x |
| AMC [[5]](#5)   | 92.80 | 91.90 | -0.90 |2.00x |
| HRank [[6]](#6) | 93.26 | 92.17 | -0.09 |2.00x |
| SFP  [[7]](#7)  | 93.59 | 93.36 | +0.23 |2.11x |
| ResRep [[8]](#8) | 93.71 | 93.71 | +0.00 |2.12x |
||
| Ours-L1 | 93.53 | 92.93 | -0.60 | 2.12x |
| Ours-BN | 93.53 | 93.29 | -0.24 | 2.12x |
| Ours-Group | 93.53 | 93.77 | +0.38 | 2.13x | -->


## Citation
<!-- ```
@inproceedings{fang2023depgraph,
  title={Depgraph: Towards any structural pruning},
  author={Fang, Gongfan and Ma, Xinyin and Song, Mingli and Mi, Michael Bi and Wang, Xinchao},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={16091--16101},
  year={2023}
}
``` -->


| ID                                                                                                                            | Paper | Method    | Conference | Code
|:-------------------------------------------------------------------------------------------------------------------------------- |:-----:|:-------:|:----:|:----:|
| 1 | [Depgraph: Towards any structural pruning](https://openaccess.thecvf.com/content/CVPR2023/papers/Fang_DepGraph_Towards_Any_Structural_Pruning_CVPR_2023_paper.pdf)      | OBD-Hessian    | CVPR 2023     | [PyTorch(Author)](https://github.com/VainF/Torch-Pruning)           |
| 1 | [Depgraph: Towards any structural pruning](https://openaccess.thecvf.com/content/CVPR2023/papers/Fang_DepGraph_Towards_Any_Structural_Pruning_CVPR_2023_paper.pdf)      | GroupNorm    | CVPR 2023     | [PyTorch(Author)](https://github.com/VainF/Torch-Pruning)           |
| 2 | [Layer-adaptive Sparsity for the Magnitude-based Pruning](https://openreview.net/forum?id=H6ATjJ0TKdf)      | LAMP    | ICLR 2021     | [PyTorch(Author)](https://github.com/jaeho-lee/layer-adaptive-sparsity)           |
| 3 | [Neural Pruning via Growing Regularization](https://openreview.net/forum?id=o966_Is_nPA)                                                                                                                                                                               | GrowingReg    | ICLR 2020    | [PyTorch(Author)](https://github.com/MingSun-Tse/Regularization-Pruning)                           |
| 4 | [HRank: Filter Pruning using High-Rank Feature Map](https://arxiv.org/abs/2002.10179)    | HRank     | CVPR 2020 **(Oral)**    | [Pytorch(Author)](https://github.com/lmbxmu/HRank)  
| 5  | [Filter Pruning via Geometric Median for Deep Convolutional Neural Networks Acceleration](https://arxiv.org/abs/1811.00250)                                                                                      | FPGM   |  CVPR 2019 **(Oral)**   | [PyTorch(Author)](https://github.com/he-y/filter-pruning-geometric-median)            |
| 6 | [Importance Estimation for Neural Network Pruning](http://jankautz.com/publications/Importance4NNPruning_CVPR19.pdf)  | Taylor          | CVPR 2019   | [PyTorch(Author)](https://github.com/NVlabs/Taylor_pruning)   
| 7 | [EigenDamage: Structured Pruning in the Kronecker-Factored Eigenbasis](https://arxiv.org/abs/1905.05934)                                                                                                         |  OBD-C        | ICML 2019     | [PyTorch(Author)](https://github.com/alecwangcq/EigenDamage-Pytorch)                  |
| 8 | [Recovering from random pruning: On the plasticity of deep convolutional neural networks](https://ieeexplore.ieee.org/abstract/document/8354202)     |  Random        | WACV 2018     | [PyTorch(Author)](https://github.com/shwetabhardwaj44/RecoveringFrom_RandomPruning_WACV2018)                  |
| 9 | [ThiNet: A Filter Level Pruning Method for Deep Neural Network Compression](https://arxiv.org/abs/1707.06342)                                            |  ThiNet   | ICCV 2017  | [Caffe(Author)](https://github.com/Roll920/ThiNet) |
| 10 | [Channel pruning for accelerating very deep neural networks](https://arxiv.org/abs/1707.06168)                                                           | CP  | ICCV 2017 | [Caffe(Author)](https://github.com/yihui-he/channel-pruning)  
| 11 | [Learning Efficient Convolutional Networks Through Network Slimming](https://arxiv.org/abs/1708.06519)                                                   |  BNScale  | ICCV 2017  | [PyTorch(Author)](https://github.com/Eric-mingjie/network-slimming)                                                         |
| 12 | [Pruning Filters for Efficient ConvNets](https://arxiv.org/abs/1608.08710)                                                                               | MagnitudeL1(MagnitudeL2)   | ICLR 2017  | [PyTorch(Unofficial)](https://github.com/Eric-mingjie/rethinking-network-pruning/tree/master/imagenet/l1-norm-pruning)       |
| 13 | [A note on the group lasso and a sparse group lasso](https://arxiv.org/pdf/1001.0736)                                                                               | MagnitudeL1(MagnitudeL2)   | arXiv 2010  | -       |


