# Codes
Code done throughout my career
# R Codes of ML models 
# . Association Rules	
		                
# Assignment 1

 # BP:  Prepare rules for the all the data sets 
 #   1) Try different values of support and confidence. Observe the change in number of rules for different support,confidence values
 #  2) Change the minimum length in apriori algorithm
 #   3) Visulize the obtained rules using different plots
  # PROCEDURE:

  # STEP 1: First we have to Exploratory Data Analysis which can be done by plotting scattered plot, box plots and summary.

    ## summary(book_1_)
    ChildBks        YouthBks         CookBks         DoItYBks         RefBks      
 Min.   :0.000   Min.   :0.0000   Min.   :0.000   Min.   :0.000   Min.   :0.0000  
 1st Qu.:0.000   1st Qu.:0.0000   1st Qu.:0.000   1st Qu.:0.000   1st Qu.:0.0000  
 Median :0.000   Median :0.0000   Median :0.000   Median :0.000   Median :0.0000  
 Mean   :0.423   Mean   :0.2475   Mean   :0.431   Mean   :0.282   Mean   :0.2145  
 3rd Qu.:1.000   3rd Qu.:0.0000   3rd Qu.:1.000   3rd Qu.:1.000   3rd Qu.:0.0000  
 Max.   :1.000   Max.   :1.0000   Max.   :1.000   Max.   :1.000   Max.   :1.0000  
     ArtBks         GeogBks         ItalCook        ItalAtlas        ItalArt      
 Min.   :0.000   Min.   :0.000   Min.   :0.0000   Min.   :0.000   Min.   :0.0000  
 1st Qu.:0.000   1st Qu.:0.000   1st Qu.:0.0000   1st Qu.:0.000   1st Qu.:0.0000  
 Median :0.000   Median :0.000   Median :0.0000   Median :0.000   Median :0.0000  
 Mean   :0.241   Mean   :0.276   Mean   :0.1135   Mean   :0.037   Mean   :0.0485  
 3rd Qu.:0.000   3rd Qu.:1.000   3rd Qu.:0.0000   3rd Qu.:0.000   3rd Qu.:0.0000  
 Max.   :1.000   Max.   :1.000   Max.   :1.0000   Max.   :1.000   Max.   :1.0000  
    Florence     
 Min.   :0.0000  
 1st Qu.:0.0000  
 Median :0.0000  
 Mean   :0.1085  
 3rd Qu.:0.0000  
 Max.   :1.0000 


# From the summary we can see that all are lying in the same level , it can my confirmed by using Box Plot .













## Scatter Plot for the Following data frame is:

 
 # Scatter plot is given by :
 







 # STEP 2: Building Rules using Apriori algorithm which is given by :

 ## Rules  <-apriori(as.matrix(book_1_[,1:11]),parameter=list(support=0.002,confidence=0.7)) 
Apriori

##Parameter specification:
 confidence minval smax arem  aval originalSupport maxtime support minlen maxlen
        0.7    0.1    1 none FALSE            TRUE       5    0.02      1     10
 target   ext
  rules FALSE

## Algorithmic control:
 filter tree heap memopt load sort verbose
    0.1 TRUE TRUE  FALSE TRUE    2    TRUE

Absolute minimum support count: 40 

set item appearances ...[0 item(s)] done [0.00s].
set transactions ...[11 item(s), 2000 transaction(s)] done [0.00s].
sorting and recoding items ... [11 item(s)] done [0.00s].
creating transaction tree ... done [0.00s].
checking subsets of size 1 2 3 4 5 6 done [0.00s].
writing ... [299 rule(s)] done [0.00s].
creating S4 object  ... done [0.00s].


inspect(rules)
lhs                   rhs                support confidence       lift count
[1]      {}                 => {Gladiator=1}          0.7  0.7000000  1.0000000     7
[2]      {}                 => {Green Mile=0}         0.8  0.8000000  1.0000000     8
[3]      {}                 => {LOTR2=0}              0.8  0.8000000  1.0000000     8
[4]      {}                 => {Harry Potter1=0}      0.8  0.8000000  1.0000000     8
[5]      {}                 => {LOTR1=0}              0.8  0.8000000  1.0000000     8
[6]      {}                 => {LOTR=0}               0.9  0.9000000  1.0000000     9
[7]      {}                 => {Braveheart=0}         0.9  0.9000000  1.0000000     9
[8]      {}                 => {Harry Potter2=0}      0.9  0.9000000  1.0000000     9
[9]      {Harry Potter2=1}  => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[10]     {V2=Harry Potter2} => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[11]     {Harry Potter2=1}  => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[12]     {V1=Harry Potter1} => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[13]     {Harry Potter2=1}  => {Harry Potter1=1}      0.1  1.0000000  5.0000000     1
[14]     {Harry Potter2=1}  => {Gladiator=0}          0.1  1.0000000  3.3333333     1
[15]     {Harry Potter2=1}  => {Sixth Sense=0}        0.1  1.0000000  2.5000000     1
[16]     {Harry Potter2=1}  => {Patriot=0}            0.1  1.0000000  2.5000000     1
[17]     {Harry Potter2=1}  => {Green Mile=0}         0.1  1.0000000  1.2500000     1
[18]     {Harry Potter2=1}  => {LOTR2=0}              0.1  1.0000000  1.2500000     1
[19]     {Harry Potter2=1}  => {LOTR1=0}              0.1  1.0000000  1.2500000     1
[20]     {Harry Potter2=1}  => {LOTR=0}               0.1  1.0000000  1.1111111     1
[21]     {Harry Potter2=1}  => {Braveheart=0}         0.1  1.0000000  1.1111111     1
[22]     {V2=Harry Potter2} => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[23]     {V1=Harry Potter1} => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[24]     {V2=Harry Potter2} => {Harry Potter1=1}      0.1  1.0000000  5.0000000     1
[25]     {V2=Harry Potter2} => {Gladiator=0}          0.1  1.0000000  3.3333333     1
[26]     {V2=Harry Potter2} => {Sixth Sense=0}        0.1  1.0000000  2.5000000     1
[27]     {V2=Harry Potter2} => {Patriot=0}            0.1  1.0000000  2.5000000     1
[28]     {V2=Harry Potter2} => {Green Mile=0}         0.1  1.0000000  1.2500000     1
[29]     {V2=Harry Potter2} => {LOTR2=0}              0.1  1.0000000  1.2500000     1
[30]     {V2=Harry Potter2} => {LOTR1=0}              0.1  1.0000000  1.2500000     1
[31]     {V2=Harry Potter2} => {LOTR=0}               0.1  1.0000000  1.1111111     1
[32]     {V2=Harry Potter2} => {Braveheart=0}         0.1  1.0000000  1.1111111     1
[33]     {V1=Harry Potter1} => {Harry Potter1=1}      0.1  1.0000000  5.0000000     1
[34]     {V1=Harry Potter1} => {Gladiator=0}          0.1  1.0000000  3.3333333     1
[35]     {V1=Harry Potter1} => {Sixth Sense=0}        0.1  1.0000000  2.5000000     1
[36]     {V1=Harry Potter1} => {Patriot=0}            0.1  1.0000000  2.5000000     1
[37]     {V1=Harry Potter1} => {Green Mile=0}         0.1  1.0000000  1.2500000     1
[38]     {V1=Harry Potter1} => {LOTR2=0}              0.1  1.0000000  1.2500000     1
[39]     {V1=Harry Potter1} => {LOTR1=0}              0.1  1.0000000  1.2500000     1
[40]     {V1=Harry Potter1} => {LOTR=0}               0.1  1.0000000  1.1111111     1
[41]     {V1=Harry Potter1} => {Braveheart=0}         0.1  1.0000000  1.1111111     1
[42]     {V2=LOTR2}         => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[43]     {V1=LOTR1}         => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[44]     {V2=LOTR2}         => {LOTR2=1}              0.1  1.0000000  5.0000000     1
[45]     {V2=LOTR2}         => {LOTR1=1}              0.1  1.0000000  5.0000000     1
[46]     {V2=LOTR2}         => {Gladiator=0}          0.1  1.0000000  3.3333333     1
[47]     {V2=LOTR2}         => {Sixth Sense=0}        0.1  1.0000000  2.5000000     1
[48]     {V2=LOTR2}         => {Patriot=0}            0.1  1.0000000  2.5000000     1
[49]     {V2=LOTR2}         => {Green Mile=0}         0.1  1.0000000  1.2500000     1
[50]     {V2=LOTR2}         => {Harry Potter1=0}      0.1  1.0000000  1.2500000     1
[51]     {V2=LOTR2}         => {LOTR=0}               0.1  1.0000000  1.1111111     1
[52]     {V2=LOTR2}         => {Braveheart=0}         0.1  1.0000000  1.1111111     1
[53]     {V2=LOTR2}         => {Harry Potter2=0}      0.1  1.0000000  1.1111111     1
[54]     {V1=LOTR1}         => {LOTR2=1}              0.1  1.0000000  5.0000000     1
[55]     {V1=LOTR1}         => {LOTR1=1}              0.1  1.0000000  5.0000000     1
[56]     {V1=LOTR1}         => {Gladiator=0}          0.1  1.0000000  3.3333333     1
[57]     {V1=LOTR1}         => {Sixth Sense=0}        0.1  1.0000000  2.5000000     1
[58]     {V1=LOTR1}         => {Patriot=0}            0.1  1.0000000  2.5000000     1
[59]     {V1=LOTR1}         => {Green Mile=0}         0.1  1.0000000  1.2500000     1
[60]     {V1=LOTR1}         => {Harry Potter1=0}      0.1  1.0000000  1.2500000     1
[61]     {V1=LOTR1}         => {LOTR=0}               0.1  1.0000000  1.1111111     1
[62]     {V1=LOTR1}         => {Braveheart=0}         0.1  1.0000000  1.1111111     1
[63]     {V1=LOTR1}         => {Harry Potter2=0}      0.1  1.0000000  1.1111111     1
[64]     {Braveheart=1}     => {V3=Braveheart}        0.1  1.0000000 10.0000000     1
[65]     {V3=Braveheart}    => {Braveheart=1}         0.1  1.0000000 10.0000000     1
[66]     {Braveheart=1}     => {Sixth Sense=0}        0.1  1.0000000  2.5000000     1
[67]     {Braveheart=1}     => {Patriot=1}            0.1  1.0000000  1.6666667     1
[68]     {Braveheart=1}     => {V2=Patriot}           0.1  1.0000000  1.6666667     1
[69]     {Braveheart=1}     => {V1=Gladiator}         0.1  1.0000000  1.6666667     1
[70]     {Braveheart=1}     => {Gladiator=1}          0.1  1.0000000  1.4285714     1
[71]     {Braveheart=1}     => {Green Mile=0}         0.1  1.0000000  1.2500000     1
[72]     {Braveheart=1}     => {LOTR2=0}              0.1  1.0000000  1.2500000     1
[73]     {Braveheart=1}     => {Harry Potter1=0}      0.1  1.0000000  1.2500000     1
[74]     {Braveheart=1}     => {LOTR1=0}              0.1  1.0000000  1.2500000     1
[75]     {Braveheart=1}     => {LOTR=0}               0.1  1.0000000  1.1111111     1
[76]     {Braveheart=1}     => {Harry Potter2=0}      0.1  1.0000000  1.1111111     1
[77]     {V3=Braveheart}    => {Sixth Sense=0}        0.1  1.0000000  2.5000000     1
[78]     {V3=Braveheart}    => {Patriot=1}            0.1  1.0000000  1.6666667     1
[79]     {V3=Braveheart}    => {V2=Patriot}           0.1  1.0000000  1.6666667     1
[80]     {V3=Braveheart}    => {V1=Gladiator}         0.1  1.0000000  1.6666667     1
[81]     {V3=Braveheart}    => {Gladiator=1}          0.1  1.0000000  1.4285714     1
[82]     {V3=Braveheart}    => {Green Mile=0}         0.1  1.0000000  1.2500000     1
[83]     {V3=Braveheart}    => {LOTR2=0}              0.1  1.0000000  1.2500000     1
[84]     {V3=Braveheart}    => {Harry Potter1=0}      0.1  1.0000000  1.2500000     1
[85]     {V3=Braveheart}    => {LOTR1=0}              0.1  1.0000000  1.2500000     1
[86]     {V3=Braveheart}    => {LOTR=0}               0.1  1.0000000  1.1111111     1
[87]     {V3=Braveheart}    => {Harry Potter2=0}      0.1  1.0000000  1.1111111     1
[88]     {V3=Gladiator}     => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[89]     {V2=LOTR}          => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[90]     {V3=Gladiator}     => {LOTR=1}               0.1  1.0000000 10.0000000     1
[91]     {LOTR=1}           => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[92]     {V3=Gladiator}     => {V4=Green Mile}        0.1  1.0000000  5.0000000     1
[93]     {V3=Gladiator}     => {V1=Sixth Sense}       0.1  1.0000000  5.0000000     1
[94]     {V3=Gladiator}     => {Green Mile=1}         0.1  1.0000000  5.0000000     1
[95]     {V3=Gladiator}     => {Patriot=0}            0.1  1.0000000  2.5000000     1
[96]     {V3=Gladiator}     => {Sixth Sense=1}        0.1  1.0000000  1.6666667     1
[97]     {V3=Gladiator}     => {Gladiator=1}          0.1  1.0000000  1.4285714     1
[98]     {V3=Gladiator}     => {LOTR2=0}              0.1  1.0000000  1.2500000     1
[99]     {V3=Gladiator}     => {Harry Potter1=0}      0.1  1.0000000  1.2500000     1
[100]    {V3=Gladiator}     => {LOTR1=0}              0.1  1.0000000  1.2500000     1
[101]    {V3=Gladiator}     => {Braveheart=0}         0.1  1.0000000  1.1111111     1
[102]    {V3=Gladiator}     => {Harry Potter2=0}      0.1  1.0000000  1.1111111     1
[103]    {V2=LOTR}          => {LOTR=1}               0.1  1.0000000 10.0000000     1
[104]    {LOTR=1}           => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[105]    {V2=LOTR}          => {V4=Green Mile}        0.1  1.0000000  5.0000000     1
[106]    {V2=LOTR}          => {V1=Sixth Sense}       0.1  1.0000000  5.0000000     1
[107]    {V2=LOTR}          => {Green Mile=1}         0.1  1.0000000  5.0000000     1
[108]    {V2=LOTR}          => {Patriot=0}            0.1  1.0000000  2.5000000     1
[109]    {V2=LOTR}          => {Sixth Sense=1}        0.1  1.0000000  1.6666667     1
[110]    {V2=LOTR}          => {Gladiator=1}          0.1  1.0000000  1.4285714     1
[111]    {V2=LOTR}          => {LOTR2=0}              0.1  1.0000000  1.2500000     1
[112]    {V2=LOTR}          => {Harry Potter1=0}      0.1  1.0000000  1.2500000     1
[113]    {V2=LOTR}          => {LOTR1=0}              0.1  1.0000000  1.2500000     1
[114]    {V2=LOTR}          => {Braveheart=0}         0.1  1.0000000  1.1111111     1
[115]    {V2=LOTR}          => {Harry Potter2=0}      0.1  1.0000000  1.1111111     1
[116]    {LOTR=1}           => {V4=Green Mile}        0.1  1.0000000  5.0000000     1
[117]    {LOTR=1}           => {V1=Sixth Sense}       0.1  1.0000000  5.0000000     1
[118]    {LOTR=1}           => {Green Mile=1}         0.1  1.0000000  5.0000000     1
[119]    {LOTR=1}           => {Patriot=0}            0.1  1.0000000  2.5000000     1
[120]    {LOTR=1}           => {Sixth Sense=1}        0.1  1.0000000  1.6666667     1
[121]    {LOTR=1}           => {Gladiator=1}          0.1  1.0000000  1.4285714     1
[122]    {LOTR=1}           => {LOTR2=0}              0.1  1.0000000  1.2500000     1
[123]    {LOTR=1}           => {Harry Potter1=0}      0.1  1.0000000  1.2500000     1
[124]    {LOTR=1}           => {LOTR1=0}              0.1  1.0000000  1.2500000     1
[125]    {LOTR=1}           => {Braveheart=0}         0.1  1.0000000  1.1111111     1
[126]    {LOTR=1}           => {Harry Potter2=0}      0.1  1.0000000  1.1111111     1
[127]    {V2=LOTR1}         => {V3=Harry Potter1}     0.1  1.0000000 10.0000000     1
[128]    {V3=Harry Potter1} => {V2=LOTR1}             0.1  1.0000000 10.0000000     1
[129]    {V2=LOTR1}         => {V5=LOTR2}             0.1  1.0000000 10.0000000     1
[130]    {V5=LOTR2}         => {V2=LOTR1}             0.1  1.0000000 10.0000000     1
[131]    {V2=LOTR1}         => {LOTR2=1}              0.1  1.0000000  5.0000000     1
[132]    {V2=LOTR1}         => {LOTR1=1}              0.1  1.0000000  5.0000000     1
[133]    {V2=LOTR1}         => {Harry Potter1=1}      0.1  1.0000000  5.0000000     1
[134]    {V2=LOTR1}         => {V4=Green Mile}        0.1  1.0000000  5.0000000     1
[135]    {V2=LOTR1}         => {V1=Sixth Sense}       0.1  1.0000000  5.0000000     1
[136]    {V2=LOTR1}         => {Green Mile=1}         0.1  1.0000000  5.0000000     1
[137]    {V2=LOTR1}         => {Gladiator=0}          0.1  1.0000000  3.3333333     1
[138]    {V2=LOTR1}         => {Patriot=0}            0.1  1.0000000  2.5000000     1
[139]    {V2=LOTR1}         => {Sixth Sense=1}        0.1  1.0000000  1.6666667     1
[140]    {V2=LOTR1}         => {LOTR=0}               0.1  1.0000000  1.1111111     1
[141]    {V2=LOTR1}         => {Braveheart=0}         0.1  1.0000000  1.1111111     1
[142]    {V2=LOTR1}         => {Harry Potter2=0}      0.1  1.0000000  1.1111111     1
[143]    {V3=Harry Potter1} => {V5=LOTR2}             0.1  1.0000000 10.0000000     1
[144]    {V5=LOTR2}         => {V3=Harry Potter1}     0.1  1.0000000 10.0000000     1
[145]    {V3=Harry Potter1} => {LOTR2=1}              0.1  1.0000000  5.0000000     1
[146]    {V3=Harry Potter1} => {LOTR1=1}              0.1  1.0000000  5.0000000     1
[147]    {V3=Harry Potter1} => {Harry Potter1=1}      0.1  1.0000000  5.0000000     1
[148]    {V3=Harry Potter1} => {V4=Green Mile}        0.1  1.0000000  5.0000000     1
[149]    {V3=Harry Potter1} => {V1=Sixth Sense}       0.1  1.0000000  5.0000000     1
[150]    {V3=Harry Potter1} => {Green Mile=1}         0.1  1.0000000  5.0000000     1
[151]    {V3=Harry Potter1} => {Gladiator=0}          0.1  1.0000000  3.3333333     1
[152]    {V3=Harry Potter1} => {Patriot=0}            0.1  1.0000000  2.5000000     1
[153]    {V3=Harry Potter1} => {Sixth Sense=1}        0.1  1.0000000  1.6666667     1
[154]    {V3=Harry Potter1} => {LOTR=0}               0.1  1.0000000  1.1111111     1
[155]    {V3=Harry Potter1} => {Braveheart=0}         0.1  1.0000000  1.1111111     1
[156]    {V3=Harry Potter1} => {Harry Potter2=0}      0.1  1.0000000  1.1111111     1
[157]    {V5=LOTR2}         => {LOTR2=1}              0.1  1.0000000  5.0000000     1
[158]    {V5=LOTR2}         => {LOTR1=1}              0.1  1.0000000  5.0000000     1
[159]    {V5=LOTR2}         => {Harry Potter1=1}      0.1  1.0000000  5.0000000     1
[160]    {V5=LOTR2}         => {V4=Green Mile}        0.1  1.0000000  5.0000000     1
[161]    {V5=LOTR2}         => {V1=Sixth Sense}       0.1  1.0000000  5.0000000     1
[162]    {V5=LOTR2}         => {Green Mile=1}         0.1  1.0000000  5.0000000     1
[163]    {V5=LOTR2}         => {Gladiator=0}          0.1  1.0000000  3.3333333     1
[164]    {V5=LOTR2}         => {Patriot=0}            0.1  1.0000000  2.5000000     1
[165]    {V5=LOTR2}         => {Sixth Sense=1}        0.1  1.0000000  1.6666667     1
[166]    {V5=LOTR2}         => {LOTR=0}               0.1  1.0000000  1.1111111     1
[167]    {V5=LOTR2}         => {Braveheart=0}         0.1  1.0000000  1.1111111     1
[168]    {V5=LOTR2}         => {Harry Potter2=0}      0.1  1.0000000  1.1111111     1
[169]    {LOTR2=1}          => {LOTR1=1}              0.2  1.0000000  5.0000000     2
[170]    {LOTR1=1}          => {LOTR2=1}              0.2  1.0000000  5.0000000     2
[171]    {LOTR2=1}          => {Gladiator=0}          0.2  1.0000000  3.3333333     2
[172]    {LOTR2=1}          => {Patriot=0}            0.2  1.0000000  2.5000000     2
[173]    {LOTR2=1}          => {LOTR=0}               0.2  1.0000000  1.1111111     2
[174]    {LOTR2=1}          => {Braveheart=0}         0.2  1.0000000  1.1111111     2
[175]    {LOTR2=1}          => {Harry Potter2=0}      0.2  1.0000000  1.1111111     2
[176]    {LOTR1=1}          => {Gladiator=0}          0.2  1.0000000  3.3333333     2
[177]    {LOTR1=1}          => {Patriot=0}            0.2  1.0000000  2.5000000     2
[178]    {LOTR1=1}          => {LOTR=0}               0.2  1.0000000  1.1111111     2
[179]    {LOTR1=1}          => {Braveheart=0}         0.2  1.0000000  1.1111111     2
[180]    {LOTR1=1}          => {Harry Potter2=0}      0.2  1.0000000  1.1111111     2
[181]    {Harry Potter1=1}  => {Gladiator=0}          0.2  1.0000000  3.3333333     2
[182]    {Harry Potter1=1}  => {Patriot=0}            0.2  1.0000000  2.5000000     2
[183]    {Harry Potter1=1}  => {LOTR=0}               0.2  1.0000000  1.1111111     2
[184]    {Harry Potter1=1}  => {Braveheart=0}         0.2  1.0000000  1.1111111     2
[185]    {V4=Green Mile}    => {V1=Sixth Sense}       0.2  1.0000000  5.0000000     2
[186]    {V1=Sixth Sense}   => {V4=Green Mile}        0.2  1.0000000  5.0000000     2
[187]    {V4=Green Mile}    => {Green Mile=1}         0.2  1.0000000  5.0000000     2
[188]    {Green Mile=1}     => {V4=Green Mile}        0.2  1.0000000  5.0000000     2
[189]    {V4=Green Mile}    => {Patriot=0}            0.2  1.0000000  2.5000000     2
[190]    {V4=Green Mile}    => {Sixth Sense=1}        0.2  1.0000000  1.6666667     2
[191]    {V4=Green Mile}    => {Braveheart=0}         0.2  1.0000000  1.1111111     2
[192]    {V4=Green Mile}    => {Harry Potter2=0}      0.2  1.0000000  1.1111111     2
[193]    {V1=Sixth Sense}   => {Green Mile=1}         0.2  1.0000000  5.0000000     2
[194]    {Green Mile=1}     => {V1=Sixth Sense}       0.2  1.0000000  5.0000000     2
[195]    {V1=Sixth Sense}   => {Patriot=0}            0.2  1.0000000  2.5000000     2
[196]    {V1=Sixth Sense}   => {Sixth Sense=1}        0.2  1.0000000  1.6666667     2
[197]    {V1=Sixth Sense}   => {Braveheart=0}         0.2  1.0000000  1.1111111     2
[198]    {V1=Sixth Sense}   => {Harry Potter2=0}      0.2  1.0000000  1.1111111     2
[199]    {Green Mile=1}     => {Patriot=0}            0.2  1.0000000  2.5000000     2
[200]    {Green Mile=1}     => {Sixth Sense=1}        0.2  1.0000000  1.6666667     2
[201]    {Green Mile=1}     => {Braveheart=0}         0.2  1.0000000  1.1111111     2
[202]    {Green Mile=1}     => {Harry Potter2=0}      0.2  1.0000000  1.1111111     2
[203]    {Gladiator=0}      => {Patriot=0}            0.3  1.0000000  2.5000000     3
[204]    {Patriot=0}        => {Gladiator=0}          0.3  0.7500000  2.5000000     3
[205]    {Gladiator=0}      => {LOTR=0}               0.3  1.0000000  1.1111111     3
[206]    {Gladiator=0}      => {Braveheart=0}         0.3  1.0000000  1.1111111     3
[207]    {Sixth Sense=0}    => {Green Mile=0}         0.4  1.0000000  1.2500000     4
[208]    {Sixth Sense=0}    => {LOTR2=0}              0.3  0.7500000  0.9375000     3
[209]    {Sixth Sense=0}    => {Harry Potter1=0}      0.3  0.7500000  0.9375000     3
[210]    {Sixth Sense=0}    => {LOTR1=0}              0.3  0.7500000  0.9375000     3
[211]    {Sixth Sense=0}    => {LOTR=0}               0.4  1.0000000  1.1111111     4
[212]    {Sixth Sense=0}    => {Braveheart=0}         0.3  0.7500000  0.8333333     3
[213]    {Sixth Sense=0}    => {Harry Potter2=0}      0.3  0.7500000  0.8333333     3
[214]    {V3=Sixth Sense}   => {Patriot=1}            0.4  1.0000000  1.6666667     4
[215]    {V3=Sixth Sense}   => {V2=Patriot}           0.4  1.0000000  1.6666667     4
[216]    {V3=Sixth Sense}   => {V1=Gladiator}         0.4  1.0000000  1.6666667     4
[217]    {V3=Sixth Sense}   => {Sixth Sense=1}        0.4  1.0000000  1.6666667     4
[218]    {V3=Sixth Sense}   => {Gladiator=1}          0.4  1.0000000  1.4285714     4
[219]    {V3=Sixth Sense}   => {Green Mile=0}         0.4  1.0000000  1.2500000     4
[220]    {V3=Sixth Sense}   => {LOTR2=0}              0.4  1.0000000  1.2500000     4
[221]    {V3=Sixth Sense}   => {Harry Potter1=0}      0.4  1.0000000  1.2500000     4
[222]    {V3=Sixth Sense}   => {LOTR1=0}              0.4  1.0000000  1.2500000     4
[223]    {V3=Sixth Sense}   => {LOTR=0}               0.4  1.0000000  1.1111111     4
[224]    {V3=Sixth Sense}   => {Braveheart=0}         0.4  1.0000000  1.1111111     4
[225]    {V3=Sixth Sense}   => {Harry Potter2=0}      0.4  1.0000000  1.1111111     4
[226]    {Patriot=0}        => {LOTR=0}               0.3  0.7500000  0.8333333     3
[227]    {Patriot=0}        => {Braveheart=0}         0.4  1.0000000  1.1111111     4
[228]    {Patriot=0}        => {Harry Potter2=0}      0.3  0.7500000  0.8333333     3
[229]    {Patriot=1}        => {V2=Patriot}           0.6  1.0000000  1.6666667     6
[230]    {V2=Patriot}       => {Patriot=1}            0.6  1.0000000  1.6666667     6
[231]    {Patriot=1}        => {V1=Gladiator}         0.6  1.0000000  1.6666667     6
[232]    {V1=Gladiator}     => {Patriot=1}            0.6  1.0000000  1.6666667     6
[233]    {Patriot=1}        => {Gladiator=1}          0.6  1.0000000  1.4285714     6
[234]    {Gladiator=1}      => {Patriot=1}            0.6  0.8571429  1.4285714     6
[235]    {Patriot=1}        => {Green Mile=0}         0.6  1.0000000  1.2500000     6
[236]    {Green Mile=0}     => {Patriot=1}            0.6  0.7500000  1.2500000     6
[237]    {Patriot=1}        => {LOTR2=0}              0.6  1.0000000  1.2500000     6
[238]    {LOTR2=0}          => {Patriot=1}            0.6  0.7500000  1.2500000     6
[239]    {Patriot=1}        => {Harry Potter1=0}      0.6  1.0000000  1.2500000     6
[240]    {Harry Potter1=0}  => {Patriot=1}            0.6  0.7500000  1.2500000     6
[241]    {Patriot=1}        => {LOTR1=0}              0.6  1.0000000  1.2500000     6
[242]    {LOTR1=0}          => {Patriot=1}            0.6  0.7500000  1.2500000     6
[243]    {Patriot=1}        => {LOTR=0}               0.6  1.0000000  1.1111111     6
[244]    {Patriot=1}        => {Braveheart=0}         0.5  0.8333333  0.9259259     5
[245]    {Patriot=1}        => {Harry Potter2=0}      0.6  1.0000000  1.1111111     6
[246]    {V2=Patriot}       => {V1=Gladiator}         0.6  1.0000000  1.6666667     6
[247]    {V1=Gladiator}     => {V2=Patriot}           0.6  1.0000000  1.6666667     6
[248]    {V2=Patriot}       => {Gladiator=1}          0.6  1.0000000  1.4285714     6
[249]    {Gladiator=1}      => {V2=Patriot}           0.6  0.8571429  1.4285714     6
[250]    {V2=Patriot}       => {Green Mile=0}         0.6  1.0000000  1.2500000     6
[251]    {Green Mile=0}     => {V2=Patriot}           0.6  0.7500000  1.2500000     6
[252]    {V2=Patriot}       => {LOTR2=0}              0.6  1.0000000  1.2500000     6
[253]    {LOTR2=0}          => {V2=Patriot}           0.6  0.7500000  1.2500000     6
[254]    {V2=Patriot}       => {Harry Potter1=0}      0.6  1.0000000  1.2500000     6
[255]    {Harry Potter1=0}  => {V2=Patriot}           0.6  0.7500000  1.2500000     6
[256]    {V2=Patriot}       => {LOTR1=0}              0.6  1.0000000  1.2500000     6
[257]    {LOTR1=0}          => {V2=Patriot}           0.6  0.7500000  1.2500000     6
[258]    {V2=Patriot}       => {LOTR=0}               0.6  1.0000000  1.1111111     6
[259]    {V2=Patriot}       => {Braveheart=0}         0.5  0.8333333  0.9259259     5
[260]    {V2=Patriot}       => {Harry Potter2=0}      0.6  1.0000000  1.1111111     6
[261]    {V1=Gladiator}     => {Gladiator=1}          0.6  1.0000000  1.4285714     6
[262]    {Gladiator=1}      => {V1=Gladiator}         0.6  0.8571429  1.4285714     6
[263]    {V1=Gladiator}     => {Green Mile=0}         0.6  1.0000000  1.2500000     6
[264]    {Green Mile=0}     => {V1=Gladiator}         0.6  0.7500000  1.2500000     6
[265]    {V1=Gladiator}     => {LOTR2=0}              0.6  1.0000000  1.2500000     6
[266]    {LOTR2=0}          => {V1=Gladiator}         0.6  0.7500000  1.2500000     6
[267]    {V1=Gladiator}     => {Harry Potter1=0}      0.6  1.0000000  1.2500000     6
[268]    {Harry Potter1=0}  => {V1=Gladiator}         0.6  0.7500000  1.2500000     6
[269]    {V1=Gladiator}     => {LOTR1=0}              0.6  1.0000000  1.2500000     6
[270]    {LOTR1=0}          => {V1=Gladiator}         0.6  0.7500000  1.2500000     6
[271]    {V1=Gladiator}     => {LOTR=0}               0.6  1.0000000  1.1111111     6
[272]    {V1=Gladiator}     => {Braveheart=0}         0.5  0.8333333  0.9259259     5
[273]    {V1=Gladiator}     => {Harry Potter2=0}      0.6  1.0000000  1.1111111     6
[274]    {Sixth Sense=1}    => {Gladiator=1}          0.5  0.8333333  1.1904762     5
[275]    {Gladiator=1}      => {Sixth Sense=1}        0.5  0.7142857  1.1904762     5
[276]    {Sixth Sense=1}    => {LOTR2=0}              0.5  0.8333333  1.0416667     5
[277]    {Sixth Sense=1}    => {Harry Potter1=0}      0.5  0.8333333  1.0416667     5
[278]    {Sixth Sense=1}    => {LOTR1=0}              0.5  0.8333333  1.0416667     5
[279]    {Sixth Sense=1}    => {LOTR=0}               0.5  0.8333333  0.9259259     5
[280]    {Sixth Sense=1}    => {Braveheart=0}         0.6  1.0000000  1.1111111     6
[281]    {Sixth Sense=1}    => {Harry Potter2=0}      0.6  1.0000000  1.1111111     6
[282]    {Gladiator=1}      => {Green Mile=0}         0.6  0.8571429  1.0714286     6
[283]    {Green Mile=0}     => {Gladiator=1}          0.6  0.7500000  1.0714286     6
[284]    {Gladiator=1}      => {LOTR2=0}              0.7  1.0000000  1.2500000     7
[285]    {LOTR2=0}          => {Gladiator=1}          0.7  0.8750000  1.2500000     7
[286]    {Gladiator=1}      => {Harry Potter1=0}      0.7 

## inspect(sort(rules, by="lift"))

lhs                                            rhs        support confidence
[1]   {CookBks,GeogBks,ItalArt}                   => {ItalCook} 0.0240  0.9600000 
[2]   {CookBks,ArtBks,GeogBks,ItalArt}            => {ItalCook} 0.0240  0.9600000 
[3]   {ChildBks,CookBks,ItalArt}                  => {ItalCook} 0.0285  0.9500000 
[4]   {ChildBks,CookBks,ArtBks,ItalArt}           => {ItalCook} 0.0285  0.9500000 
[5]   {CookBks,DoItYBks,ItalArt}                  => {ItalCook} 0.0250  0.9259259 
[6]   {CookBks,DoItYBks,ArtBks,ItalArt}           => {ItalCook} 0.0250  0.9259259 
[7]   {CookBks,ItalArt}                           => {ItalCook} 0.0375  0.9146341 
[8]   {CookBks,ArtBks,ItalArt}                    => {ItalCook} 0.0375  0.9146341 
[9]   {ChildBks,CookBks,ItalAtlas}                => {ItalCook} 0.0200  0.8888889 
[10]  {ChildBks,CookBks,RefBks,ItalAtlas}         => {ItalCook} 0.0200  0.8888889 
[11]  {DoItYBks,ItalArt}                          => {ItalCook} 0.0250  0.8333333 
[12]  {DoItYBks,ArtBks,ItalArt}                   => {ItalCook} 0.0250  0.8333333 
[13]  {GeogBks,ItalArt}                           => {ItalCook} 0.0240  0.8135593 
[14]  {ArtBks,GeogBks,ItalArt}                    => {ItalCook} 0.0240  0.8135593 
[15]  {CookBks,ItalAtlas}                         => {ItalCook} 0.0230  0.8070175 
[16]  {CookBks,RefBks,ItalAtlas}                  => {ItalCook} 0.0230  0.8070175 
[17]  {ChildBks,ItalArt}                          => {ItalCook} 0.0285  0.7916667 
[18]  {ChildBks,ArtBks,ItalArt}                   => {ItalCook} 0.0285  0.7916667 
[19]  {ItalArt}                                   => {ItalCook} 0.0375  0.7731959 
[20]  {ArtBks,ItalArt}                            => {ItalCook} 0.0375  0.7731959 
[21]  {ChildBks,ItalAtlas}                        => {ItalCook} 0.0200  0.7017544 
[22]  {ChildBks,RefBks,ItalAtlas}                 => {ItalCook} 0.0200  0.7017544 
[23]  {ItalAtlas}                                 => {RefBks}   0.0370  1.0000000 
[24]  {ItalCook,ItalAtlas}                        => {RefBks}   0.0230  1.0000000 
[25]  {GeogBks,ItalAtlas}                         => {RefBks}   0.0205  1.0000000 
[26]  {ChildBks,ItalAtlas}                        => {RefBks}   0.0285  1.0000000 
[27]  {CookBks,ItalAtlas}                         => {RefBks}   0.0285  1.0000000 
[28]  {ChildBks,ItalCook,ItalAtlas}               => {RefBks}   0.0200  1.0000000 
[29]  {CookBks,ItalCook,ItalAtlas}                => {RefBks}   0.0230  1.0000000 
[30]  {ChildBks,CookBks,ItalAtlas}                => {RefBks}   0.0225  1.0000000 
[31]  {ChildBks,CookBks,ItalCook,ItalAtlas}       => {RefBks}   0.0200  1.0000000 
[32]  {ItalArt}                                   => {ArtBks}   0.0485  1.0000000 
[33]  {ItalCook,ItalArt}                          => {ArtBks}   0.0375  1.0000000 
[34]  {RefBks,ItalArt}                            => {ArtBks}   0.0200  1.0000000 
[35]  {YouthBks,ItalArt}                          => {ArtBks}   0.0230  1.0000000 
[36]  {DoItYBks,ItalArt}                          => {ArtBks}   0.0300  1.0000000 
[37]  {GeogBks,ItalArt}                           => {ArtBks}   0.0295  1.0000000 
[38]  {ChildBks,ItalArt}                          => {ArtBks}   0.0360  1.0000000 
[39]  {CookBks,ItalArt}                           => {ArtBks}   0.0410  1.0000000 
[40]  {DoItYBks,ItalCook,ItalArt}                 => {ArtBks}   0.0250  1.0000000 
[41]  {GeogBks,ItalCook,ItalArt}                  => {ArtBks}   0.0240  1.0000000 
[42]  {ChildBks,ItalCook,ItalArt}                 => {ArtBks}   0.0285  1.0000000 
[43]  {CookBks,ItalCook,ItalArt}                  => {ArtBks}   0.0375  1.0000000 
[44]  {ChildBks,DoItYBks,ItalArt}                 => {ArtBks}   0.0220  1.0000000 
[45]  {CookBks,DoItYBks,ItalArt}                  => {ArtBks}   0.0270  1.0000000 
[46]  {ChildBks,GeogBks,ItalArt}                  => {ArtBks}   0.0230  1.0000000 
[47]  {CookBks,GeogBks,ItalArt}                   => {ArtBks}   0.0250  1.0000000 
[48]  {ChildBks,CookBks,ItalArt}                  => {ArtBks}   0.0300  1.0000000 
[49]  {CookBks,DoItYBks,ItalCook,ItalArt}         => {ArtBks}   0.0250  1.0000000 
[50]  {CookBks,GeogBks,ItalCook,ItalArt}          => {ArtBks}   0.0240  1.0000000 
[51]  {ChildBks,CookBks,ItalCook,ItalArt}         => {ArtBks}   0.0285  1.0000000 
[52]  {ChildBks,CookBks,DoItYBks,ItalArt}         => {ArtBks}   0.0200  1.0000000 
[53]  {DoItYBks,Florence}                         => {ArtBks}   0.0245  0.7777778 
[54]  {ChildBks,GeogBks,Florence}                 => {ArtBks}   0.0230  0.7540984 
[55]  {ChildBks,CookBks,Florence}                 => {ArtBks}   0.0250  0.7462687 
[56]  {CookBks,GeogBks,Florence}                  => {ArtBks}   0.0230  0.7419355 
[57]  {GeogBks,Florence}                          => {ArtBks}   0.0300  0.7058824 
[58]  {ChildBks,CookBks,Florence}                 => {GeogBks}  0.0245  0.7313433 
[59]  {CookBks,ArtBks,Florence}                   => {GeogBks}  0.0230  0.7301587 
[60]  {YouthBks,CookBks,DoItYBks,ArtBks}          => {GeogBks}  0.0370  0.7047619 
[61]  {ItalCook}                                  => {CookBks}  0.1135  1.0000000 
[62]  {ItalCook,ItalAtlas}                        => {CookBks}  0.0230  1.0000000 
[63]  {ItalCook,ItalArt}                          => {CookBks}  0.0375  1.0000000 
[64]  {RefBks,ItalCook}                           => {CookBks}  0.0465  1.0000000 
[65]  {YouthBks,ItalCook}                         => {CookBks}  0.0590  1.0000000 
[66]  {ArtBks,ItalCook}                           => {CookBks}  0.0565  1.0000000 
[67]  {DoItYBks,ItalCook}                         => {CookBks}  0.0585  1.0000000 
[68]  {GeogBks,ItalCook}                          => {CookBks}  0.0640  1.0000000 
[69]  {ChildBks,ItalCook}                         => {CookBks}  0.0850  1.0000000 
[70]  {RefBks,ItalCook,ItalAtlas}                 => {CookBks}  0.0230  1.0000000 
[71]  {ChildBks,ItalCook,ItalAtlas}               => {CookBks}  0.0200  1.0000000 
[72]  {ArtBks,ItalCook,ItalArt}                   => {CookBks}  0.0375  1.0000000 
[73]  {DoItYBks,ItalCook,ItalArt}                 => {CookBks}  0.0250  1.0000000 
[74]  {GeogBks,ItalCook,ItalArt}                  => {CookBks}  0.0240  1.0000000 
[75]  {ChildBks,ItalCook,ItalArt}                 => {CookBks}  0.0285  1.0000000 
[76]  {YouthBks,RefBks,ItalCook}                  => {CookBks}  0.0265  1.0000000 
[77]  {RefBks,ArtBks,ItalCook}                    => {CookBks}  0.0235  1.0000000 
[78]  {DoItYBks,RefBks,ItalCook}                  => {CookBks}  0.0250  1.0000000 
[79]  {RefBks,GeogBks,ItalCook}                   => {CookBks}  0.0290  1.0000000 
[80]  {ChildBks,RefBks,ItalCook}                  => {CookBks}  0.0415  1.0000000 
[81]  {YouthBks,ArtBks,ItalCook}                  => {CookBks}  0.0305  1.0000000 
[82]  {YouthBks,DoItYBks,ItalCook}                => {CookBks}  0.0310  1.0000000 
[83]  {YouthBks,GeogBks,ItalCook}                 => {CookBks}  0.0345  1.0000000 
[84]  {ChildBks,YouthBks,ItalCook}                => {CookBks}  0.0460  1.0000000 
[85]  {DoItYBks,ArtBks,ItalCook}                  => {CookBks}  0.0365  1.0000000 
[86]  {ArtBks,GeogBks,ItalCook}                   => {CookBks}  0.0360  1.0000000 
[87]  {ChildBks,ArtBks,ItalCook}                  => {CookBks}  0.0455  1.0000000 
[88]  {DoItYBks,GeogBks,ItalCook}                 => {CookBks}  0.0345  1.0000000 
[89]  {ChildBks,DoItYBks,ItalCook}                => {CookBks}  0.0460  1.0000000 
[90]  {ChildBks,GeogBks,ItalCook}                 => {CookBks}  0.0525  1.0000000 
[91]  {ChildBks,RefBks,ItalCook,ItalAtlas}        => {CookBks}  0.0200  1.0000000 
[92]  {DoItYBks,ArtBks,ItalCook,ItalArt}          => {CookBks}  0.0250  1.0000000 
[93]  {ArtBks,GeogBks,ItalCook,ItalArt}           => {CookBks}  0.0240  1.0000000 
[94]  {ChildBks,ArtBks,ItalCook,ItalArt}          => {CookBks}  0.0285  1.0000000 
[95]  {ChildBks,YouthBks,RefBks,ItalCook}         => {CookBks}  0.0245  1.0000000 
[96]  {ChildBks,RefBks,ArtBks,ItalCook}           => {CookBks}  0.0220  1.0000000 
[97]  {ChildBks,DoItYBks,RefBks,ItalCook}         => {CookBks}  0.0225  1.0000000 
[98]  {ChildBks,RefBks,GeogBks,ItalCook}          => {CookBks}  0.0270  1.0000000 
[99]  {YouthBks,ArtBks,GeogBks,ItalCook}          => {CookBks}  0.0200  1.0000000 
[100] {ChildBks,YouthBks,ArtBks,ItalCook}         => {CookBks}  0.0255  1.0000000 
[101] {ChildBks,YouthBks,DoItYBks,ItalCook}       => {CookBks}  0.0245  1.0000000 
[102] {ChildBks,YouthBks,GeogBks,ItalCook}        => {CookBks}  0.0300  1.0000000 
[103] {DoItYBks,ArtBks,GeogBks,ItalCook}          => {CookBks}  0.0215  1.0000000 
[104] {ChildBks,DoItYBks,ArtBks,ItalCook}         => {CookBks}  0.0285  1.0000000 
[105] {ChildBks,ArtBks,GeogBks,ItalCook}          => {CookBks}  0.0300  1.0000000 
[106] {ChildBks,DoItYBks,GeogBks,ItalCook}        => {CookBks}  0.0270  1.0000000 
[107] {RefBks,ArtBks,ItalCook}                    => {ChildBks} 0.0220  0.9361702 
[108] {CookBks,RefBks,ArtBks,ItalCook}            => {ChildBks} 0.0220  0.9361702 
[109] {RefBks,GeogBks,ItalCook}                   => {ChildBks} 0.0270  0.9310345 
[110] {CookBks,RefBks,GeogBks,ItalCook}           => {ChildBks} 0.0270  0.9310345 
[111] {YouthBks,CookBks,DoItYBks,RefBks,GeogBks}  => {ChildBks} 0.0270  0.9310345 
[112] {YouthBks,RefBks,ItalCook}                  => {ChildBks} 0.0245  0.9245283 
[113] {YouthBks,CookBks,RefBks,ItalCook}          => {ChildBks} 0.0245  0.9245283 
[114] {YouthBks,DoItYBks,RefBks,GeogBks}          => {ChildBks} 0.0300  0.9230769 
[115] {YouthBks,DoItYBks,ArtBks,GeogBks}          => {CookBks}  0.0370  0.9367089 
[116] {YouthBks,CookBks,RefBks,GeogBks}           => {ChildBks} 0.0440  0.9166667 
[117] {YouthBks,DoItYBks,RefBks}                  => {ChildBks} 0.0530  0.9137931 
[118] {CookBks,DoItYBks,RefBks,GeogBks}           => {ChildBks} 0.0450  0.9090909 
[119] {ChildBks,YouthBks,DoItYBks,ArtBks,GeogBks} => {CookBks}  0.0310  0.9253731 
[120] {YouthBks,CookBks,DoItYBks,RefBks}          => {ChildBks} 0.0440  0.9072165 
[121] {YouthBks,RefBks,GeogBks}                   => {ChildBks} 0.0515  0.9035088 
[122] {DoItYBks,RefBks,ItalCook}                  => {ChildBks} 0.0225  0.9000000 
[123] {CookBks,DoItYBks,RefBks,ItalCook}          => {ChildBks} 0.0225  0.9000000 
[124] {DoItYBks,RefBks,GeogBks}                   => {ChildBks} 0.0525  0.8974359 
[125] {RefBks,ItalCook}                           => {ChildBks} 0.0415  0.8924731 
[126] {CookBks,RefBks,ItalCook}                   => {ChildBks} 0.0415  0.8924731 
[127] {ChildBks,DoItYBks,ItalArt}                 => {CookBks}  0.0200  0.9090909 
[128] {ChildBks,DoItYBks,ArtBks,ItalArt}          => {CookBks}  0.0200  0.9090909 
[129] {ChildBks,YouthBks,DoItYBks,GeogBks}        => {CookBks}  0.0510  0.9026549 
[130] {YouthBks,RefBks,ArtBks,GeogBks}            => {ChildBks} 0.0270  0.8852459 
[131] {YouthBks,DoItYBks,RefBks,ArtBks}           => {ChildBks} 0.0265  0.8833333 
[132] {DoItYBks,ItalArt}                          => {CookBks}  0.0270  0.9000000 
[133] {DoItYBks,ArtBks,ItalArt}                   => {CookBks}  0.0270  0.9000000 
[134] {ChildBks,YouthBks,DoItYBks,RefBks,GeogBks} => {CookBks}  0.0270  0.9000000 
[135] {ChildBks,DoItYBks,ArtBks,GeogBks}          => {CookBks}  0.0535  0.8991597 
[136] {YouthBks,CookBks,RefBks,ArtBks,GeogBks}    => {ChildBks} 0.0225  0.8823529 
[137] {CookBks,RefBks,GeogBks}                    => {ChildBks} 0.0785  0.8820225 
[138] {CookBks,DoItYBks,RefBks}                   => {ChildBks} 0.0745  0.8816568 
[139] {CookBks,RefBks,ArtBks,GeogBks}             => {ChildBks} 0.0405  0.8804348 
[140] {YouthBks,CookBks,RefBks}                   => {ChildBks} 0.0680  0.8774194 
[141] {RefBks,ArtBks,GeogBks}                     => {ChildBks} 0.0495  0.8761062 
[142] {YouthBks,DoItYBks,RefBks,GeogBks}          => {CookBks}  0.0290  0.8923077 
      lift     count
[1]   8.458150  48  
[2]   8.458150  48  
[3]   8.370044  57  
[4]   8.370044  57  
[5]   8.157938  50  
[6]   8.157938  50  
[7]   8.058451  75  
[8]   8.058451  75  
[9]   7.831620  40  
[10]  7.831620  40  
[11]  7.342144  50  
[12]  7.342144  50  
[13]  7.167924  48  
[14]  7.167924  48  
[15]  7.110287  46  
[16]  7.110287  46  
[17]  6.975037  57  
[18]  6.975037  57  
[19]  6.812298  75  
[20]  6.812298  75  
[21]  6.182858  40  
[22]  6.182858  40  
[23]  4.662005  74  
[24]  4.662005  46  
[25]  4.662005  41  
[26]  4.662005  57  
[27]  4.662005  57  
[28]  4.662005  40  
[29]  4.662005  46  
[30]  4.662005  45  
[31]  4.662005  40  
[32]  4.149378  97  
[33]  4.149378  75  
[34]  4.149378  40  
[35]  4.149378  46  
[36]  4.149378  60  
[37]  4.149378  59  
[38]  4.149378  72  
[39]  4.149378  82  
[40]  4.149378  50  
[41]  4.149378  48  
[42]  4.149378  57  
[43]  4.149378  75  
[44]  4.149378  44  
[45]  4.149378  54  
[46]  4.149378  46  
[47]  4.149378  50  
[48]  4.149378  60  
[49]  4.149378  50  
[50]  4.149378  48  
[51]  4.149378  57  
[52]  4.149378  40  
[53]  3.227294  49  
[54]  3.129039  46  
[55]  3.096550  50  
[56]  3.078570  46  
[57]  2.928972  60  
[58]  2.649795  49  
[59]  2.645503  46  
[60]  2.553485  74  
[61]  2.320186 227  
[62]  2.320186  46  
[63]  2.320186  75  
[64]  2.320186  93  
[65]  2.320186 118  
[66]  2.320186 113  
[67]  2.320186 117  
[68]  2.320186 128  
[69]  2.320186 170  
[70]  2.320186  46  
[71]  2.320186  40  
[72]  2.320186  75  
[73]  2.320186  50  
[74]  2.320186  48  
[75]  2.320186  57  
[76]  2.320186  53  
[77]  2.320186  47  
[78]  2.320186  50  
[79]  2.320186  58  
[80]  2.320186  83  
[81]  2.320186  61  
[82]  2.320186  62  
[83]  2.320186  69  
[84]  2.320186  92  
[85]  2.320186  73  
[86]  2.320186  72  
[87]  2.320186  91  
[88]  2.320186  69  
[89]  2.320186  92  
[90]  2.320186 105  
[91]  2.320186  40  
[92]  2.320186  50  
[93]  2.320186  48  
[94]  2.320186  57  
[95]  2.320186  49  
[96]  2.320186  44  
[97]  2.320186  45  
[98]  2.320186  54  
[99]  2.320186  40  
[100] 2.320186  51  
[101] 2.320186  49  
[102] 2.320186  60  
[103] 2.320186  43  
[104] 2.320186  57  
[105] 2.320186  60  
[106] 2.320186  54  
[107] 2.213168  44  
[108] 2.213168  44  
[109] 2.201027  54  
[110] 2.201027  54  
[111] 2.201027  54  
[112] 2.185646  49  
[113] 2.185646  49  
[114] 2.182215  60  
[115] 2.173338  74  
[116] 2.167061  88  
[117] 2.160267 106  
[118] 2.149151  90  
[119] 2.147037  62  
[120] 2.144720  88  
[121] 2.135955 103  
[122] 2.127660  45  
[123] 2.127660  45  
[124] 2.121598 105  
[125] 2.109866  83  
[126] 2.109866  83  
[127] 2.109260  40  
[128] 2.109260  40  
[129] 2.094327 102  
[130] 2.092780  54  
[131] 2.088258  53  
[132] 2.088167  54  
[133] 2.088167  54  
[134] 2.088167  54  
[135] 2.086217 107  
[136] 2.085941  45  
[137] 2.085160 157  
[138] 2.084295 149  
[139] 2.081406  81  
[140] 2.074277 136  
[141] 2.071173  99  
[142] 2.070319  58  



## head(quality(rules))

  support confidence     lift count
1  0.0370  1.0000000 4.662005    74
2  0.0285  0.7702703 1.820970    57
3  0.0285  0.7702703 1.787170    57
4  0.0375  0.7731959 6.812298    75
5  0.0485  1.0000000 4.149378    97
6  0.0360  0.7422680 1.754771    72



 ### plot(rules)
 



### For better visualizations we can use other methods to plot and we can do 
that in a new window  


 ## windows()


  ## plot(rules,method = "grouped")


 








 ### plot(rules[1:20] , method = "graph")


 

### . Thus ,  we can Association rules are formed , we can by :
 #### write(rules , file = " arulessol.csv" , sep="," )
 
