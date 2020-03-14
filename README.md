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
 
 
 # Assignment 2 
 
 
 
 # Association Rules	
		                

 # BP:  Prepare rules for the all the data sets 
# 1) Try different values of support and confidence. Observe the change in number of rules for different support,confidence values
# 2) Change the minimum length in apriori algorithm
# 3) Visulize the obtained rules using different plots 


 # PROCEDURE:

# STEP 1: First we have to Exploratory Data Analysis which can be done by plotting scattered plot, box plots and summary.

## summary(book_1_)
V1                V2                V3             V4        V5   
 Gladiator    :6   Harry Potter2:1   Braveheart   :1   Green Mile:2   LOTR2:1  
 Harry Potter1:1   LOTR         :1   Gladiator    :1   NA's      :8   NA's :9  
 LOTR1        :1   LOTR1        :1   Harry Potter1:1                           
 Sixth Sense  :2   LOTR2        :1   Sixth Sense  :4                           
                   Patriot      :6   NA's         :3                           
                                                                               
  Sixth Sense    Gladiator        LOTR1     Harry Potter1    Patriot   
 Min.   :0.0   Min.   :0.00   Min.   :0.0   Min.   :0.0   Min.   :0.0  
 1st Qu.:0.0   1st Qu.:0.25   1st Qu.:0.0   1st Qu.:0.0   1st Qu.:0.0  
 Median :1.0   Median :1.00   Median :0.0   Median :0.0   Median :1.0  
 Mean   :0.6   Mean   :0.70   Mean   :0.2   Mean   :0.2   Mean   :0.6  
 3rd Qu.:1.0   3rd Qu.:1.00   3rd Qu.:0.0   3rd Qu.:0.0   3rd Qu.:1.0  
 Max.   :1.0   Max.   :1.00   Max.   :1.0   Max.   :1.0   Max.   :1.0  
     LOTR2     Harry Potter2      LOTR       Braveheart    Green Mile 
 Min.   :0.0   Min.   :0.0   Min.   :0.0   Min.   :0.0   Min.   :0.0  
 1st Qu.:0.0   1st Qu.:0.0   1st Qu.:0.0   1st Qu.:0.0   1st Qu.:0.0  
 Median :0.0   Median :0.0   Median :0.0   Median :0.0   Median :0.0  
 Mean   :0.2   Mean   :0.1   Mean   :0.1   Mean   :0.1   Mean   :0.2  
 3rd Qu.:0.0   3rd Qu.:0.0   3rd Qu.:0.0   3rd Qu.:0.0   3rd Qu.:0.0  
 Max.   :1.0   Max.   :1.0   Max.   :1.0   Max.   :1.0   Max.   :1.0  

# From the summary we can see that all are lying in the same level , it can my confirmed by using Box Plot .













# Box  Plot for the Following data frame is:


 

# Scatter plot is given by :


 





# STEP 2:

# Building Rules using Apriori algorithm which is given by :

 ## Rules  <-apriori(my_movies,parameter=list(support=0.002,confidence=0.7)) 
Apriori

## Parameter specification:
##  confidence minval smax arem  aval originalSupport maxtime support minlen maxlen
##        0.7    0.1    1 none FALSE            TRUE       5    0.02      1     10
##  target   ext
##  rules FALSE

## Algorithmic control:
 ## filter tree heap memopt load sort verbose
  ##  0.1 TRUE TRUE  FALSE TRUE    2    TRUE

 ## Absolute minimum support count: 40 

set item appearances ...[0 item(s)] done [0.00s].
set transactions ...[11 item(s), 2000 transaction(s)] done [0.00s].
sorting and recoding items ... [11 item(s)] done [0.00s].
creating transaction tree ... done [0.00s].
checking subsets of size 1 2 3 4 5 6 done [0.00s].
writing ... [299 rule(s)] done [0.00s].
creating S4 object  ... done [0.00s].


inspect(rules)
lhs                                            rhs        support confidence
[1]   {ItalAtlas}                                 => {RefBks}   0.0370  1.0000000 
[2]   {ItalAtlas}                                 => {ChildBks} 0.0285  0.7702703 
[3]   {ItalAtlas}                                 => {CookBks}  0.0285  0.7702703 
[4]   {ItalArt}                                   => {ItalCook} 0.0375  0.7731959 
[5]   {ItalArt}                                   => {ArtBks}   0.0485  1.0000000 
[6]   {ItalArt}                                   => {ChildBks} 0.0360  0.7422680 
[7]   {ItalArt}                                   => {CookBks}  0.0410  0.8453608 
[8]   {ItalCook}                                  => {ChildBks} 0.0850  0.7488987 
[9]   {ItalCook}                                  => {CookBks}  0.1135  1.0000000 
[10]  {RefBks}                                    => {ChildBks} 0.1515  0.7062937 
[11]  {RefBks}                                    => {CookBks}  0.1525  0.7109557 
[12]  {GeogBks}                                   => {ChildBks} 0.1950  0.7065217 
[13]  {ItalCook,ItalAtlas}                        => {RefBks}   0.0230  1.0000000 
[14]  {ItalCook,ItalAtlas}                        => {ChildBks} 0.0200  0.8695652 
[15]  {ChildBks,ItalAtlas}                        => {ItalCook} 0.0200  0.7017544 
[16]  {ItalCook,ItalAtlas}                        => {CookBks}  0.0230  1.0000000 
[17]  {CookBks,ItalAtlas}                         => {ItalCook} 0.0230  0.8070175 
[18]  {GeogBks,ItalAtlas}                         => {RefBks}   0.0205  1.0000000 
[19]  {RefBks,ItalAtlas}                          => {ChildBks} 0.0285  0.7702703 
[20]  {ChildBks,ItalAtlas}                        => {RefBks}   0.0285  1.0000000 
[21]  {RefBks,ItalAtlas}                          => {CookBks}  0.0285  0.7702703 
[22]  {CookBks,ItalAtlas}                         => {RefBks}   0.0285  1.0000000 
[23]  {ChildBks,ItalAtlas}                        => {CookBks}  0.0225  0.7894737 
[24]  {CookBks,ItalAtlas}                         => {ChildBks} 0.0225  0.7894737 
[25]  {ItalCook,ItalArt}                          => {ArtBks}   0.0375  1.0000000 
[26]  {ArtBks,ItalArt}                            => {ItalCook} 0.0375  0.7731959 
[27]  {DoItYBks,ItalArt}                          => {ItalCook} 0.0250  0.8333333 
[28]  {GeogBks,ItalArt}                           => {ItalCook} 0.0240  0.8135593 
[29]  {ItalCook,ItalArt}                          => {ChildBks} 0.0285  0.7600000 
[30]  {ChildBks,ItalArt}                          => {ItalCook} 0.0285  0.7916667 
[31]  {ItalCook,ItalArt}                          => {CookBks}  0.0375  1.0000000 
[32]  {CookBks,ItalArt}                           => {ItalCook} 0.0375  0.9146341 
[33]  {RefBks,ItalArt}                            => {ArtBks}   0.0200  1.0000000 
[34]  {YouthBks,ItalArt}                          => {ArtBks}   0.0230  1.0000000 
[35]  {DoItYBks,ItalArt}                          => {ArtBks}   0.0300  1.0000000 
[36]  {GeogBks,ItalArt}                           => {ArtBks}   0.0295  1.0000000 
[37]  {ArtBks,ItalArt}                            => {ChildBks} 0.0360  0.7422680 
[38]  {ChildBks,ItalArt}                          => {ArtBks}   0.0360  1.0000000 
[39]  {ArtBks,ItalArt}                            => {CookBks}  0.0410  0.8453608 
[40]  {CookBks,ItalArt}                           => {ArtBks}   0.0410  1.0000000 
[41]  {DoItYBks,ItalArt}                          => {ChildBks} 0.0220  0.7333333 
[42]  {DoItYBks,ItalArt}                          => {CookBks}  0.0270  0.9000000 
[43]  {GeogBks,ItalArt}                           => {ChildBks} 0.0230  0.7796610 
[44]  {GeogBks,ItalArt}                           => {CookBks}  0.0250  0.8474576 
[45]  {ChildBks,ItalArt}                          => {CookBks}  0.0300  0.8333333 
[46]  {CookBks,ItalArt}                           => {ChildBks} 0.0300  0.7317073 
[47]  {YouthBks,Florence}                         => {CookBks}  0.0200  0.7843137 
[48]  {DoItYBks,Florence}                         => {ArtBks}   0.0245  0.7777778 
[49]  {GeogBks,Florence}                          => {ArtBks}   0.0300  0.7058824 
[50]  {DoItYBks,Florence}                         => {ChildBks} 0.0225  0.7142857 
[51]  {DoItYBks,Florence}                         => {CookBks}  0.0235  0.7460317 
[52]  {GeogBks,Florence}                          => {ChildBks} 0.0305  0.7176471 
[53]  {GeogBks,Florence}                          => {CookBks}  0.0310  0.7294118 
[54]  {CookBks,Florence}                          => {ChildBks} 0.0335  0.7052632 
[55]  {RefBks,ItalCook}                           => {ChildBks} 0.0415  0.8924731 
[56]  {RefBks,ItalCook}                           => {CookBks}  0.0465  1.0000000 
[57]  {YouthBks,ItalCook}                         => {ChildBks} 0.0460  0.7796610 
[58]  {YouthBks,ItalCook}                         => {CookBks}  0.0590  1.0000000 
[59]  {ArtBks,ItalCook}                           => {ChildBks} 0.0455  0.8053097 
[60]  {ArtBks,ItalCook}                           => {CookBks}  0.0565  1.0000000 
[61]  {DoItYBks,ItalCook}                         => {ChildBks} 0.0460  0.7863248 
[62]  {DoItYBks,ItalCook}                         => {CookBks}  0.0585  1.0000000 
[63]  {GeogBks,ItalCook}                          => {ChildBks} 0.0525  0.8203125 
[64]  {GeogBks,ItalCook}                          => {CookBks}  0.0640  1.0000000 
[65]  {ChildBks,ItalCook}                         => {CookBks}  0.0850  1.0000000 
[66]  {CookBks,ItalCook}                          => {ChildBks} 0.0850  0.7488987 
[67]  {YouthBks,RefBks}                           => {ChildBks} 0.0830  0.8601036 
[68]  {YouthBks,RefBks}                           => {CookBks}  0.0775  0.8031088 
[69]  {RefBks,ArtBks}                             => {ChildBks} 0.0760  0.8491620 
[70]  {RefBks,ArtBks}                             => {CookBks}  0.0700  0.7821229 
[71]  {DoItYBks,RefBks}                           => {ChildBks} 0.0900  0.8530806 
[72]  {DoItYBks,RefBks}                           => {CookBks}  0.0845  0.8009479 
[73]  {RefBks,GeogBks}                            => {ChildBks} 0.0940  0.8506787 
[74]  {RefBks,GeogBks}                            => {CookBks}  0.0890  0.8054299 
[75]  {ChildBks,RefBks}                           => {CookBks}  0.1225  0.8085809 
[76]  {CookBks,RefBks}                            => {ChildBks} 0.1225  0.8032787 
[77]  {YouthBks,ArtBks}                           => {ChildBks} 0.0805  0.7970297 
[78]  {YouthBks,ArtBks}                           => {CookBks}  0.0810  0.8019802 
[79]  {YouthBks,DoItYBks}                         => {ChildBks} 0.0950  0.8225108 
[80]  {YouthBks,DoItYBks}                         => {CookBks}  0.0950  0.8225108 
[81]  {YouthBks,GeogBks}                          => {ChildBks} 0.0990  0.8215768 
[82]  {YouthBks,GeogBks}                          => {CookBks}  0.0970  0.8049793 
[83]  {ChildBks,YouthBks}                         => {CookBks}  0.1290  0.7818182 
[84]  {YouthBks,CookBks}                          => {ChildBks} 0.1290  0.7962963 
[85]  {DoItYBks,ArtBks}                           => {ChildBks} 0.0950  0.7692308 
[86]  {DoItYBks,ArtBks}                           => {CookBks}  0.1015  0.8218623 
[87]  {ArtBks,GeogBks}                            => {ChildBks} 0.1020  0.8000000 
[88]  {ArtBks,GeogBks}                            => {CookBks}  0.1035  0.8117647 
[89]  {ChildBks,ArtBks}                           => {CookBks}  0.1265  0.7784615 
[90]  {CookBks,ArtBks}                            => {ChildBks} 0.1265  0.7574850 
[91]  {DoItYBks,GeogBks}                          => {ChildBks} 0.1045  0.7886792 
[92]  {DoItYBks,GeogBks}                          => {CookBks}  0.1085  0.8188679 
[93]  {ChildBks,DoItYBks}                         => {CookBks}  0.1460  0.7934783 
[94]  {CookBks,DoItYBks}                          => {ChildBks} 0.1460  0.7786667 
[95]  {ChildBks,GeogBks}                          => {CookBks}  0.1495  0.7666667 
[96]  {CookBks,GeogBks}                           => {ChildBks} 0.1495  0.7766234 
[97]  {RefBks,ItalCook,ItalAtlas}                 => {ChildBks} 0.0200  0.8695652 
[98]  {ChildBks,ItalCook,ItalAtlas}               => {RefBks}   0.0200  1.0000000 
[99]  {ChildBks,RefBks,ItalAtlas}                 => {ItalCook} 0.0200  0.7017544 
[100] {RefBks,ItalCook,ItalAtlas}                 => {CookBks}  0.0230  1.0000000 
[101] {CookBks,ItalCook,ItalAtlas}                => {RefBks}   0.0230  1.0000000 
[102] {CookBks,RefBks,ItalAtlas}                  => {ItalCook} 0.0230  0.8070175 
[103] {ChildBks,ItalCook,ItalAtlas}               => {CookBks}  0.0200  1.0000000 
[104] {CookBks,ItalCook,ItalAtlas}                => {ChildBks} 0.0200  0.8695652 
[105] {ChildBks,CookBks,ItalAtlas}                => {ItalCook} 0.0200  0.8888889 
[106] {ChildBks,RefBks,ItalAtlas}                 => {CookBks}  0.0225  0.7894737 
[107] {CookBks,RefBks,ItalAtlas}                  => {ChildBks} 0.0225  0.7894737 
[108] {ChildBks,CookBks,ItalAtlas}                => {RefBks}   0.0225  1.0000000 
[109] {DoItYBks,ItalCook,ItalArt}                 => {ArtBks}   0.0250  1.0000000 
[110] {DoItYBks,ArtBks,ItalArt}                   => {ItalCook} 0.0250  0.8333333 
[111] {GeogBks,ItalCook,ItalArt}                  => {ArtBks}   0.0240  1.0000000 
[112] {ArtBks,GeogBks,ItalArt}                    => {ItalCook} 0.0240  0.8135593 
[113] {ArtBks,ItalCook,ItalArt}                   => {ChildBks} 0.0285  0.7600000 
[114] {ChildBks,ItalCook,ItalArt}                 => {ArtBks}   0.0285  1.0000000 
[115] {ChildBks,ArtBks,ItalArt}                   => {ItalCook} 0.0285  0.7916667 
[116] {ArtBks,ItalCook,ItalArt}                   => {CookBks}  0.0375  1.0000000 
[117] {CookBks,ItalCook,ItalArt}                  => {ArtBks}   0.0375  1.0000000 
[118] {CookBks,ArtBks,ItalArt}                    => {ItalCook} 0.0375  0.9146341 
[119] {DoItYBks,ItalCook,ItalArt}                 => {CookBks}  0.0250  1.0000000 
[120] {CookBks,DoItYBks,ItalArt}                  => {ItalCook} 0.0250  0.9259259 
[121] {GeogBks,ItalCook,ItalArt}                  => {CookBks}  0.0240  1.0000000 
[122] {CookBks,GeogBks,ItalArt}                   => {ItalCook} 0.0240  0.9600000 
[123] {ChildBks,ItalCook,ItalArt}                 => {CookBks}  0.0285  1.0000000 
[124] {CookBks,ItalCook,ItalArt}                  => {ChildBks} 0.0285  0.7600000 
[125] {ChildBks,CookBks,ItalArt}                  => {ItalCook} 0.0285  0.9500000 
[126] {DoItYBks,ArtBks,ItalArt}                   => {ChildBks} 0.0220  0.7333333 
[127] {ChildBks,DoItYBks,ItalArt}                 => {ArtBks}   0.0220  1.0000000 
[128] {DoItYBks,ArtBks,ItalArt}                   => {CookBks}  0.0270  0.9000000 
[129] {CookBks,DoItYBks,ItalArt}                  => {ArtBks}   0.0270  1.0000000 
[130] {ArtBks,GeogBks,ItalArt}                    => {ChildBks} 0.0230  0.7796610 
[131] {ChildBks,GeogBks,ItalArt}                  => {ArtBks}   0.0230  1.0000000 
[132] {ArtBks,GeogBks,ItalArt}                    => {CookBks}  0.0250  0.8474576 
[133] {CookBks,GeogBks,ItalArt}                   => {ArtBks}   0.0250  1.0000000 
[134] {ChildBks,ArtBks,ItalArt}                   => {CookBks}  0.0300  0.8333333 
[135] {CookBks,ArtBks,ItalArt}                    => {ChildBks} 0.0300  0.7317073 
[136] {ChildBks,CookBks,ItalArt}                  => {ArtBks}   0.0300  1.0000000 
[137] {ChildBks,DoItYBks,ItalArt}                 => {CookBks}  0.0200  0.9090909 
[138] {CookBks,DoItYBks,ItalArt}                  => {ChildBks} 0.0200  0.7407407 
[139] {ArtBks,GeogBks,Florence}                   => {ChildBks} 0.0230  0.7666667 
[140] {ChildBks,GeogBks,Florence}                 => {ArtBks}   0.0230  0.7540984 
[141] {ArtBks,GeogBks,Florence}                   => {CookBks}  0.0230  0.7666667 
[142] {CookBks,ArtBks,Florence}                   => {GeogBks}  0.0230  0.7301587 
      lift     count
[1]   4.662005  74  
[2]   1.820970  57  
[3]   1.787170  57  
[4]   6.812298  75  
[5]   4.149378  97  
[6]   1.754771  72  
[7]   1.961394  82  
[8]   1.770446 170  
[9]   2.320186 227  
[10]  1.669725 303  
[11]  1.649549 305  
[12]  1.670264 390  
[13]  4.662005  46  
[14]  2.055710  40  
[15]  6.182858  40  
[16]  2.320186  46  
[17]  7.110287  46  
[18]  4.662005  41  
[19]  1.820970  57  
[20]  4.662005  57  
[21]  1.787170  57  
[22]  4.662005  57  
[23]  1.831725  45  
[24]  1.866368  45  
[25]  4.149378  75  
[26]  6.812298  75  
[27]  7.342144  50  
[28]  7.167924  48  
[29]  1.796690  57  
[30]  6.975037  57  
[31]  2.320186  75  
[32]  8.058451  75  
[33]  4.149378  40  
[34]  4.149378  46  
[35]  4.149378  60  
[36]  4.149378  59  
[37]  1.754771  72  
[38]  4.149378  72  
[39]  1.961394  82  
[40]  4.149378  82  
[41]  1.733649  44  
[42]  2.088167  54  
[43]  1.843170  46  
[44]  1.966259  50  
[45]  1.933488  60  
[46]  1.729805  60  
[47]  1.819753  40  
[48]  3.227294  49  
[49]  2.928972  60  
[50]  1.688619  45  
[51]  1.730932  47  
[52]  1.696565  61  
[53]  1.692371  62  
[54]  1.667289  67  
[55]  2.109866  83  
[56]  2.320186  93  
[57]  1.843170  92  
[58]  2.320186 118  
[59]  1.903806  91  
[60]  2.320186 113  
[61]  1.858924  92  
[62]  2.320186 117  
[63]  1.939273 105  
[64]  2.320186 128  
[65]  2.320186 170  
[66]  1.770446 170  
[67]  2.033342 166  
[68]  1.863362 155  
[69]  2.007475 152  
[70]  1.814670 140  
[71]  2.016739 180  
[72]  1.858348 169  
[73]  2.011061 188  
[74]  1.868747 178  
[75]  1.876058 245  
[76]  1.899004 245  
[77]  1.884231 161  
[78]  1.860743 162  
[79]  1.944470 190  
[80]  1.908378 190  
[81]  1.942262 198  
[82]  1.867701 194  
[83]  1.813963 258  
[84]  1.882497 258  
[85]  1.818512 190  
[86]  1.906873 203  
[87]  1.891253 204  
[88]  1.883445 207  
[89]  1.806175 253  
[90]  1.790745 253  
[91]  1.864490 209  
[92]  1.899926 217  
[93]  1.841017 292  
[94]  1.840820 292  
[95]  1.778809 299  
[96]  1.835989 299  
[97]  2.055710  40  
[98]  4.662005  40  
[99]  6.182858  40  
[100] 2.320186  46  
[101] 4.662005  46  
[102] 7.110287  46  
[103] 2.320186  40  
[104] 2.055710  40  
[105] 7.831620  40  
[106] 1.831725  45  
[107] 1.866368  45  
[108] 4.662005  45  
[109] 4.149378  50  
[110] 7.342144  50  
[111] 4.149378  48  
[112] 7.167924  48  
[113] 1.796690  57  
[114] 4.149378  57  
[115] 6.975037  57  
[116] 2.320186  75  
[117] 4.149378  75  
[118] 8.058451  75  
[119] 2.320186  50  
[120] 8.157938  50  
[121] 2.320186  48  
[122] 8.458150  48  
[123] 2.320186  57  
[124] 1.796690  57  
[125] 8.370044  57  
[126] 1.733649  44  
[127] 4.149378  44  
[128] 2.088167  54  
[129] 4.149378  54  
[130] 1.843170  46  
[131] 4.149378  46  
[132] 1.966259  50  
[133] 4.149378  50  
[134] 1.933488  60  
[135] 1.729805  60  
[136] 4.149378  60  
[137] 2.109260  40  
[138] 1.751160  40  
[139] 1.812451  46  
[140] 3.129039  46  
[141] 1.778809  46  
[142] 2.645503  46  


## inspect(sort(rules, by="lift"))

lhs                   rhs                support confidence       lift count
[1]      {Harry Potter2=1}  => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[2]      {V2=Harry Potter2} => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[3]      {Harry Potter2=1}  => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[4]      {V1=Harry Potter1} => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[5]      {V2=Harry Potter2} => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[6]      {V1=Harry Potter1} => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[7]      {V2=LOTR2}         => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[8]      {V1=LOTR1}         => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[9]      {Braveheart=1}     => {V3=Braveheart}        0.1  1.0000000 10.0000000     1
[10]     {V3=Braveheart}    => {Braveheart=1}         0.1  1.0000000 10.0000000     1
[11]     {V3=Gladiator}     => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[12]     {V2=LOTR}          => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[13]     {V3=Gladiator}     => {LOTR=1}               0.1  1.0000000 10.0000000     1
[14]     {LOTR=1}           => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[15]     {V2=LOTR}          => {LOTR=1}               0.1  1.0000000 10.0000000     1
[16]     {LOTR=1}           => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[17]     {V2=LOTR1}         => {V3=Harry Potter1}     0.1  1.0000000 10.0000000     1
[18]     {V3=Harry Potter1} => {V2=LOTR1}             0.1  1.0000000 10.0000000     1
[19]     {V2=LOTR1}         => {V5=LOTR2}             0.1  1.0000000 10.0000000     1
[20]     {V5=LOTR2}         => {V2=LOTR1}             0.1  1.0000000 10.0000000     1
[21]     {V3=Harry Potter1} => {V5=LOTR2}             0.1  1.0000000 10.0000000     1
[22]     {V5=LOTR2}         => {V3=Harry Potter1}     0.1  1.0000000 10.0000000     1
[23]     {V2=Harry Potter2,                                                          
          Harry Potter2=1}  => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[24]     {V1=Harry Potter1,                                                          
          Harry Potter2=1}  => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[25]     {V1=Harry Potter1,                                                          
          V2=Harry Potter2} => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[26]     {Harry Potter1=1,                                                           
          Harry Potter2=1}  => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[27]     {V2=Harry Potter2,                                                          
          Harry Potter1=1}  => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[28]     {Gladiator=0,                                                               
          Harry Potter2=1}  => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[29]     {V2=Harry Potter2,                                                          
          Gladiator=0}      => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[30]     {Sixth Sense=0,                                                             
          Harry Potter2=1}  => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[31]     {V2=Harry Potter2,                                                          
          Sixth Sense=0}    => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[32]     {Patriot=0,                                                                 
          Harry Potter2=1}  => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[33]     {V2=Harry Potter2,                                                          
          Patriot=0}        => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[34]     {Harry Potter2=1,                                                           
          Green Mile=0}     => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[35]     {V2=Harry Potter2,                                                          
          Green Mile=0}     => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[36]     {LOTR2=0,                                                                   
          Harry Potter2=1}  => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[37]     {V2=Harry Potter2,                                                          
          LOTR2=0}          => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[38]     {LOTR1=0,                                                                   
          Harry Potter2=1}  => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[39]     {V2=Harry Potter2,                                                          
          LOTR1=0}          => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[40]     {Harry Potter2=1,                                                           
          LOTR=0}           => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[41]     {V2=Harry Potter2,                                                          
          LOTR=0}           => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[42]     {Harry Potter2=1,                                                           
          Braveheart=0}     => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[43]     {V2=Harry Potter2,                                                          
          Braveheart=0}     => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[44]     {Harry Potter1=1,                                                           
          Harry Potter2=1}  => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[45]     {V1=Harry Potter1,                                                          
          Harry Potter1=1}  => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[46]     {Gladiator=0,                                                               
          Harry Potter2=1}  => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[47]     {V1=Harry Potter1,                                                          
          Gladiator=0}      => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[48]     {Sixth Sense=0,                                                             
          Harry Potter2=1}  => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[49]     {V1=Harry Potter1,                                                          
          Sixth Sense=0}    => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[50]     {Patriot=0,                                                                 
          Harry Potter2=1}  => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[51]     {V1=Harry Potter1,                                                          
          Patriot=0}        => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[52]     {Harry Potter2=1,                                                           
          Green Mile=0}     => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[53]     {V1=Harry Potter1,                                                          
          Green Mile=0}     => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[54]     {LOTR2=0,                                                                   
          Harry Potter2=1}  => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[55]     {V1=Harry Potter1,                                                          
          LOTR2=0}          => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[56]     {LOTR1=0,                                                                   
          Harry Potter2=1}  => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[57]     {V1=Harry Potter1,                                                          
          LOTR1=0}          => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[58]     {Harry Potter2=1,                                                           
          LOTR=0}           => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[59]     {V1=Harry Potter1,                                                          
          LOTR=0}           => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[60]     {Harry Potter2=1,                                                           
          Braveheart=0}     => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[61]     {V1=Harry Potter1,                                                          
          Braveheart=0}     => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[62]     {Sixth Sense=0,                                                             
          Harry Potter1=1}  => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[63]     {Harry Potter1=1,                                                           
          Green Mile=0}     => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[64]     {Harry Potter1=1,                                                           
          LOTR2=0}          => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[65]     {LOTR1=0,                                                                   
          Harry Potter1=1}  => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[66]     {Gladiator=0,                                                               
          LOTR2=0}          => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[67]     {Gladiator=0,                                                               
          LOTR1=0}          => {Harry Potter2=1}      0.1  1.0000000 10.0000000     1
[68]     {V2=Harry Potter2,                                                          
          Harry Potter1=1}  => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[69]     {V1=Harry Potter1,                                                          
          Harry Potter1=1}  => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[70]     {V2=Harry Potter2,                                                          
          Gladiator=0}      => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[71]     {V1=Harry Potter1,                                                          
          Gladiator=0}      => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[72]     {V2=Harry Potter2,                                                          
          Sixth Sense=0}    => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[73]     {V1=Harry Potter1,                                                          
          Sixth Sense=0}    => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[74]     {V2=Harry Potter2,                                                          
          Patriot=0}        => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[75]     {V1=Harry Potter1,                                                          
          Patriot=0}        => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[76]     {V2=Harry Potter2,                                                          
          Green Mile=0}     => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[77]     {V1=Harry Potter1,                                                          
          Green Mile=0}     => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[78]     {V2=Harry Potter2,                                                          
          LOTR2=0}          => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[79]     {V1=Harry Potter1,                                                          
          LOTR2=0}          => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[80]     {V2=Harry Potter2,                                                          
          LOTR1=0}          => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[81]     {V1=Harry Potter1,                                                          
          LOTR1=0}          => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[82]     {V2=Harry Potter2,                                                          
          LOTR=0}           => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[83]     {V1=Harry Potter1,                                                          
          LOTR=0}           => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[84]     {V2=Harry Potter2,                                                          
          Braveheart=0}     => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[85]     {V1=Harry Potter1,                                                          
          Braveheart=0}     => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[86]     {Sixth Sense=0,                                                             
          Harry Potter1=1}  => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[87]     {Harry Potter1=1,                                                           
          Green Mile=0}     => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[88]     {Harry Potter1=1,                                                           
          LOTR2=0}          => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[89]     {LOTR1=0,                                                                   
          Harry Potter1=1}  => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[90]     {Gladiator=0,                                                               
          LOTR2=0}          => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[91]     {Gladiator=0,                                                               
          LOTR1=0}          => {V2=Harry Potter2}     0.1  1.0000000 10.0000000     1
[92]     {Sixth Sense=0,                                                             
          Harry Potter1=1}  => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[93]     {Harry Potter1=1,                                                           
          Green Mile=0}     => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[94]     {Harry Potter1=1,                                                           
          LOTR2=0}          => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[95]     {LOTR1=0,                                                                   
          Harry Potter1=1}  => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[96]     {Gladiator=0,                                                               
          LOTR2=0}          => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[97]     {Gladiator=0,                                                               
          LOTR1=0}          => {V1=Harry Potter1}     0.1  1.0000000 10.0000000     1
[98]     {V2=LOTR2,                                                                  
          LOTR2=1}          => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[99]     {V1=LOTR1,                                                                  
          LOTR2=1}          => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[100]    {V2=LOTR2,                                                                  
          LOTR1=1}          => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[101]    {V1=LOTR1,                                                                  
          LOTR1=1}          => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[102]    {V2=LOTR2,                                                                  
          Gladiator=0}      => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[103]    {V1=LOTR1,                                                                  
          Gladiator=0}      => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[104]    {V2=LOTR2,                                                                  
          Sixth Sense=0}    => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[105]    {V1=LOTR1,                                                                  
          Sixth Sense=0}    => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[106]    {V2=LOTR2,                                                                  
          Patriot=0}        => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[107]    {V1=LOTR1,                                                                  
          Patriot=0}        => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[108]    {V2=LOTR2,                                                                  
          Green Mile=0}     => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[109]    {V1=LOTR1,                                                                  
          Green Mile=0}     => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[110]    {V2=LOTR2,                                                                  
          Harry Potter1=0}  => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[111]    {V1=LOTR1,                                                                  
          Harry Potter1=0}  => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[112]    {V2=LOTR2,                                                                  
          LOTR=0}           => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[113]    {V1=LOTR1,                                                                  
          LOTR=0}           => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[114]    {V2=LOTR2,                                                                  
          Braveheart=0}     => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[115]    {V1=LOTR1,                                                                  
          Braveheart=0}     => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[116]    {V2=LOTR2,                                                                  
          Harry Potter2=0}  => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[117]    {V1=LOTR1,                                                                  
          Harry Potter2=0}  => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[118]    {Sixth Sense=0,                                                             
          LOTR2=1}          => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[119]    {LOTR2=1,                                                                   
          Green Mile=0}     => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[120]    {Harry Potter1=0,                                                           
          LOTR2=1}          => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[121]    {Sixth Sense=0,                                                             
          LOTR1=1}          => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[122]    {LOTR1=1,                                                                   
          Green Mile=0}     => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[123]    {LOTR1=1,                                                                   
          Harry Potter1=0}  => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[124]    {Gladiator=0,                                                               
          Harry Potter1=0}  => {V2=LOTR2}             0.1  1.0000000 10.0000000     1
[125]    {Sixth Sense=0,                                                             
          LOTR2=1}          => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[126]    {LOTR2=1,                                                                   
          Green Mile=0}     => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[127]    {Harry Potter1=0,                                                           
          LOTR2=1}          => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[128]    {Sixth Sense=0,                                                             
          LOTR1=1}          => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[129]    {LOTR1=1,                                                                   
          Green Mile=0}     => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[130]    {LOTR1=1,                                                                   
          Harry Potter1=0}  => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[131]    {Gladiator=0,                                                               
          Harry Potter1=0}  => {V1=LOTR1}             0.1  1.0000000 10.0000000     1
[132]    {Sixth Sense=0,                                                             
          Braveheart=1}     => {V3=Braveheart}        0.1  1.0000000 10.0000000     1
[133]    {V3=Braveheart,                                                             
          Sixth Sense=0}    => {Braveheart=1}         0.1  1.0000000 10.0000000     1
[134]    {Patriot=1,                                                                 
          Braveheart=1}     => {V3=Braveheart}        0.1  1.0000000 10.0000000     1
[135]    {V3=Braveheart,                                                             
          Patriot=1}        => {Braveheart=1}         0.1  1.0000000 10.0000000     1
[136]    {V2=Patriot,                                                                
          Braveheart=1}     => {V3=Braveheart}        0.1  1.0000000 10.0000000     1
[137]    {V2=Patriot,                                                                
          V3=Braveheart}    => {Braveheart=1}         0.1  1.0000000 10.0000000     1
[138]    {V1=Gladiator,                                                              
          Braveheart=1}     => {V3=Braveheart}        0.1  1.0000000 10.0000000     1
[139]    {V1=Gladiator,                                                              
          V3=Braveheart}    => {Braveheart=1}         0.1  1.0000000 10.0000000     1
[140]    {Gladiator=1,                                                               
          Braveheart=1}     => {V3=Braveheart}        0.1  1.0000000 10.0000000     1
[141]    {V3=Braveheart,                                                             
          Gladiator=1}      => {Braveheart=1}         0.1  1.0000000 10.0000000     1
[142]    {Braveheart=1,                                                              
          Green Mile=0}     => {V3=Braveheart}        0.1  1.0000000 10.0000000     1
[143]    {V3=Braveheart,                                                             
          Green Mile=0}     => {Braveheart=1}         0.1  1.0000000 10.0000000     1
[144]    {LOTR2=0,                                                                   
          Braveheart=1}     => {V3=Braveheart}        0.1  1.0000000 10.0000000     1
[145]    {V3=Braveheart,                                                             
          LOTR2=0}          => {Braveheart=1}         0.1  1.0000000 10.0000000     1
[146]    {Harry Potter1=0,                                                           
          Braveheart=1}     => {V3=Braveheart}        0.1  1.0000000 10.0000000     1
[147]    {V3=Braveheart,                                                             
          Harry Potter1=0}  => {Braveheart=1}         0.1  1.0000000 10.0000000     1
[148]    {LOTR1=0,                                                                   
          Braveheart=1}     => {V3=Braveheart}        0.1  1.0000000 10.0000000     1
[149]    {V3=Braveheart,                                                             
          LOTR1=0}          => {Braveheart=1}         0.1  1.0000000 10.0000000     1
[150]    {LOTR=0,                                                                    
          Braveheart=1}     => {V3=Braveheart}        0.1  1.0000000 10.0000000     1
[151]    {V3=Braveheart,                                                             
          LOTR=0}           => {Braveheart=1}         0.1  1.0000000 10.0000000     1
[152]    {Harry Potter2=0,                                                           
          Braveheart=1}     => {V3=Braveheart}        0.1  1.0000000 10.0000000     1
[153]    {V3=Braveheart,                                                             
          Harry Potter2=0}  => {Braveheart=1}         0.1  1.0000000 10.0000000     1
[154]    {V2=LOTR,                                                                   
          V3=Gladiator}     => {LOTR=1}               0.1  1.0000000 10.0000000     1
[155]    {V3=Gladiator,                                                              
          LOTR=1}           => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[156]    {V2=LOTR,                                                                   
          LOTR=1}           => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[157]    {V3=Gladiator,                                                              
          V4=Green Mile}    => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[158]    {V2=LOTR,                                                                   
          V4=Green Mile}    => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[159]    {V1=Sixth Sense,                                                            
          V3=Gladiator}     => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[160]    {V1=Sixth Sense,                                                            
          V2=LOTR}          => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[161]    {V3=Gladiator,                                                              
          Green Mile=1}     => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[162]    {V2=LOTR,                                                                   
          Green Mile=1}     => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[163]    {V3=Gladiator,                                                              
          Patriot=0}        => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[164]    {V2=LOTR,                                                                   
          Patriot=0}        => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[165]    {V3=Gladiator,                                                              
          Sixth Sense=1}    => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[166]    {V2=LOTR,                                                                   
          Sixth Sense=1}    => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[167]    {V3=Gladiator,                                                              
          Gladiator=1}      => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[168]    {V2=LOTR,                                                                   
          Gladiator=1}      => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[169]    {V3=Gladiator,                                                              
          LOTR2=0}          => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[170]    {V2=LOTR,                                                                   
          LOTR2=0}          => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[171]    {V3=Gladiator,                                                              
          Harry Potter1=0}  => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[172]    {V2=LOTR,                                                                   
          Harry Potter1=0}  => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[173]    {V3=Gladiator,                                                              
          LOTR1=0}          => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[174]    {V2=LOTR,                                                                   
          LOTR1=0}          => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[175]    {V3=Gladiator,                                                              
          Braveheart=0}     => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[176]    {V2=LOTR,                                                                   
          Braveheart=0}     => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[177]    {V3=Gladiator,                                                              
          Harry Potter2=0}  => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[178]    {V2=LOTR,                                                                   
          Harry Potter2=0}  => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[179]    {V3=Gladiator,                                                              
          V4=Green Mile}    => {LOTR=1}               0.1  1.0000000 10.0000000     1
[180]    {V4=Green Mile,                                                             
          LOTR=1}           => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[181]    {V1=Sixth Sense,                                                            
          V3=Gladiator}     => {LOTR=1}               0.1  1.0000000 10.0000000     1
[182]    {V1=Sixth Sense,                                                            
          LOTR=1}           => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[183]    {V3=Gladiator,                                                              
          Green Mile=1}     => {LOTR=1}               0.1  1.0000000 10.0000000     1
[184]    {LOTR=1,                                                                    
          Green Mile=1}     => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[185]    {V3=Gladiator,                                                              
          Patriot=0}        => {LOTR=1}               0.1  1.0000000 10.0000000     1
[186]    {Patriot=0,                                                                 
          LOTR=1}           => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[187]    {V3=Gladiator,                                                              
          Sixth Sense=1}    => {LOTR=1}               0.1  1.0000000 10.0000000     1
[188]    {Sixth Sense=1,                                                             
          LOTR=1}           => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[189]    {V3=Gladiator,                                                              
          Gladiator=1}      => {LOTR=1}               0.1  1.0000000 10.0000000     1
[190]    {Gladiator=1,                                                               
          LOTR=1}           => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[191]    {V3=Gladiator,                                                              
          LOTR2=0}          => {LOTR=1}               0.1  1.0000000 10.0000000     1
[192]    {LOTR2=0,                                                                   
          LOTR=1}           => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[193]    {V3=Gladiator,                                                              
          Harry Potter1=0}  => {LOTR=1}               0.1  1.0000000 10.0000000     1
[194]    {Harry Potter1=0,                                                           
          LOTR=1}           => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[195]    {V3=Gladiator,                                                              
          LOTR1=0}          => {LOTR=1}               0.1  1.0000000 10.0000000     1
[196]    {LOTR1=0,                                                                   
          LOTR=1}           => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[197]    {V3=Gladiator,                                                              
          Braveheart=0}     => {LOTR=1}               0.1  1.0000000 10.0000000     1
[198]    {LOTR=1,                                                                    
          Braveheart=0}     => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[199]    {V3=Gladiator,                                                              
          Harry Potter2=0}  => {LOTR=1}               0.1  1.0000000 10.0000000     1
[200]    {Harry Potter2=0,                                                           
          LOTR=1}           => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[201]    {V4=Green Mile,                                                             
          Gladiator=1}      => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[202]    {V4=Green Mile,                                                             
          LOTR2=0}          => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[203]    {V4=Green Mile,                                                             
          Harry Potter1=0}  => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[204]    {V4=Green Mile,                                                             
          LOTR1=0}          => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[205]    {V1=Sixth Sense,                                                            
          Gladiator=1}      => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[206]    {V1=Sixth Sense,                                                            
          LOTR2=0}          => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[207]    {V1=Sixth Sense,                                                            
          Harry Potter1=0}  => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[208]    {V1=Sixth Sense,                                                            
          LOTR1=0}          => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[209]    {Gladiator=1,                                                               
          Green Mile=1}     => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[210]    {LOTR2=0,                                                                   
          Green Mile=1}     => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[211]    {Harry Potter1=0,                                                           
          Green Mile=1}     => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[212]    {LOTR1=0,                                                                   
          Green Mile=1}     => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[213]    {Gladiator=1,                                                               
          Patriot=0}        => {V3=Gladiator}         0.1  1.0000000 10.0000000     1
[214]    {V2=LOTR,                                                                   
          V4=Green Mile}    => {LOTR=1}               0.1  1.0000000 10.0000000     1
[215]    {V4=Green Mile,                                                             
          LOTR=1}           => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[216]    {V1=Sixth Sense,                                                            
          V2=LOTR}          => {LOTR=1}               0.1  1.0000000 10.0000000     1
[217]    {V1=Sixth Sense,                                                            
          LOTR=1}           => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[218]    {V2=LOTR,                                                                   
          Green Mile=1}     => {LOTR=1}               0.1  1.0000000 10.0000000     1
[219]    {LOTR=1,                                                                    
          Green Mile=1}     => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[220]    {V2=LOTR,                                                                   
          Patriot=0}        => {LOTR=1}               0.1  1.0000000 10.0000000     1
[221]    {Patriot=0,                                                                 
          LOTR=1}           => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[222]    {V2=LOTR,                                                                   
          Sixth Sense=1}    => {LOTR=1}               0.1  1.0000000 10.0000000     1
[223]    {Sixth Sense=1,                                                             
          LOTR=1}           => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[224]    {V2=LOTR,                                                                   
          Gladiator=1}      => {LOTR=1}               0.1  1.0000000 10.0000000     1
[225]    {Gladiator=1,                                                               
          LOTR=1}           => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[226]    {V2=LOTR,                                                                   
          LOTR2=0}          => {LOTR=1}               0.1  1.0000000 10.0000000     1
[227]    {LOTR2=0,                                                                   
          LOTR=1}           => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[228]    {V2=LOTR,                                                                   
          Harry Potter1=0}  => {LOTR=1}               0.1  1.0000000 10.0000000     1
[229]    {Harry Potter1=0,                                                           
          LOTR=1}           => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[230]    {V2=LOTR,                                                                   
          LOTR1=0}          => {LOTR=1}               0.1  1.0000000 10.0000000     1
[231]    {LOTR1=0,                                                                   
          LOTR=1}           => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[232]    {V2=LOTR,                                                                   
          Braveheart=0}     => {LOTR=1}               0.1  1.0000000 10.0000000     1
[233]    {LOTR=1,                                                                    
          Braveheart=0}     => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[234]    {V2=LOTR,                                                                   
          Harry Potter2=0}  => {LOTR=1}               0.1  1.0000000 10.0000000     1
[235]    {Harry Potter2=0,                                                           
          LOTR=1}           => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[236]    {V4=Green Mile,                                                             
          Gladiator=1}      => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[237]    {V4=Green Mile,                                                             
          LOTR2=0}          => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[238]    {V4=Green Mile,                                                             
          Harry Potter1=0}  => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[239]    {V4=Green Mile,                                                             
          LOTR1=0}          => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[240]    {V1=Sixth Sense,                                                            
          Gladiator=1}      => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[241]    {V1=Sixth Sense,                                                            
          LOTR2=0}          => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[242]    {V1=Sixth Sense,                                                            
          Harry Potter1=0}  => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[243]    {V1=Sixth Sense,                                                            
          LOTR1=0}          => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[244]    {Gladiator=1,                                                               
          Green Mile=1}     => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[245]    {LOTR2=0,                                                                   
          Green Mile=1}     => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[246]    {Harry Potter1=0,                                                           
          Green Mile=1}     => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[247]    {LOTR1=0,                                                                   
          Green Mile=1}     => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[248]    {Gladiator=1,                                                               
          Patriot=0}        => {V2=LOTR}              0.1  1.0000000 10.0000000     1
[249]    {V4=Green Mile,                                                             
          Gladiator=1}      => {LOTR=1}               0.1  1.0000000 10.0000000     1
[250]    {V4=Green Mile,                                                             
          LOTR2=0}          => {LOTR=1}               0.1  1.0000000 10.0000000     1
[251]    {V4=Green Mile,                                                             
          Harry Potter1=0}  => {LOTR=1}               0.1  1.0000000 10.0000000     1
[252]    {V4=Green Mile,                                                             
          LOTR1=0}          => {LOTR=1}               0.1  1.0000000 10.0000000     1
[253]    {V1=Sixth Sense,                                                            
          Gladiator=1}      => {LOTR=1}               0.1  1.0000000 10.0000000     1
[254]    {V1=Sixth Sense,                                                            
          LOTR2=0}          => {LOTR=1}               0.1  1.0000000 10.0000000     1
[255]    {V1=Sixth Sense,                                                            
          Harry Potter1=0}  => {LOTR=1}               0.1  1.0000000 10.0000000     1
[256]    {V1=Sixth Sense,                                                            
          LOTR1=0}          => {LOTR=1}               0.1  1.0000000 10.0000000     1
[257]    {Gladiator=1,                                                               
          Green Mile=1}     => {LOTR=1}               0.1  1.0000000 10.0000000     1
[258]    {LOTR2=0,                                                                   
          Green Mile=1}     => {LOTR=1}               0.1  1.0000000 10.0000000     1
[259]    {Harry Potter1=0,                                                           
          Green Mile=1}     => {LOTR=1}               0.1  1.0000000 10.0000000     1
[260]    {LOTR1=0,                                                                   
          Green Mile=1}     => {LOTR=1}               0.1  1.0000000 10.0000000     1
[261]    {Gladiator=1,                                                               
          Patriot=0}        => {LOTR=1}               0.1  1.0000000 10.0000000     1
[262]    {V2=LOTR1,                                                                  
          V3=Harry Potter1} => {V5=LOTR2}             0.1  1.0000000 10.0000000     1
[263]    {V2=LOTR1,                                                                  
          V5=LOTR2}         => {V3=Harry Potter1}     0.1  1.0000000 10.0000000     1



## head(quality(rules))
support confidence lift count
1     0.7        0.7    1     7
2     0.8        0.8    1     8
3     0.8        0.8    1     8
4     0.8        0.8    1     8
5     0.8        0.8    1     8
6     0.9        0.9    1     9



## plot(rules)
 



# For better visualizations we can use other methods to plot and we can do 
# that in a new window  


## windows()


 ## plot(rules,method = "grouped")


 








## plot(rules[1:20] , method = "graph")


 

# Thus ,  we can Association rules are formed , we can by :
# write(rules , file = " arulessol.csv" , sep="," )
 


# Clustering			                
## Assignment 1
 #### BP:  Perform clustering for the crime data and identify the number of clusters formed and draw inferences.


 ### PROCEDURE:

## STEP 1: First we have to Exploratory Data Analysis which can be done by plotting scattered plot, box plots and summary.

### summary(crime_data_1_)
      X1                Murder          Assault         UrbanPop    
 Length: 50          Min.   : 0.800   Min. :  45.0    Min.  :32.00  
 Class: character   1st Qu.: 4.075   1st Qu.:109.0   1st Qu.:54.50  
 Mode : character   Median : 7.250   Median :159.0   Median :66.00  
                    Mean   : 7.788   Mean   :170.8   Mean   :65.54  
                    3rd Qu.:11.250   3rd Qu.:249.0   3rd Qu.:77.75  
                    Max.   :17.400   Max.   :337.0   Max.   :91.00  
      Rape      
 Min.   : 7.30  
 1st Qu.:15.07  
 Median :20.10  
 Mean   :21.23  
 3rd Qu.:26.18  
 Max.   :46.00  


### From the summary we can see that in assault the difference between mean and max is large       so it may be right skewed it can my confirmed by using Box Plot .


 

 ### It can be confirmed that Assault is right Skewed.

Scatter Plot for the Following data frame is:


 


## STEP 2: Now we can observe from the summary that the data is not in similar scale so now we have to normalize the data into same scale which can be done as follows:

### normzalizeddata <- scale(crime_data_1_[,2:5])

### View(normzalizeddata)

 ### summary(normzalizeddata)

     Murder           Assault           UrbanPop             Rape        
 Min.   :-1.6044   Min.   :-1.5090   Min.   :-2.31714   Min.   :-1.4874  
 1st Qu.:-0.8525   1st Qu.:-0.7411   1st Qu.:-0.76271   1st Qu.:-0.6574  
 Median :-0.1235   Median :-0.1411   Median : 0.03178   Median :-0.1209  
 Mean   : 0.0000   Mean   : 0.0000   Mean   : 0.00000   Mean   : 0.0000  
 3rd Qu.: 0.7949   3rd Qu.: 0.9388   3rd Qu.: 0.84354   3rd Qu.: 0.5277  
 Max.   : 2.2069   Max.   : 1.9948   Max.   : 1.75892   Max.   : 2.6444 

### From the summary we can see that whole data is converted into Z Scale. 

## STEP 3: Now we have to measure the distance between the rows so that we can cluster so code is as follows:
 ### d <- dist(normzalizeddata,method = "euclidean")

  ### d

           1         2         3         4         5         6         7         8
2  2.7037541                                                                      
3  2.2935197 2.7006429                                                            
4  1.2898102 2.8260386 2.7177583                                                  
5  3.2631104 3.0125415 1.3104842 3.7636409                                        
6  2.6510673 2.3265187 1.3650307 2.8310512 1.2876185                              
7  3.2152975 4.7399125 3.2628575 2.6076395 4.0663898 3.3279920                    
8  2.0192927 3.6213633 1.9093696 1.8003239 3.0737852 2.5547456 1.7568475          
9  2.2981353 2.9967642 1.7493928 3.3721968 2.0250039 2.4458600 4.4700701 3.0614170
10 1.1314351 2.8194388 2.7871963 2.2117614 3.3780585 2.8649105 3.9738227 2.9838715
11 3.3885300 4.5301340 3.2621208 2.9723097 3.6589083 2.8233524 1.3843291 2.4748807
12 2.9146623 4.0580555 3.5210071 1.7687255 4.4879436 3.4767685 1.6354214 2.0382540
13 1.8734993 3.2670626 1.0825512 2.4626424 1.9117469 1.7898322 2.7400560 1.5584719
14 2.0761411 3.3655952 2.6407486 1.4450503 3.4061273 2.3655622 1.6147898 1.6973340
15 3.4878952 4.7251910 4.1157513 2.4252661 4.9708591 3.9406898 1.5470089 2.6068606
16 2.2941096 3.6808173 2.7762838 1.5718411 3.6071725 2.6272281 1.2280424 1.5510864
17 1.8475879 3.5440903 3.3567681 1.0598104 4.2463809 3.2274013 2.3346386 2.2514939
18 0.7722224 2.9631431 2.2178519 2.0254276 3.0176625 2.6546743 3.5329409 2.3266996
19 3.4851115 4.8322605 4.2961903 2.3621893 5.2699843 4.2713441 1.8792141 2.6560808
20 1.2896460 2.2777590 1.2117356 2.0582244 2.2312581 1.9667562 3.4968269 1.9624834
21 2.9874810 4.3729925 2.5162281 2.6881270 3.2156499 2.6522793 0.9468199 1.4382527
           9        10        11        12        13        14        15        16
2                                                                                 
3                                                                                 
4                                                                                 
5                                                                                 
6                                                                                 
7                                                                                 
8                                                                                 
9                                                                                 
10 2.1812958                                                                      
11 4.3596338 3.8105218                                                            
12 4.6999827 3.8005715 2.3658101                                                  
13 1.7711863 2.3135778 2.7329756 3.2728945                                        
14 3.6150778 2.6924143 1.5460727 1.4923351 2.2027081                              
15 5.2682765 4.2517889 2.1564575 0.8584962 3.7380070 1.7786548                    
16 3.8424558 3.0071474 1.4648766 1.2103118 2.3228505 0.4287712 1.4699265          
17 3.9474983 2.4408198 2.5203345 1.6565236 2.8478883 1.1790552 1.9426473 1.3020180
18 1.7529677 0.8592544 3.5687157 3.5283772 1.6535178 2.4957547 4.0359614 2.7284126
19 5.3946798 4.3334217 2.7160558 0.8486112 3.9342034 2.1029158 0.6457158 1.7913753
20 1.4355204 1.8388691 3.6148670 3.4014584 1.3429997 2.5430878 4.0642448 2.7400943
21 3.7753087 3.6706708 1.3276676 2.2201020 2.0080982 1.6615695 2.3510287 1.4343401
          17        18        19        20        21        22        23        24
2                                                                                 
3                                                                                 
4                                                                                 
5                                                                                 
6                                                                                 
7                                                                                 
8                                                                                 
9                                                                                 
10                                                                                
11                                                                                
12                                                                                
13                                                                                
14                                                                                
15                                                                                
16                                                                                
17                                                                                
18 2.4221964                                                                      
19 1.9925855 4.0901924                                                            
20 2.8229479 1.2739137 4.1259083                                                  
21 2.6284451 3.1524549 2.6920282 2.9743193                                        
          25        26        27        28        29        30        31        32
2                                                                                 
3                                                                                 
4                                                                                 
5                                                                                 
6                                                                                 
7                                                                                 
8                                                                                 
9                                                                                 
10                                                                                
11                                                                                
12                                                                                
13                                                                                
14                                                                                
15                                                                                
16                                                                                
17                                                                                
18                                                                                
19                                                                                
20                                                                                
21                                                                                
          33        34        35        36        37        38        39        40
2                                                                                 
3                                                                                 
4                                                                                 
5                                                                                 
6                                                                                 
7                                                                                 
8                                                                                 
9                                                                                 
10                                                                                
11                                                                                
12                                                                                
13                                                                                
14                                                                                
15                                                                                
16                                                                                
17                                                                                
18                                                                                
19                                                                                
20                                                                                
21                                                                                
          41        42        43        44        45        46        47        48
2                                                                                 
3                                                                                 
4                                                                                 
5                                                                                 
6                                                                                 
7                                                                                 
8                                                                                 
9                                                                                 
10                                                                                
11                                                                                
12                                                                                
13                                                                                
14                                                                                
15                                                                                
16                                                                                
17                                                                                
18                                                                                
19                                                                                
20                                                                                
21                                                                                
          49
2           
3           
4           
5           
6           
7           
8           
9           
10          
11          
12          
13          
14          
15          
16          
17          
18          
19          
20          
21          


 ## STEP 4: After the distance matrix is formed now we have to cluster it now:
### cluster <- hclust(d,method = "complete")
### > plot(cluster)
### > plot(cluster,hang = -1)

 


 

## STEP 5: Now after the Dendrogram is formed we can cut them into number of clusters which is suitable according to the data set :

### groups <- cutree(cluster , k=10)

### > groups

 1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 
 1  2  3  4  5  5  6  7  3  1  6  8  3  6  8  6  4  1  8  3  7  3  6  9  4  8  8  5 
29 30 31 32 33 34 35 36 37 38 39 40 41 42 43 44 45 46 47 48 49 50 
 8  7  3  3  9 10  6  6  4  6  7  9 10  1  3  6 10  4  4 10  6  4 


### Now there are 10 groups which are formed from the 50 entries of the data set.





 ### To visualize the groups we use:
### rect.hclust(cluster, k=10 , border = "red") 
### Now the groups are converted into column format :
### clusters <- as.matrix(groups)

### > clusters

   [,1]

1     1
2     2
3     3
4     4
5     5
6     5
7     6
8     7
9     3
10    1
11    6
12    8
13    3
14    6
15    8
16    6
17    4
18    1
19    8
20    3
21    7
22    3
23    6
24    9
25    4
26    8
27    8
28    5
29    8
30    7
31    3
32    3
33    9
34   10
35    6
36    6
37    4
38    6
39    7
40    9
41   10
42    1
43    3
44    6
45   10
46    4
47    4
48   10
49    6
50    4



### Now , for comparison of the final clusters we use the following code :
### aggregate(crime_data_1_[,2:5] , by=list(final$clusters) , FUN=mean)


      Group    Murder    Assault        UrbanPop      Rape
1        1   14.800000   221.00000    60.75000 	24.02500
2        2   10.000000   263.00000    48.00000 	44.50000
3        3   11.562500   271.62500    77.50000 	29.18750
4        4    7.385714   156.85714    62.14286 	22.25714
5        5   9.700000    244.00000    83.33333 	41.76667
6        6   5.050000    100.60000    71.80000 	17.52000
7        7   5.275000    180.00000    83.25000 	14.80000
8        8   3.216667    87.83333     55.50000 	12.61667
9        9   14.500000   291.66667    45.66667 	18.56667
10      10   3.125000    65.00000     40.00000 	10.15000


### Now we can see that clusters have been formed:
### It can be inferred that group1 consists of max amount of murder %  and group 10 consists of min murder % and so on .





 # Clustering			                
# Assignment 1
## BP:  Perform clustering for the crime data and identify the number of clusters formed and draw inferences.


# PROCEDURE:

## STEP 1: First we have to Exploratory Data Analysis which can be done by plotting scattered plot, box plots and summary.
ID#          Balance               Qual_miles        cc1_miles      cc2_miles    
 Min.   :   1   Min.   :      0   Min.   :    0.0   Min.   :1.00   Min.   :1.000  
 1st Qu.:1010   1st Qu.:  18528   1st Qu.:    0.0   1st Qu.:1.00   1st Qu.:1.000  
 Median :2016   Median :  43097   Median :    0.0   Median :1.00   Median :1.000  
 Mean   :2015   Mean   :  73601   Mean   :  144.1   Mean   :2.06   Mean   :1.015  
 3rd Qu.:3020   3rd Qu.:  92404   3rd Qu.:    0.0   3rd Qu.:3.00   3rd Qu.:1.000  
 Max.   :4021   Max.   :1704838   Max.   :11148.0   Max.   :5.00   Max.   :3.000  

   cc3_miles      Bonus_miles      Bonus_trans   Flight_miles_12mo  Flight_trans_12 
 Min.   :1.000   Min.   :     0   Min.   : 0.0   Min.   :    0.0    Min.   : 0.000  
 1st Qu.:1.000   1st Qu.:  1250   1st Qu.: 3.0   1st Qu.:    0.0    1st Qu.: 0.000  
 Median :1.000   Median :  7171   Median :12.0   Median :    0.0    Median : 0.000  
 Mean   :1.012   Mean   : 17145   Mean   :11.6   Mean   :  460.1    Mean   : 1.374  
 3rd Qu.:1.000   3rd Qu.: 23801   3rd Qu.:17.0   3rd Qu.:  311.0    3rd Qu.: 1.000  
 Max.   :5.000   Max.   :263685   Max.   :86.0   Max.   :30817.0    Max.   :53.000  
 Days_since_enroll     Award?      
 Min.   :   2        Min.   :0.0000  
 1st Qu.:2330       1st Qu.:0.0000  
 Median :4096       Median :0.0000  
 Mean   :4119       Mean   :0.3703  
 3rd Qu.:5790       3rd Qu.:1.0000  
 Max.   :8296       Max.   :1.0000  




### From the summary we can see that in balance it is left skewed and, bonus miles flight_miles_12mo  the difference between mean and max is large       so it may be right skewed it can my confirmed by using Box Plot .


 

### It can be confirmed that Assault is right Skewed.

Scatter Plot for the Following data frame is:



 

## STEP 2: Now we can observe from the summary that the data is not in similar scale so now we have to normalize the data into same scale which can be done as follows:

### normzalizeddata <- scale(crime_data_1_[,2:5])

 ### View(normzalizeddata)

 ### summary(normzalizeddata)

     ID#               Balance          Qual_miles        cc1_miles      
 Min.   :-1.734908   Min.   :-0.7303   Min.   :-0.1863   Min.   :-0.7695  
 1st Qu.:-0.865223   1st Qu.:-0.5465   1st Qu.:-0.1863   1st Qu.:-0.7695  
 Median : 0.001017   Median :-0.3027   Median :-0.1863   Median :-0.7695  
 Mean   : 0.000000   Mean   : 0.0000   Mean   : 0.0000   Mean   : 0.0000  
 3rd Qu.: 0.866395   3rd Qu.: 0.1866   3rd Qu.:-0.1863   3rd Qu.: 0.6830  
 Max.   : 1.728327   Max.   :16.1868   Max.   :14.2231   Max.   : 2.1356  
   cc2_miles          cc3_miles         Bonus_miles       Bonus_trans      
 Min.   :-0.09823   Min.   :-0.06276   Min.   :-0.7099   Min.   :-1.20805  
 1st Qu.:-0.09823   1st Qu.:-0.06276   1st Qu.:-0.6581   1st Qu.:-0.89568  
 Median :-0.09823   Median :-0.06276   Median :-0.4130   Median : 0.04145  
 Mean   : 0.00000   Mean   : 0.00000   Mean   : 0.0000   Mean   : 0.00000  
 3rd Qu.:-0.09823   3rd Qu.:-0.06276   3rd Qu.: 0.2756   3rd Qu.: 0.56208  
 Max.   :13.44729   Max.   :20.42477   Max.   :10.2083   Max.   : 7.74673  
 Flight_miles_12mo Flight_trans_12    Days_since_enroll      Award?       
 Min.   :-0.3286   Min.   :-0.36212   Min.   :-1.99336   Min.   :-0.7668  
 1st Qu.:-0.3286   1st Qu.:-0.36212   1st Qu.:-0.86607   1st Qu.:-0.7668  
 Median :-0.3286   Median :-0.36212   Median :-0.01092   Median :-0.7668  
 Mean   : 0.0000   Mean   : 0.00000   Mean   : 0.00000   Mean   : 0.0000  
 3rd Qu.:-0.1065   3rd Qu.:-0.09849   3rd Qu.: 0.80960   3rd Qu.: 1.3038  
 Max.   :21.6803   Max.   :13.61035   Max.   : 2.02284   Max.   : 1.3038  

### From the summary we can see that whole data is converted into Z Scale. 

## STEP 3: Now we have to measure the distance between the rows so that we can cluster so code is as follows:
## d <- dist(normzalizeddata,method = "euclidean")

 ## d


## STEP 4: After the distance matrix is formed now we have to cluster it now:
### cluster <- hclust(d,method = "complete")
### > plot(cluster)
### > plot(cluster,hang = -1)

 




## STEP 5: Now after the Dendrogram is formed we can cut them into number of clusters which is suitable according to the data set :
### Due to huge data set frame the dendrogram is unclear due to huge number of clusters.

 
### groups <- cutree(cluster , k=10)

### > groups

[1] 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
  [40] 1 1 1 3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 3 1 1 1 1 1 1 1 1 1 1 1 1
  [79] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 3 1 1 1 1 1 1 1 1 1 1 1 4 1 1 1 1 1 3 1 1 1 1
 [118] 5 1 1 1 3 1 1 1 1 6 3 1 1 1 1 1 1 1 3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 6 1 1 1 1
 [157] 1 1 1 1 1 1 1 1 1 1 1 6 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 3 1 1 1 6 3 6 1 1
 [196] 1 1 1 2 1 1 3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 5 1 1 1 1 1 2 1 1 1 1 1 1 1
 [235] 1 1 1 1 3 1 1 1 1 3 6 3 1 1 1 1 1 1 1 1 1 1 1 1 1 6 1 1 1 1 1 1 1 1 1 1 1 1 1
 [274] 1 1 5 1 1 1 1 1 1 1 1 1 1 1 1 1 1 6 1 1 1 1 1 1 1 3 1 1 1 1 1 1 1 1 1 1 1 1 1
 [313] 1 6 1 1 1 1 5 1 1 1 1 7 1 1 1 3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [352] 1 1 1 1 1 1 1 1 1 3 1 1 1 1 1 1 1 1 1 1 3 1 1 1 3 1 1 1 1 6 2 1 1 4 1 1 1 1 1
 [391] 1 1 2 1 1 1 1 1 1 1 1 1 1 1 3 1 1 1 1 1 3 1 3 1 1 1 1 1 1 1 8 1 1 1 1 1 1 6 1
 [430] 1 1 1 1 1 1 1 1 6 1 1 1 1 1 1 3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 6 5 6
 [469] 1 1 1 5 1 1 1 3 1 1 1 1 1 5 1 1 1 1 1 1 5 1 1 1 3 1 1 1 1 1 1 1 3 1 1 1 1 1 1
 [508] 1 1 1 6 3 1 1 1 1 1 3 1 3 1 1 1 1 1 1 1 1 1 1 1 3 1 1 6 1 1 1 1 1 1 1 1 1 1 1
 [547] 1 1 1 3 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [586] 1 1 1 1 8 1 1 1 1 3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 3 1 1 1 1 1 1 1 1 1 1 7 1
 [625] 1 1 1 1 1 5 3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 3
 [664] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [703] 3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [742] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [781] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [820] 1 1 1 1 5 1 1 1 1 1 1 1 1 1 8 1 1 1 1 1 3 1 1 1 1 1 1 1 1 1 1 9 3 1 1 1 1 1 1
 [859] 1 1 3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 8
 [898] 1 1 1 1 8 1 1 9 1 1 1 1 1 1 1 1 1 3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [937] 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 7 1 1 1 1 1 1 1 3 1 1 1 1 1 1 1 1
 [976] 1 3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1


## Now there are 10 groups which are formed from the  entries of the data set.





##  To visualize the groups we use:
### rect.hclust(cluster, k=10 , border = "red")
 





## Now the groups are converted into column format :
### clusters <- as.matrix(groups)





### Now , for comparison of the final clusters we use the following code :
### aggregate(crime_data_1_[,2:5] , by=list(final$clusters) , FUN=mean)

Group.1       ID#    Balance Qual_miles cc1_miles cc2_miles cc3_miles
1        1 2040.9579   65933.05  107.19427  2.033386  1.000000  1.000789
2        2 2269.3721   68876.58   23.25581  1.139535  2.348837  1.000000
3        3 1188.4133  154470.67  343.88000  2.786667  1.000000  1.000000
4        4 1549.1000  171035.50  118.20000  3.600000  1.000000  3.600000
5        5  556.0833 1001289.83  808.83333  2.416667  1.000000  1.000000
6        6 1033.0000  479273.43   44.52174  4.782609  1.000000  1.000000
7        7 1973.5455  170277.82 1121.54545  1.636364  1.000000  1.000000
8        8 1713.7857  127093.71 8294.21429  2.071429  1.000000  1.000000
9        9 1896.4000   72113.20    0.00000  3.200000  1.000000  5.000000
10      10 2819.0000  106673.00  694.00000  2.500000  1.000000  1.000000
 Bonus_miles Bonus_trans Flight_miles_12mo Flight_trans_12 Days_since_enroll
1     15515.16    10.85174          305.3410       0.8995794          4065.016
2     14689.84    17.53488          582.6279       2.2093023          3968.930
3     42403.01    32.94667         5220.1733      17.7200000          5624.973
4     79268.70    30.60000          650.0000       2.1000000          4891.600
5     28693.75    16.75000         1624.4167       7.0000000          7150.500
6    141124.09    23.73913         1200.6522       3.3043478          6224.565
7     29527.73    34.63636        12223.6364      27.8181818          4116.545
8     18153.21    13.64286         1399.6429       4.2142857          4685.429
9    123246.20    23.00000          220.0000       0.6000000          4058.400
10    76325.00    75.50000        26458.5000      49.0000000          2602.000
      Award?
1  0.3509464
2  0.3953488
3  0.8533333
4  0.4000000
5  0.9166667
6  1.0000000
7  1.0000000
8  0.7142857
9  0.8000000
10 1.0000000


### Now we can see that clusters have been formed:
### It can be inferred that group1 consists of least balance   and group 5 has highest balance and so on.




## Clustering
###  K –means 			                
###  Assignment 1
##  BP: Analyse the information given in the following ‘Insurance Policy dataset’ to create clusters of persons falling in the same type.


## PROCEDURE:

## STEP 1: First we have to Exploratory Data Analysis which can be done by plotting scattered plot, box plots and summary.

###  summary(Insurance_Dataset)
Premiums Paid        Age                Days to Renew            Claims made        Income      
 Min.   : 2800       Min.   :23.00     Min.   :  1.0  		Min.   : 1978       Min.   : 28000  
 1st Qu.: 6975      1st Qu.:34.00    1st Qu.: 56.0   	1st Qu.: 5221     1st Qu.: 65125  
 Median :11825   Median :45.00   Median : 89.0   	Median : 8386    Median :102250  
 Mean   :12542     Mean   :46.11    Mean   :120.4   	Mean   :12579    Mean   :102250  
 3rd Qu.:15475    3rd Qu.:54.50    3rd Qu.:186.5   	3rd Qu.:14671    3rd Qu.:139375  
 Max.   :29900     Max.   :82.00   Max.   :321.0   	Max.   :99677    Max.   :176500 


###  From the summary we can see that in column claims made the difference between mean and max is large so it may be right skewed it can my confirmed by using Box Plot .

 



Scatter Plot for the Following data frame is:


 


## STEP 2: To determine the value of k, we have to do code for elbow curve :

for (i in 1:5) { wss <- c(wss,kmeans(nd,centers=i)$tot.withins)

}
> wss

[1] 495.0000 313.9598 246.8452 201.2060 159.9849

###  > plot(wss, type = "b" , xlab ="number of clusters", ylab = "within groups sum of squares")

###  > title(sub = " K-means clustering scree plot")
 
  
         
 ### From the elbow curve we can assume that we can form 2 clusters , to confirm our assumption we can use the auto selection of k by code :
###  k <- kselection(Insurance_Dataset , parallel = TRUE , max_centers=12)

###  > k

###  f(k) finds 2 clusters

###  Thus we can conclude that we can form 2 clusters . 




##  STEP 3:  Now we have to cluster it now:

###  clust <- kmeans(nd,2)

###  > str(clust)

List of 9
 $ cluster     : int [1:100] 2 2 2 2 2 2 2 2 2 2 ...
 $ centers     : num [1:2, 1:5] 1.307 -0.436 1.072 -0.357 0.602 ...
  ..- attr(*, "dimnames")=List of 2
  .. ..$ : chr [1:2] "1" "2"
  .. ..$ : chr [1:5] "Premiums Paid" "Age" "Days to Renew" "Claims made" ...
 $ totss       : num 495
 $ withinss    : num [1:2] 121 193
 $ tot.withinss: num 314
 $ betweenss   : num 181
 $ size        : int [1:2] 25 75
 $ iter        : int 1
 $ ifault      : int 0
 - attr(*, "class")= chr "kmeans"


###  > clust$centers


  Premiums Paid        Age Days to Renew Claims made     Income
1     1.3070388  1.0721764     0.6018913   1.1064252  0.9933994
2    -0.4356796 -0.3573921    -0.2006304  -0.3688084 -0.3311331

###  > clust$cluster
  [1] 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 1 1 1 2 2 2
 [40] 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 1 1 2 2 2 2 2 2 2 2 2 1 2 2 1 2 2 2 2 2 2
 [79] 1 2 1 1 2 1 1 1 1 1 1 1 1 2 1 2 1 1 1 1 1 1

###  > final <- data.frame(clust$cluster , Insurance_Dataset)

### > View(final)

### > final
    clust.cluster Premiums.Paid Age Days.to.Renew Claims.made Income
1               2          2800  26           233    3890.076  28000
2               2          2950  27           130    2294.444  29500
3               2          3100  28           144    2564.545  31000
4               2          3250  30            65    1978.261  32500
5               2          3400  32            56    2009.091  34000
6               2          3550  35            89    2349.455  35500
7               2          3700  44            95    2503.346  37000
8               2          3850  45            48    2217.405  38500
9               2          4000  46            76    2527.778  40000
10              2          6225  56           200    6908.232  41500
11              2          6450  67           211    7672.549  43000
12              2          6675  69           245   10208.824  44500
13              2          6900  70           261   12192.233  46000
14              2          4750  34           278   10052.326  47500
15              2          4900  44           182    4900.000  49000
16              2          7575  45            60    4535.033  50500
17              2          5200  23            12    2688.636  52000
18              2          8025  53             2    4034.669  53500
19              2          5500  48             1    2757.576  55000
20              2          5650  49            14    2938.000  56500
21              2          5800  41            17    3042.075  58000
22              2          5950  42            65    3621.739  59500
23              2          9150  50            56    5406.818  61000
24              2          6250  26            89    4136.364  62500
25              2          6400  27            95    4330.112  64000
26              2          6550  28            48    3772.468  65500
27              2          6700  30            76    4234.028  67000
28              2          6850  32            39    3836.000  68500
29              2          7000  35            34    3860.606  70000
30              2          7150  44            57    4238.762  71500
31              2          7300  45            85    4762.007  73000
32              2          7450  46           165    6813.568  74500
33              2         11400  56           234   15960.000  76000
34              1         11625  67           256   19590.278  77500
35              1         11850  69           233   16463.359  79000
36              1         12075  70           321   51108.140  80500
37              2          8200  34           233   11392.366  82000
38              2         12525  44           130    9741.667  83500
39              2         12750  45           144   10547.727  85000
40              2         12975  23            65    7897.826  86500
41              2         13200  53            56    7800.000  88000
42              2          8950  48            89    5923.273  89500
43              2          9100  49            95    6156.877  91000
44              2          9250  41            48    5327.532  92500
45              2          9400  42            76    5940.278  94000
46              2         14325  50           123   10818.050  95500
47              2          9700  26           156    8487.500  97000
48              2          9850  27           245   15064.706  98500
49              2         10000  28           261   17669.903 100000
50              2         10150  30           278   21480.233 101500
51              2         10300  32           182   10300.000 103000
52              2         10450  35            60    6256.250 104500
53              2         10600  44            12    5480.682 106000
54              2         10750  45             2    5404.696 107500
55              2         10900  46             1    5465.014 109000
56              2         16575  56            14    8619.000 110500
57              2         16800  67            17    8811.527 112000
58              1         17025  69            65   10363.043 113500
59              1         23000  70            56   13590.909 115000
60              2         11650  34            89    7710.182 116500
61              2         11800  44            95    7983.643 118000
62              2         11950  45            48    6882.595 119500
63              2         12100  23            76    7646.528 121000
64              2         18375  53            39   10290.000 122500
65              2         12400  48            34    6838.788 124000
66              2         12550  49            57    7440.065 125500
67              2         12700  41            85    8284.588 127000
68              2         12850  42           165   11752.261 128500
69              1         19500  50           234   27300.000 130000
70              2         13150  32           256   22160.185 131500
71              2         13300  34           233   18477.863 133000
72              1         13450  36           321   56927.907 134500
73              2         13600  39            65    8278.261 136000
74              2         13750  42            56    8125.000 137500
75              2         13900  44            89    9199.273 139000
76              2         14050  45            95    9505.948 140500
77              2         14200  48            48    8178.481 142000
78              2         14350  49            76    9068.403 143500
79              1         21750  54            39   12180.000 145000
80              2         14650  32            34    8079.697 146500
81              1         29600  77            57   17547.883 148000
82              1         29900  82            85   19504.660 149500
83              2         15100  34           165   13810.050 151000
84              1         15250  56           234   21350.000 152500
85              1         23100  63           256   38927.778 154000
86              1         23325  62           233   32405.725 155500
87              1         23550  59           321   99676.744 157000
88              1         23775  58           233   33030.916 158500
89              1         24000  52           130   18666.667 160000
90              1         16150  45           144   13360.455 161500
91              1         24450  54            65   14882.609 163000
92              2         16450  36            56    9720.455 164500
93              1         16600  82            89   10986.182 166000
94              2         16750  34            95   11332.714 167500
95              1         25350  56            48   14600.316 169000
96              1         25575  63            76   16161.979 170500
97              1         25800  62           166   23715.152 172000
98              1         26025  59           167   24043.401 173500
99              1         26250  58           245   40147.059 175000
100             1         26475  52           261   46781.068 176500

## STEP 4: Now we can visualize the clusters in graphical form by:

### km <- kmeans.ani(nd,2)
 

### Therefore, out of 100 rows from the data frame with k clustering method we have formed them into two clusters. 
### The inferences which we can make from this is that cluster 1 consists of the people who have premiums paid , age and the ### claims made are on the higher side whereas in cluster 2   comparatively these factors are relatively low.




## Clustering	
### K means		                
### Assignment 2
### BP:  Perform clustering for the crime data and identify the number of clusters formed and draw inferences.


## PROCEDURE:

## STEP 1: First we have to Exploratory Data Analysis which can be done by plotting scattered plot, box plots and summary.

### summary(crime_data_1_)
      X1                Murder          Assault         UrbanPop    
 Length: 50          Min.   : 0.800   Min. :  45.0    Min.  :32.00  
 Class: character   1st Qu.: 4.075   1st Qu.:109.0   1st Qu.:54.50  
 Mode : character   Median : 7.250   Median :159.0   Median :66.00  
                    Mean   : 7.788   Mean   :170.8   Mean   :65.54  
                    3rd Qu.:11.250   3rd Qu.:249.0   3rd Qu.:77.75  
                    Max.   :17.400   Max.   :337.0   Max.   :91.00  
      Rape      
 Min.   : 7.30  
 1st Qu.:15.07  
 Median :20.10  
 Mean   :21.23  
 3rd Qu.:26.18  
 Max.   :46.00  


### From the summary we can see that in assault the difference between mean and max is large       so it may be right skewed it can my confirmed by using Box Plot .


 

### It can be confirmed that Assault is right Skewed.

Scatter Plot for the Following data frame is:


 


## STEP 2: Now we can observe from the summary that the data is not in similar scale so now we have to normalize the data into same scale which can be done as follows:

 ### normzalizeddata <- scale(crime_data_1_[,2:5])

 ### View(normzalizeddata)

 ### summary(normzalizeddata)

     Murder           Assault           UrbanPop             Rape        
 Min.   :-1.6044   Min.   :-1.5090   Min.   :-2.31714   Min.   :-1.4874  
 1st Qu.:-0.8525   1st Qu.:-0.7411   1st Qu.:-0.76271   1st Qu.:-0.6574  
 Median :-0.1235   Median :-0.1411   Median : 0.03178   Median :-0.1209  
 Mean   : 0.0000   Mean   : 0.0000   Mean   : 0.00000   Mean   : 0.0000  
 3rd Qu.: 0.7949   3rd Qu.: 0.9388   3rd Qu.: 0.84354   3rd Qu.: 0.5277  
 Max.   : 2.2069   Max.   : 1.9948   Max.   : 1.75892   Max.   : 2.6444 

### From the summary we can see that whole data is converted into Z Scale. 




## STEP 3: To determine the value of k, we have to do code for elbow curve :

for (i in 1:5) { wss <- c(wss,kmeans(nd,centers=i)$tot.withins)

}
> wss

[1] 102.86240  81.59329  56.40317  51.42912

### > plot(wss, type = "b" , xlab ="number of clusters", ylab = "within groups sum of squares")


   
         
### From the elbow curve we can assume that we can form 2 clusters, to confirm our assumption we can use the auto selection of k by code :
### k <- kselection(crime_data_1_[,2:5] , parallel = TRUE , max_centers=12)

### > k

### f(k) finds 2 clusters



### Thus we can conclude that we can form 2 clusters. 




## STEP 3:  Now we have to cluster it now:

### clust <- kmeans(nd,2)

### > str(clust)

List of 9
 $ cluster     : int [1:50] 1 1 1 2 1 1 2 2 1 1 ...
 $ centers     : num [1:2, 1:4] 1.005 -0.67 1.014 -0.676 0.198 ...
  ..- attr(*, "dimnames")=List of 2
  .. ..$ : chr [1:2] "1" "2"
  .. ..$ : chr [1:4] "Murder" "Assault" "UrbanPop" "Rape"
 $ totss       : num 196
 $ withinss    : num [1:2] 46.7 56.1
 $ tot.withinss: num 103
 $ betweenss   : num 93.1
 $ size        : int [1:2] 20 30
 $ iter        : int 1
 $ ifault      : int 0
 - attr(*, "class")= chr "kmeans"

### > clust$centers


     Murder    Assault   UrbanPop       Rape
1  1.004934  1.0138274  0.1975853  0.8469650
2 -0.669956 -0.6758849 -0.1317235 -0.5646433

 ### > clust$cluster

[1] 1 1 1 2 1 1 2 2 1 1 2 2 1 2 2 2 2 1 2 1 2 1 2 1 1 2 2 1 2 2 1 1 1 2 2 2 2 2 2 1
[41] 2 1 1 2 2 2 2 2 2 2

### final <- data.frame(clust$cluster , crime_data_1_)


### > View(final)

### > final

  clust.cluster             X1 Murder Assault   UrbanPop 	Rape
1              1        Alabama   13.2     236       58 	21.2
2              1         Alaska   10.0     263       48  	44.5
3              1        Arizona    8.1     294       80  	31.0
4              2       Arkansas    8.8     190       50 	19.5
5              1     California    9.0     276       91 	40.6
6              1       Colorado    7.9     204       78 	38.7
7              2    Connecticut    3.3     110       77 	11.1
8              2       Delaware    5.9     238       72 	15.8
9              1        Florida   15.4     335       80 	31.9
10             1        Georgia   17.4     211       60 	25.8
11             2         Hawaii    5.3      46       83 	20.2
12             2          Idaho    2.6     120       54 	14.2
13             1       Illinois   10.4     249       83 	24.0
14             2        Indiana    7.2     113       65 	21.0
15             2           Iowa    2.2      56       57 	11.3
16             2         Kansas    6.0     115       66 18.0
17             2       Kentucky    9.7     109       52 16.3
18             1      Louisiana   15.4     249       66 22.2
19             2          Maine    2.1      83       51  7.8
20             1       Maryland   11.3     300       67 27.8
21             2  Massachusetts    4.4     149       85 16.3
22             1       Michigan   12.1     255       74 35.1
23             2      Minnesota    2.7      72       66 14.9
24             1    Mississippi   16.1     259       44 17.1
25             1       Missouri    9.0     178       70 28.2
26             2        Montana    6.0     109       53 16.4
27             2       Nebraska    4.3     102       62 16.5
28             1         Nevada   12.2     252       81 46.0
29             2  New Hampshire    2.1      57       56  9.5
30             2     New Jersey    7.4     159       89 18.8
31             1     New Mexico   11.4     285       70 32.1
32             1       New York   11.1     254       86 26.1
33             1 North Carolina   13.0     337       45 16.1
34             2   North Dakota    0.8      45       44  7.3
35             2           Ohio    7.3     120       75 21.4
36             2       Oklahoma    6.6     151       68 20.0
37             2         Oregon    4.9     159       67 29.3
38             2   Pennsylvania    6.3     106       72 14.9
39             2   Rhode Island    3.4     174       87  8.3
40             1 South Carolina   14.4     279       48 22.5
41             2   South Dakota    3.8      86       45 12.8
42             1      Tennessee   13.2     188       59 26.9
43             1          Texas   12.7     201       80 25.5
44             2           Utah    3.2     120       80 22.9
45             2        Vermont    2.2      48       32 11.2
46             2       Virginia    8.5     156       63 20.7
47             2     Washington    4.0     145       73 26.2
48             2  West Virginia    5.7      81       39  9.3
49             2      Wisconsin    2.6      53       66 10.8
50             2        Wyoming    6.8     161       60 15.6


## STEP 4: Now we can visualize the clusters in graphical form by:

### km <- kmeans.ani(nd,2)





 


### Therefore, out of 50 observations from the data frame with k clustering method we have formed them into two clusters. 
### The inferences which we can make from this is that cluster 1 consists of high murder rate and assault compared to that of ### cluster 2 whereas rape and urban pop is evenly distributed. 


## PCA	
		                
###  Assignment 1
###  BP:  Perform Principal component analysis and perform clustering using first 
### 3 principal component scores (both heirarchial and k mean clustering(scree plot or elbow curve) and obtain 
###  optimum number of clusters and check whether we have obtained same number of clusters with the original data 
###  (class column we have ignored at the begining who shows it has 3 clusters)df


## PROCEDURE:

## STEP 1: First we have to Exploratory Data Analysis which can be done by plotting scattered plot, box plots and summary.

###  summary(crime_data_1_)
  Type          Alcohol          Malic            Ash          Alcalinity   
 Min.   :1.000   Min.   :11.03   Min.   :0.740   Min.   :1.360   Min.   :10.60  
 1st Qu.:1.000   1st Qu.:12.36   1st Qu.:1.603   1st Qu.:2.210   1st Qu.:17.20  
 Median :2.000   Median :13.05   Median :1.865   Median :2.360   Median :19.50  
 Mean   :1.938   Mean   :13.00   Mean   :2.336   Mean   :2.367   Mean   :19.49  
 3rd Qu.:3.000   3rd Qu.:13.68   3rd Qu.:3.083   3rd Qu.:2.558   3rd Qu.:21.50  
 Max.   :3.000   Max.   :14.83   Max.   :5.800   Max.   :3.230   Max.   :30.00  
   Magnesium         Phenols        Flavanoids    Nonflavanoids    Proanthocyanins
 Min.   : 70.00   Min.   :0.980   Min.   :0.340   Min.   :0.1300   Min.   :0.410  
 1st Qu.: 88.00   1st Qu.:1.742   1st Qu.:1.205   1st Qu.:0.2700   1st Qu.:1.250  
 Median : 98.00   Median :2.355   Median :2.135   Median :0.3400   Median :1.555  
 Mean   : 99.74   Mean   :2.295   Mean   :2.029   Mean   :0.3619   Mean   :1.591  
 3rd Qu.:107.00   3rd Qu.:2.800   3rd Qu.:2.875   3rd Qu.:0.4375   3rd Qu.:1.950  
 Max.   :162.00   Max.   :3.880   Max.   :5.080   Max.   :0.6600   Max.   :3.580  
     Color             Hue            Dilution        Proline      
 Min.   : 1.280   Min.   :0.4800   Min.   :1.270   Min.   : 278.0  
 1st Qu.: 3.220   1st Qu.:0.7825   1st Qu.:1.938   1st Qu.: 500.5  
 Median : 4.690   Median :0.9650   Median :2.780   Median : 673.5  
 Mean   : 5.058   Mean   :0.9574   Mean   :2.612   Mean   : 746.9  
 3rd Qu.: 6.200   3rd Qu.:1.1200   3rd Qu.:3.170   3rd Qu.: 985.0  
 Max.   :13.000   Max.   :1.7100   Max.   :4.000   Max.   :1680.0

### From the summary we can see that in Proline the difference between mean and max is large       so it may be right skewed it can my confirmed by using Box Plot .




### It can be confirmed that Assault is right Skewed.
 
### Scatter Plot for the Following data frame is:


 








## STEP 2 : Now forming the clusters using PCA:

### On finding the correlation of the data we get :
     		 Alcohol       Malic          Ash  Alcalinity   Magnesium
Alcohol          1.00000000  0.09439694  0.211544596 -0.31023514  0.27079823
Malic            0.09439694  1.00000000  0.164045470  0.28850040 -0.05457510
Ash              0.21154460  0.16404547  1.000000000  0.44336719  0.28658669
Alcalinity      -0.31023514  0.28850040  0.443367187  1.00000000 -0.08333309
Magnesium        0.27079823 -0.05457510  0.286586691 -0.08333309  1.00000000
Phenols          0.28910112 -0.33516700  0.128979538 -0.32111332  0.21440123
Flavanoids       0.23681493 -0.41100659  0.115077279 -0.35136986  0.19578377
Nonflavanoids   -0.15592947  0.29297713  0.186230446  0.36192172 -0.25629405
Proanthocyanins  0.13669791 -0.22074619  0.009651935 -0.19732684  0.23644061
Color            0.54636420  0.24898534  0.258887259  0.01873198  0.19995001
Hue             -0.07174720 -0.56129569 -0.074666889 -0.27395522  0.05539820
Dilution         0.07234319 -0.36871043  0.003911231 -0.27676855  0.06600394
Proline          0.64372004 -0.19201056  0.223626264 -0.44059693  0.39335085
                    Phenols Flavanoids Nonflavanoids Proanthocyanins       Color
Alcohol          0.28910112  0.2368149    -0.1559295     0.136697912  0.54636420
Malic           -0.33516700 -0.4110066     0.2929771    -0.220746187  0.24898534
Ash              0.12897954  0.1150773     0.1862304     0.009651935  0.25888726
Alcalinity      -0.32111332 -0.3513699     0.3619217    -0.197326836  0.01873198
Magnesium        0.21440123  0.1957838    -0.2562940     0.236440610  0.19995001
Phenols          1.00000000  0.8645635    -0.4499353     0.612413084 -0.05513642
Flavanoids       0.86456350  1.0000000    -0.5378996     0.652691769 -0.17237940
Nonflavanoids   -0.44993530 -0.5378996     1.0000000    -0.365845099  0.13905701
Proanthocyanins  0.61241308  0.6526918    -0.3658451     1.000000000 -0.02524993
Color           -0.05513642 -0.1723794     0.1390570    -0.025249931  1.00000000
Hue              0.43368134  0.5434786    -0.2626396     0.295544253 -0.52181319
Dilution         0.69994936  0.7871939    -0.5032696     0.519067096 -0.42881494
Proline          0.49811488  0.4941931    -0.3113852     0.330416700  0.31610011
                        Hue     Dilution    Proline
Alcohol         -0.07174720  0.072343187  0.6437200
Malic           -0.56129569 -0.368710428 -0.1920106
Ash             -0.07466689  0.003911231  0.2236263
Alcalinity      -0.27395522 -0.276768549 -0.4405969
Magnesium        0.05539820  0.066003936  0.3933508
Phenols          0.43368134  0.699949365  0.4981149
Flavanoids       0.54347857  0.787193902  0.4941931
Nonflavanoids   -0.26263963 -0.503269596 -0.3113852
Proanthocyanins  0.29554425  0.519067096  0.3304167
Color           -0.52181319 -0.428814942  0.3161001
Hue              1.00000000  0.565468293  0.2361834
Dilution         0.56546829  1.000000000  0.3127611
Proline          0.23618345  0.312761075  1.0000000





### To know the importance of the components :
### pcobj <- princomp(wine[-1], cor=TRUE , scores = TRUE , covmat = NULL)

### > summary(pcobj)

Importance of components:
                          Comp.1    Comp.2    Comp.3    Comp.4     Comp.5
Standard deviation     2.1692972 1.5801816 1.2025273 0.9586313 0.92370351
Proportion of Variance 0.3619885 0.1920749 0.1112363 0.0706903 0.06563294
Cumulative Proportion  0.3619885 0.5540634 0.6652997 0.7359900 0.80162293
                           Comp.6     Comp.7     Comp.8     Comp.9    Comp.10
Standard deviation     0.80103498 0.74231281 0.59033665 0.53747553 0.50090167
Proportion of Variance 0.04935823 0.04238679 0.02680749 0.02222153 0.01930019
Cumulative Proportion  0.85098116 0.89336795 0.92017544 0.94239698 0.96169717
                          Comp.11    Comp.12     Comp.13
Standard deviation     0.47517222 0.41081655 0.321524394
Proportion of Variance 0.01736836 0.01298233 0.007952149
Cumulative Proportion  0.97906553 0.99204785 1.000000000





### > str(pcobj)
List of 7
 $ sdev    : Named num [1:13] 2.169 1.58 1.203 0.959 0.924 ...
  ..- attr(*, "names")= chr [1:13] "Comp.1" "Comp.2" "Comp.3" "Comp.4" ...
 $ loadings: loadings [1:13, 1:13] -0.14433 0.24519 0.00205 0.23932 -0.14199 ...
  ..- attr(*, "dimnames")=List of 2
  .. ..$ : chr [1:13] "Alcohol" "Malic" "Ash" "Alcalinity" ...
  .. ..$ : chr [1:13] "Comp.1" "Comp.2" "Comp.3" "Comp.4" ...
 $ center  : Named num [1:13] 13 2.34 2.37 19.49 99.74 ...
  ..- attr(*, "names")= chr [1:13] "Alcohol" "Malic" "Ash" "Alcalinity" ...
 $ scale   : Named num [1:13] 0.81 1.114 0.274 3.33 14.242 ...
  ..- attr(*, "names")= chr [1:13] "Alcohol" "Malic" "Ash" "Alcalinity" ...
 $ n.obs   : int 178
 $ scores  : num [1:178, 1:13] -3.32 -2.21 -2.52 -3.76 -1.01 ...
  ..- attr(*, "dimnames")=List of 2
  .. ..$ : NULL
  .. ..$ : chr [1:13] "Comp.1" "Comp.2" "Comp.3" "Comp.4" ...
 $ call    : language princomp(x = wine[-1], cor = TRUE, scores = TRUE, covmat = NULL)
 - attr(*, "class")= chr "princomp"

















###  >loadings(pcobj)

Loadings:
                Comp.1 Comp.2 Comp.3 Comp.4 Comp.5 Comp.6 Comp.7 Comp.8 Comp.9
Alcohol         -0.144 -0.484 -0.207        -0.266  0.214         0.396 -0.509
Malic            0.245 -0.225         0.537         0.537 -0.421              
Ash                    -0.316  0.626 -0.214 -0.143  0.154  0.149 -0.170  0.308
Alcalinity       0.239         0.612               -0.101  0.287  0.428 -0.200
Magnesium       -0.142 -0.300  0.131 -0.352  0.727        -0.323 -0.156 -0.271
Phenols         -0.395         0.146  0.198 -0.149               -0.406 -0.286
Flavanoids      -0.423         0.151  0.152 -0.109               -0.187       
Nonflavanoids    0.299         0.170 -0.203 -0.501 -0.259 -0.595 -0.233 -0.196
Proanthocyanins -0.313         0.149  0.399  0.137 -0.534 -0.372  0.368  0.209
Color                  -0.530 -0.137               -0.419  0.228              
Hue             -0.297  0.279        -0.428 -0.174  0.106 -0.232  0.437       
Dilution        -0.376  0.164  0.166  0.184 -0.101  0.266               -0.137
Proline         -0.287 -0.365 -0.127 -0.232 -0.158  0.120         0.120  0.576
                Comp.10 Comp.11 Comp.12 Comp.13
Alcohol          0.212  -0.226  -0.266         
Malic           -0.309           0.122         
Ash                     -0.499          -0.141 
Alcalinity               0.479                 
Magnesium                                      
Phenols         -0.320   0.304  -0.304  -0.464 
Flavanoids      -0.163                   0.832 
Nonflavanoids    0.216   0.117           0.114 
Proanthocyanins  0.134  -0.237          -0.117 
Color           -0.291           0.604         
Hue             -0.522           0.259         
Dilution         0.524           0.601  -0.157 
Proline          0.162   0.539                 

               Comp.1 Comp.2 Comp.3 Comp.4 Comp.5 Comp.6 Comp.7 Comp.8 Comp.9
SS loadings     1.000  1.000  1.000  1.000  1.000  1.000  1.000  1.000  1.000
Proportion Var  0.077  0.077  0.077  0.077  0.077  0.077  0.077  0.077  0.077
Cumulative Var  0.077  0.154  0.231  0.308  0.385  0.462  0.538  0.615  0.692
               Comp.10 Comp.11 Comp.12 Comp.13
SS loadings      1.000   1.000   1.000   1.000
Proportion Var   0.077   0.077   0.077   0.077
Cumulative Var   0.769   0.846   0.923   1.000

### > plot(pcobj)
 
From the plot we can see that most of the data is occupied in the first 3 columns.
On doing :
biplot(pcobj)


 

### Now we can view the data of 3 major columns by :
pcobj$scores[,1:3]

            Comp.1      Comp.2       Comp.3
  [1,] -3.31675081 -1.44346263 -0.165739045
  [2,] -2.20946492  0.33339289 -2.026457374
  [3,] -2.51674015 -1.03115130  0.982818670
  [4,] -3.75706561 -2.75637191 -0.176191842
  [5,] -1.00890849 -0.86983082  2.026688219
  [6,] -3.05025392 -2.12240111 -0.629395827
  [7,] -2.44908967 -1.17485013 -0.977094891
  [8,] -2.05943687 -1.60896307  0.146281883
  [9,] -2.51087430 -0.91807096 -1.770969027
 [10,] -2.75362819 -0.78943767 -0.984247490
 [11,] -3.47973668 -1.30233324 -0.422735217
 [12,] -1.75475290 -0.61197723 -1.190878320
 [13,] -2.11346234 -0.67570634 -0.865086426
 [14,] -3.45815682 -1.13062988 -1.204276353
 [15,] -4.31278391 -2.09597558 -1.263912752
 [16,] -2.30518820 -1.66255173  0.217902616
 [17,] -2.17195527 -2.32730534  0.831729866
 [18,] -1.89897118 -1.63136888  0.794913792
 [19,] -3.54198508 -2.51834367 -0.485458508
 [20,] -2.08452220 -1.06113799 -0.164746678
 [21,] -3.12440254 -0.78689711 -0.364887083
 [22,] -1.08657007 -0.24174355  0.936961600
 [23,] -2.53522408  0.09184062 -0.311932659
 [24,] -1.64498834  0.51627893  0.143885095
 [25,] -1.76157587  0.31714893  0.890285647
 [26,] -0.99007910 -0.94066734  3.820908008
 [27,] -1.77527763 -0.68617513 -0.086700406
 [28,] -1.23542396  0.08980704 -1.386896545
 [29,] -2.18840633 -0.68956962  1.394566881
 [30,] -2.25610898 -0.19146194 -1.092657258
 [31,] -2.50022003 -1.24083383  1.386017855
 [32,] -2.67741105 -1.47187365 -0.332261728
 [33,] -1.62857912 -0.05270445 -0.167128706
 [34,] -1.90269086 -1.63306043  1.172082119
 [35,] -1.41038853 -0.69793432  0.479743025
 [36,] -1.90382623 -0.17671095  0.450835040
 [37,] -1.38486223 -0.65863985  0.458438581
 [38,] -1.12220741 -0.11410976 -0.039107277
 [39,] -1.50219450  0.76943201 -1.426177346
 [40,] -2.52980109 -1.80300198 -0.343152389
 [41,] -2.58809543 -0.77961630 -0.118477466
 [42,] -0.66848199 -0.16996094 -0.783362548
 [43,] -3.07080699 -1.15591896 -0.312758084
 [44,] -0.46220914 -0.33074213 -0.201476496
 [45,] -2.10135193  0.07100892 -0.655849415
 [46,] -1.13616618 -1.77710739  0.028705736
 [47,] -2.72660096 -1.19133469 -0.539773261
 [48,] -2.82133927 -0.64625860 -1.155552411
 [49,] -2.00985085 -1.24702946 -0.057293988
 [50,] -2.70749130 -1.75196741 -0.643113612
 [51,] -3.21491747 -0.16699199 -1.973571680
 [52,] -2.85895983 -0.74527880  0.004719502
 [53,] -3.50560436 -1.61273386 -0.520774530
 [54,] -2.22479138 -1.87516800  0.339549850
 [55,] -2.14698782 -1.01675154 -0.957762762
 [56,] -2.46932948 -1.32900831  0.513437453
 [57,] -2.74151791 -1.43654878 -0.612473396
 [58,] -2.17374092 -1.21219984  0.261779593
 [59,] -3.13938015 -1.73157912 -0.285661413
 [60,]  0.92858197  3.07348616 -4.585064007
 [61,]  1.54248014  1.38144351 -0.874683112
 [62,]  1.83624976  0.82998412 -1.605702186
 [63,] -0.03060683  1.26278614 -1.784408010
 [64,] -2.05026161  1.92503260 -0.007368777
 [65,]  0.60968083  1.90805881  0.679357938
 [66,] -0.90022784  0.76391147  0.573361302
 [67,] -2.24850719  1.88459248 -2.031840193
 [68,] -0.18338403  2.42714611 -1.069745560
 [69,]  0.81280503  0.22051399 -0.707005396
 [70,] -1.97562050  1.40328323 -1.238276220
 [71,]  1.57221622  0.88498314 -0.628997950
 [72,] -1.65768181  0.95671220  1.952584217
 [73,]  0.72537239  1.06364540  0.080332229
 [74,] -2.56222717 -0.26019855  3.374393962
 [75,] -1.83256757  1.28787820  0.458280027
 [76,]  0.86799290  2.44410119 -1.563333179
 [77,] -0.37001440  2.15390698 -2.449386348
 [78,]  1.45737704  1.38335177 -0.227306902
 [79,] -1.26293085  0.77084953 -1.184224517
 [80,] -0.37615037  1.02704340  1.794466295
 [81,] -0.76206390  3.37505381 -0.357470056
 [82,] -1.03457797  1.45070974 -0.363011773
 [83,]  0.49487676  2.38124353  1.335743176
 [84,]  2.53897708  0.08744336  0.474251393
 [85,] -0.83532015  1.47367055  0.610093576
 [86,] -0.78790461  2.02662652 -0.254723404
 [87,]  0.80683216  2.23383039  0.772855797
 [88,]  0.55804262  2.37298543  2.307611404
 [89,]  1.11511104  1.80224719  0.959253308
 [90,]  0.55572283  2.65754004  0.849126898
 [91,]  1.34928528  2.11800147 -0.047652321
 [92,]  1.56448261  1.85221452  0.781067031
 [93,]  1.93255561  1.55949546 -0.089274676
 [94,] -0.74666594  2.31293171  0.114679769
 [95,] -0.95745536  2.22352843  0.142444774
 [96,] -2.54386518 -0.16927402  0.788696991
 [97,]  0.54395259  0.36892655  1.308895932
 [98,] -1.03104975  2.56556935 -1.086390174
 [99,] -2.25190942  1.43274138 -0.230208244
[100,] -1.41021602  2.16619177  0.748896411
[101,] -0.79771979  2.37694880 -1.568112531
[102,]  0.54953173  2.29312864 -1.498935323
[103,]  0.16117374  1.16448332  1.003713103
[104,]  0.65979494  2.67996119 -0.764920868
[105,] -0.39235441  2.09873171 -0.471850008
[106,]  1.77249908  1.71728847  0.947033174
[107,]  0.36626736  2.16935330 -0.481324235
[108,]  1.62067257  1.35558339  0.287159001
[109,] -0.08253578  2.30623459 -0.463574989
[110,] -1.57827507  1.46203429  1.779645955
[111,] -1.42056925  1.41820664  0.139275829
[112,]  0.27870275  1.93056809  0.078670553
[113,]  1.30314497  0.76317231  1.999596510
[114,]  0.45707187  2.26941561  1.061338968
[115,]  0.49418585  1.93904505  1.323938072
[116,] -0.48207441  3.87178385  1.344271223
[117,]  0.25288888  2.82149237 -0.302639785
[118,]  0.10722764  1.92892204  0.690148243
[119,]  2.43301260  1.25714104 -1.903027404
[120,]  0.55108954  2.22216155 -0.356228830
[121,] -0.73962193  1.40895667  1.125345492
[122,] -1.33632173 -0.25333693  5.345388179
[123,]  1.17708700  0.66396684  3.010221888
[124,]  0.46233501  0.61828818  0.483442366
[125,] -0.97847408  1.44557050  1.481236975
[126,]  0.09680973  2.10999799  0.434826116
[127,] -0.03848715  1.26676211  0.687577913
[128,]  1.59715850  1.20814357  3.361175555
[129,]  0.47956492  1.93884066  1.296507519
[130,]  1.79283347  1.15028810  0.782800173
[131,]  1.32710166 -0.17038923 -1.180013355
[132,]  2.38450083 -0.37458261 -0.723822595
[133,]  2.93694010 -0.26386183 -0.167639816
[134,]  2.14681113 -0.36825495 -0.453301301
[135,]  2.36986949  0.45963481 -1.101399789
[136,]  3.06384157 -0.35341284 -1.099124104
[137,]  3.91575378 -0.15458252  0.221827800
[138,]  3.93646339 -0.65968723  1.712215419
[139,]  3.09427612 -0.34884276 -1.026831413
[140,]  2.37447163 -0.29198035  1.241914333
[141,]  2.77881295 -0.28680487  0.609670124
[142,]  2.28656128 -0.37250784 -0.971643032
[143,]  2.98563349 -0.48921791  0.946952932
[144,]  2.37519470 -0.48233372 -0.252883994
[145,]  2.20986553 -1.16005250 -1.245125226
[146,]  2.62562100 -0.56316076 -0.855961082
[147,]  4.28063878 -0.64967096 -1.458196962
[148,]  3.58264137 -1.27270275 -0.110784038
[149,]  2.80706372 -1.57053379 -0.472527935
[150,]  2.89965933 -2.04105701 -0.495959810
[151,]  2.32073698 -2.35636608  0.437681744
[152,]  2.54983095 -2.04528309 -0.312267999
[153,]  1.81254128 -1.52764595  1.362589782
[154,]  2.76014464 -2.13893235 -0.964628688
[155,]  2.73715050 -0.40988627 -1.190404684
[156,]  3.60486887 -1.80238422 -0.094036861
[157,]  2.88982600 -1.92521861 -0.782322556
[158,]  3.39215608 -1.31187639  1.602025969
[159,]  1.04818190 -3.51508969  1.160038566
[160,]  1.60991228 -2.40663816  0.548559697
[161,]  3.14313097 -0.73816104 -0.090998724
[162,]  2.24015690 -1.17546529 -0.101376932
[163,]  2.84767378 -0.55604397  0.804215218
[164,]  2.59749706 -0.69796554 -0.884939521
[165,]  2.94929937 -1.55530896 -0.983400727
[166,]  3.53003227 -0.88252680 -0.466029128
[167,]  2.40611054 -2.59235618  0.428226211
[168,]  2.92908473 -1.27444695 -1.213358272
[169,]  2.18141278 -2.07753731  0.763782552
[170,]  2.38092779 -2.58866743  1.418044029
[171,]  3.21161722  0.25124910 -0.847129152
[172,]  3.67791872 -0.84774784 -1.339420231
[173,]  2.46555580 -2.19379830 -0.918780960
[174,]  3.37052415 -2.21628914 -0.342569512
[175,]  2.60195585 -1.75722935  0.207581355
[176,]  2.67783946 -2.76089913 -0.940941877
[177,]  2.38701709 -2.29734668 -0.550696197
[178,]  3.20875816 -2.76891957  1.013913664


### wine <- cbind(wine ,pcobj$scores[,1:3])
### > View(wine)
Type Alcohol Malic  Ash Alcalinity Magnesium Phenols Flavanoids Nonflavanoids
1      1   14.23  1.71 2.43       15.6       127    2.80       3.06          0.28
2      1   13.20  1.78 2.14       11.2       100    2.65       2.76          0.26
3      1   13.16  2.36 2.67       18.6       101    2.80       3.24          0.30
4      1   14.37  1.95 2.50       16.8       113    3.85       3.49          0.24
5      1   13.24  2.59 2.87       21.0       118    2.80       2.69          0.39
6      1   14.20  1.76 2.45       15.2       112    3.27       3.39          0.34
7      1   14.39  1.87 2.45       14.6        96    2.50       2.52          0.30
8      1   14.06  2.15 2.61       17.6       121    2.60       2.51          0.31
9      1   14.83  1.64 2.17       14.0        97    2.80       2.98          0.29
10     1   13.86  1.35 2.27       16.0        98    2.98       3.15          0.22
11     1   14.10  2.16 2.30       18.0       105    2.95       3.32          0.22
12     1   14.12  1.48 2.32       16.8        95    2.20       2.43          0.26
13     1   13.75  1.73 2.41       16.0        89    2.60       2.76          0.29
14     1   14.75  1.73 2.39       11.4        91    3.10       3.69          0.43
15     1   14.38  1.87 2.38       12.0       102    3.30       3.64          0.29
16     1   13.63  1.81 2.70       17.2       112    2.85       2.91          0.30
17     1   14.30  1.92 2.72       20.0       120    2.80       3.14          0.33
18     1   13.83  1.57 2.62       20.0       115    2.95       3.40          0.40
19     1   14.19  1.59 2.48       16.5       108    3.30       3.93          0.32
20     1   13.64  3.10 2.56       15.2       116    2.70       3.03          0.17
21     1   14.06  1.63 2.28       16.0       126    3.00       3.17          0.24
22     1   12.93  3.80 2.65       18.6       102    2.41       2.41          0.25
23     1   13.71  1.86 2.36       16.6       101    2.61       2.88          0.27
24     1   12.85  1.60 2.52       17.8        95    2.48       2.37          0.26
25     1   13.50  1.81 2.61       20.0        96    2.53       2.61          0.28
26     1   13.05  2.05 3.22       25.0       124    2.63       2.68          0.47
27     1   13.39  1.77 2.62       16.1        93    2.85       2.94          0.34
28     1   13.30  1.72 2.14       17.0        94    2.40       2.19          0.27
29     1   13.87  1.90 2.80       19.4       107    2.95       2.97          0.37
30     1   14.02  1.68 2.21       16.0        96    2.65       2.33          0.26
31     1   13.73  1.50 2.70       22.5       101    3.00       3.25          0.29
32     1   13.58  1.66 2.36       19.1       106    2.86       3.19          0.22
33     1   13.68  1.83 2.36       17.2       104    2.42       2.69          0.42
34     1   13.76  1.53 2.70       19.5       132    2.95       2.74          0.50
35     1   13.51  1.80 2.65       19.0       110    2.35       2.53          0.29
36     1   13.48  1.81 2.41       20.5       100    2.70       2.98          0.26
37     1   13.28  1.64 2.84       15.5       110    2.60       2.68          0.34
38     1   13.05  1.65 2.55       18.0        98    2.45       2.43          0.29
39     1   13.07  1.50 2.10       15.5        98    2.40       2.64          0.28
40     1   14.22  3.99 2.51       13.2       128    3.00       3.04          0.20
41     1   13.56  1.71 2.31       16.2       117    3.15       3.29          0.34
42     1   13.41  3.84 2.12       18.8        90    2.45       2.68          0.27
43     1   13.88  1.89 2.59       15.0       101    3.25       3.56          0.17
44     1   13.24  3.98 2.29       17.5       103    2.64       2.63          0.32
45     1   13.05  1.77 2.10       17.0       107    3.00       3.00          0.28
46     1   14.21  4.04 2.44       18.9       111    2.85       2.65          0.30
47     1   14.38  3.59 2.28       16.0       102    3.25       3.17          0.27
48     1   13.90  1.68 2.12       16.0       101    3.10       3.39          0.21
49     1   14.10  2.02 2.40       18.8       103    2.75       2.92          0.32
50     1   13.94  1.73 2.27       17.4       108    2.88       3.54          0.32
51     1   13.05  1.73 2.04       12.4        92    2.72       3.27          0.17
52     1   13.83  1.65 2.60       17.2        94    2.45       2.99          0.22
53     1   13.82  1.75 2.42       14.0       111    3.88       3.74          0.32
54     1   13.77  1.90 2.68       17.1       115    3.00       2.79          0.39
55     1   13.74  1.67 2.25       16.4       118    2.60       2.90          0.21
56     1   13.56  1.73 2.46       20.5       116    2.96       2.78          0.20
57     1   14.22  1.70 2.30       16.3       118    3.20       3.00          0.26
58     1   13.29  1.97 2.68       16.8       102    3.00       3.23          0.31
    Proanthocyanins     Color   Hue Dilution Proline      Comp.1      Comp.2
1              2.29  5.640000 1.040     3.92    1065 -3.31675081 -1.44346263
2              1.28  4.380000 1.050     3.40    1050 -2.20946492  0.33339289
3              2.81  5.680000 1.030     3.17    1185 -2.51674015 -1.03115130
4              2.18  7.800000 0.860     3.45    1480 -3.75706561 -2.75637191
5              1.82  4.320000 1.040     2.93     735 -1.00890849 -0.86983082
6              1.97  6.750000 1.050     2.85    1450 -3.05025392 -2.12240111
7              1.98  5.250000 1.020     3.58    1290 -2.44908967 -1.17485013
8              1.25  5.050000 1.060     3.58    1295 -2.05943687 -1.60896307
9              1.98  5.200000 1.080     2.85    1045 -2.51087430 -0.91807096
10             1.85  7.220000 1.010     3.55    1045 -2.75362819 -0.78943767
11             2.38  5.750000 1.250     3.17    1510 -3.47973668 -1.30233324
12             1.57  5.000000 1.170     2.82    1280 -1.75475290 -0.61197723
13             1.81  5.600000 1.150     2.90    1320 -2.11346234 -0.67570634
14             2.81  5.400000 1.250     2.73    1150 -3.45815682 -1.13062988
15             2.96  7.500000 1.200     3.00    1547 -4.31278391 -2.09597558
16             1.46  7.300000 1.280     2.88    1310 -2.30518820 -1.66255173
17             1.97  6.200000 1.070     2.65    1280 -2.17195527 -2.32730534
18             1.72  6.600000 1.130     2.57    1130 -1.89897118 -1.63136888
19             1.86  8.700000 1.230     2.82    1680 -3.54198508 -2.51834367
20             1.66  5.100000 0.960     3.36     845 -2.08452220 -1.06113799
21             2.10  5.650000 1.090     3.71     780 -3.12440254 -0.78689711
22             1.98  4.500000 1.030     3.52     770 -1.08657007 -0.24174355
23             1.69  3.800000 1.110     4.00    1035 -2.53522408  0.09184062
24             1.46  3.930000 1.090     3.63    1015 -1.64498834  0.51627893
25             1.66  3.520000 1.120     3.82     845 -1.76157587  0.31714893
26             1.92  3.580000 1.130     3.20     830 -0.99007910 -0.94066734
27             1.45  4.800000 0.920     3.22    1195 -1.77527763 -0.68617513
28             1.35  3.950000 1.020     2.77    1285 -1.23542396  0.08980704
29             1.76  4.500000 1.250     3.40     915 -2.18840633 -0.68956962
30             1.98  4.700000 1.040     3.59    1035 -2.25610898 -0.19146194
31             2.38  5.700000 1.190     2.71    1285 -2.50022003 -1.24083383
32             1.95  6.900000 1.090     2.88    1515 -2.67741105 -1.47187365
33             1.97  3.840000 1.230     2.87     990 -1.62857912 -0.05270445
34             1.35  5.400000 1.250     3.00    1235 -1.90269086 -1.63306043
35             1.54  4.200000 1.100     2.87    1095 -1.41038853 -0.69793432
36             1.86  5.100000 1.040     3.47     920 -1.90382623 -0.17671095
37             1.36  4.600000 1.090     2.78     880 -1.38486223 -0.65863985
38             1.44  4.250000 1.120     2.51    1105 -1.12220741 -0.11410976
39             1.37  3.700000 1.180     2.69    1020 -1.50219450  0.76943201
40             2.08  5.100000 0.890     3.53     760 -2.52980109 -1.80300198
41             2.34  6.130000 0.950     3.38     795 -2.58809543 -0.77961630
42             1.48  4.280000 0.910     3.00    1035 -0.66848199 -0.16996094
43             1.70  5.430000 0.880     3.56    1095 -3.07080699 -1.15591896
44             1.66  4.360000 0.820     3.00     680 -0.46220914 -0.33074213
45             2.03  5.040000 0.880     3.35     885 -2.10135193  0.07100892
46             1.25  5.240000 0.870     3.33    1080 -1.13616618 -1.77710739
47             2.19  4.900000 1.040     3.44    1065 -2.72660096 -1.19133469
48             2.14  6.100000 0.910     3.33     985 -2.82133927 -0.64625860
49             2.38  6.200000 1.070     2.75    1060 -2.00985085 -1.24702946
50             2.08  8.900000 1.120     3.10    1260 -2.70749130 -1.75196741
51             2.91  7.200000 1.120     2.91    1150 -3.21491747 -0.16699199
52             2.29  5.600000 1.240     3.37    1265 -2.85895983 -0.74527880
53             1.87  7.050000 1.010     3.26    1190 -3.50560436 -1.61273386
54             1.68  6.300000 1.130     2.93    1375 -2.22479138 -1.87516800
55             1.62  5.850000 0.920     3.20    1060 -2.14698782 -1.01675154
56             2.45  6.250000 0.980     3.03    1120 -2.46932948 -1.32900831
57             2.03  6.380000 0.940     3.31     970 -2.74151791 -1.43654878
58             1.66  6.000000 1.070     2.84    1270 -2.17374092 -1.21219984
          Comp.3
1   -0.165739045
2   -2.026457374
3    0.982818670
4   -0.176191842
5    2.026688219
6   -0.629395827
7   -0.977094891
8    0.146281883
9   -1.770969027
10  -0.984247490
11  -0.422735217
12  -1.190878320
13  -0.865086426
14  -1.204276353
15  -1.263912752
16   0.217902616
17   0.831729866
18   0.794913792
19  -0.485458508
20  -0.164746678
21  -0.364887083
22   0.936961600
23  -0.311932659
24   0.143885095
25   0.890285647
26   3.820908008
27  -0.086700406
28  -1.386896545
29   1.394566881
30  -1.092657258
31   1.386017855
32  -0.332261728
33  -0.167128706
34   1.172082119
35   0.479743025
36   0.450835040
37   0.458438581
38  -0.039107277
39  -1.426177346
40  -0.343152389
41  -0.118477466
42  -0.783362548
43  -0.312758084
44  -0.201476496
45  -0.655849415
46   0.028705736
47  -0.539773261
48  -1.155552411
49  -0.057293988
50  -0.643113612
51  -1.973571680
52   0.004719502
53  -0.520774530
54   0.339549850
55  -0.957762762
56   0.513437453
57  -0.612473396
58   0.261779593


### > clust_data <- wine[,15:17]
### > norm_clust <- scale(clust_data)
### > dist1 <- dist(norm_clust ,method = "euclidean")

### > fit1 <- hclust(dist1 , method = "complete")
### > plot(fit1)

 





### Forming into groups , 

### > groups <- cutree(fit1 , 3)
### > mem <- as.matrix(groups)



### > final <- cbind(mem , wine)
### > View(final)


 





 ###  Therefore , 3 cluster have been formed .

###  We can save the new csv file by :
### write.csv(final, file = "pca sol1.csv", row.names = F , col.names = F)
### > getwd()

[1] "C:/Users/admin/Documents"




				            	
# 	FORECASTING		                
## Assignment 1
###  BP:   Forecast the Airlines Passengers data set. Prepare a document for each model explaining how many dummy variables you have created and RMSE value for each model. Finally which model you will use for Forecasting.



PROCEDURE:

## STEP 1: First we have to Exploratory Data Analysis which can be done by plotting scattered plot, box plots and summary.

### summary(Airlines_Data_1_)
     Month                       Passengers   
 Min.   :1995-01-01 00:00:00   Min.   :104.0  
 1st Qu.:1996-12-24 06:00:00   1st Qu.:156.0  
 Median :1998-12-16 12:00:00   Median :200.0  
 Mean   :1998-12-16 05:00:00   Mean   :213.7  
 3rd Qu.:2000-12-08 18:00:00   3rd Qu.:264.8  
 Max.   :2002-12-01 00:00:00   Max.   :413.0  


### From the summary we can see that in Month & Passengers the difference between mean and max is     not so   large so it is centre skewed can my confirmed by using Box Plot .



 


Scatter Plot for the Following data frame is:



 

# STEP 2: Forecasting the data 


## first from the data we have to analyse the seasonality, trend.

## Now on drawing the plots we can say that the data is seasonal, has some trend.

 


## Now, pre-processing the data. After pre-processing uploading the data in excel miner then we can partition the data and then apply forecasting methods.




## Now using r Studio we can pre-process data by following code: 


## Dividing the dataset into 12 columns and assigning names to columns
###  x <- data.frame(outer(rep(month.abb,length=96),month.abb,"==") +0)
### > colnames(x) <- month.abb
### > View(x)

## Combing the columns of original data set to the newly formed dataset :

### > airlinespassengers <- cbind(Airlines_Data_original,x)
### > View(airlinespassengers)


### Adding the columns as a part of preprocessing data : 
### adding time index:

### airlinespassengers["t"] <- c(1:96)
### adding the column log :airlinespassengers["log_Passengers"] <- log(airlinespassengers["Passengers"])
### adding the column t Square : airlinespassengers["T_Square"] <- airlinespassengers["t"] * airlinespassengers["t"]
### > View(airlinespassengers)


### End of pre-processing the data. Now we have to partition data :
### train <- airlinespassengers[1:84,]
### test <- airlinespassengers[85:96,]

### Now preparing the models to find out the value of RMSE :

### Linear Model:
### linearmodel <- lm(Passengers~t , data = train)
### > linear_pred <- data.frame(predict(linearmodel, interval = 'predict', newdata=test))
### > rmselinear <- sqrt(mean((test$Passengers-linear_pred$fit)^2 , na.rm = T))

### exponential model :
### expomodel <- lm(log_Passengers~t , data= train)
### > expopred <- data.frame(predict(expomodel,interval = 'predict',newdata = test))
### > rmseexpo <- sqrt(mean((test$Passengers- exp(expopred$fit))^2 , na.rm = T))
### > rmseexpo



### Quadratic:
### quamodel <- lm(Passengers~t+ T_Square , data= train)
### > quapred <- data.frame(predict(quamodel, interval = 'predict' , newdata = test))
### > rmsequa <- sqrt(mean((test$Passengers-quapred$fit)^2 , na.rm=T))




### Additive seasonality :
### addmodel <- lm(Passengers ~ Jan+Feb+Mar+Apr+May+Jun +Jul +Aug +Sep +Oct +Nov , data=train)
### > addpred <- data.frame(predict(addmodel, interval = 'predict', newdata = test))
### > rmsadd <- sqrt(mean((test$Passengers-addpred$fit)^2, na.ram=T))

### Additive seasonality with quadratic trend :
### addquadpred <- data.frame(predict(addquadmodel, interval='predict' , newdata=test))
### > addquadadd <- sqrt(mean((test$Passengers-addquadpred$fit)^2, na.rm = T))



### Multiplication Seasonality :
### mulmodel <- lm(log_Passengers~Jan+Feb+Mar+Apr+May+Jun +Jul +Aug +Sep +Oct +Nov , data=train)
### > mullpred <- data.frame(predict(mulmodel , interval = 'predict' , newdata = test))
### > rmsemul <- sqrt(mean((test$Passengers-exp(mullpred$fit))^2, na.rm = T))

 
###  From the above table we can that the Best model is Additive seasonality with quadratic trend.

### Now prepare a final model with complete data  ( not with partitioning )
### finalmodel <- lm(Passengers~t+T_Square+Jan+Feb+Mar+Apr+May+Jun +Jul +Aug +Sep +Oct +Nov , data=airlinespassengers)
 

### Now a dataset of pre-processed set is uploaded into r studio:
### predictnew <- predict(finalmodel , newdata = test_data , interval = 'predict')
> predictnew <- as.data.frame(predictnew)

### Now using these we can predict the values  and plotting the acf  we can find any significance is existing :

### acf(finalmodel$residuals , lag.max = 10)
  
### From the plot we can see that there are lot of significant values , acc to law of parsimony we  use arima model i.e., autoregressive model with 1 (as 1st significant error) :

### a <- arima(finalmodel$residuals , order = c(1,0,0))

### Now we do error or errors to reduce the significant values:
 
 ### Now we can observe that there are no significant values ( as lag 0 we dint consider it ).
### Forecasting the errors :
### errors12 <- forecast(a , h=12)

### futureerrors <- data.frame(errors12)
### > class(futureerrors)
[1] "data.frame"
### > futureerrors <- futureerrors$Point.Forecast


### Now the forecasted data for the next 12 months along with errors I given by : 

### prednewvalues <- predictnew + futureerrors


### We can save the file by using the following code:

###  write.csv(prednewvalues , file="prednewvalues.csv" )








## NEURAL NETWORKS 	
		                
### Assignment 1
## BP:  Build a Neural Network model for 50_startups data to predict profit

## PROCEDURE:

## STEP 1: First we have to Exploratory Data Analysis which can be done by plotting scattered plot, box plots and summary.

### summary(X50_Startups_1_)

   R&D Spend         Administration      Marketing Spend        State    
 Min.   :     0.00   Min.   : 51283.14   Min.   :     0.0   Min.   : NA  
 1st Qu.: 39936.37   1st Qu.:103730.88   1st Qu.:129300.1   1st Qu.: NA  
 Median : 73051.08   Median :122699.79   Median :212716.2   Median : NA  
 Mean   : 73721.62   Mean   :121344.64   Mean   :211025.1   Mean   :NaN  
 3rd Qu.:101602.80   3rd Qu.:144842.18   3rd Qu.:299469.1   3rd Qu.: NA  
 Max.   :165349.20   Max.   :182645.56   Max.   :471784.1   Max.   : NA  
                                                            NA's   :50   
     Profit        
 Min.   : 14681.4  
 1st Qu.: 90138.9  
 Median :107978.2  
 Mean   :112012.6  
 3rd Qu.:139766.0  
 Max.   :192261.8 
  

### From the summary we can see that in Profit   the difference between mean and max is         large so it may be right  skewed it can my confirmed by using Box Plot .

### It can be confirmed that Profit is right  Skewed.

 


Scatter Plot for the Following data frame is:






 



## STEP 2: Now forming the neural networks 
## Normalizing the data:

### normalize<-function(x){
+   return ( (x-min(x))/(max(x)-min(x)))
+ }
> concrete_norm<-as.data.frame(lapply(concrete,FUN=normalize))

## After normalization we can check by using summary : 

### > summary(summary(X50_Startups_1_$Profit)

   Min. 1st Qu.  Median    Mean   3rd Qu.    Max. 
 0.0000  0.424  0.4001    0.5480    0.7324    1.0000 




 

## Now splitting the data into test and train : 


### > X50_Startups_1__train<-concrete_norm[1:30,]
### > X50_Startups_1_$_test<-concrete_norm[31:50,]


 

## Before building the model we need to install some packages required for neural network formation:

### install.packages("neuralnet")
### install.packages("nnet")

### library(neuralnet)

### library(nnet)



 

### Now after splitting the data into test and train , we can Build model on training data  which is given by :
### X50_Startups_1_model <- neuralnet(Profit~R.D.Spend+ Administration + Marketing Spend + state ,data = X50_Startups_1__train)


## The Plot is given by :
### plot(X50_Startups_1_model)
 






### > cor(predicted_strength, X50_Startups_1__test$Profit)
             [,1]
[1,] 0.8262921349
### > plot(predicted_strength, X50_Startups_1__test$Profit)



## Now for better accuracy we can create various models:

## We are trying to increase the number of nodes :

### Model2<- neuralnet(Profit~R.D.Spend+ Administration + Marketing Spend + state ,data = X50_Startups_1__train,hidden = 6)

### > plot(model2)


 





### model_2_res<-compute(model2, X50_Startups_1__test [1:4])

### > pred_strn_2<-model_2_res$net.result
### > cor(pred_strn_2, X50_Startups_1__test$Profit)
            [,1]
[1,] 0.9051979049
### > plot(pred_strn_5,concrete_test$strength)

> 

 

### Comparatively , model 2 has higher correlation value compared to that of the model , which is even visible through the plot .

### Thus model 2 is taken into consideration .  



## Regression
## Logistic  Regression
## Assignment 3
###  BP:  Suppose we are interested in the factors that influence whether a political candidate wins an election. 
The outcome (response) variable is binary (0/1); win or lose. 
The predictor variables of interest are the amount of money spent on the campaign, 
the amount of time spent campaigning negatively and whether or not the candidate is an incumbent.

###  1.	Now we have to create a Logistic Regression model for this , by the formula :
logreg <- glm(Result ~ factor (amount spent)+ factor (popularity rank) )

###  on using summary ( reg ) we get,
Null deviance: 2.4000e+00  on 9  degrees of freedom
Residual deviance: 9.3711e-31  on 0  degrees of freedom
  (1 observation deleted due to missingness)
AIC: -664.07


###  The model with least AIC is the best model .

EDA of the data is as follows:


 
	

 






### 2.	 Now we have to try and build model by finding the probability we can get an idea of the model i.e, the probability of candidate whether he wins or not
prob = predict(logreg, type=c("response"),election_data)

On entering prob we get
prob 

1             2             3             4             5             6 
           NA  5.726371e-16  1.000000e+00  1.000000e+00  4.037458e-16  1.000000e+00 
            7             8             9            10            11 
-2.192009e-17  1.000000e+00  1.000000e+00  1.000000e+00  2.755483e-16 




## Now from the values we can assume that for the 1st value the probability of candidate winning  is 0% , so from the data we can see that it may be correct.


## To get the Confusion matrix ,

###  confusion <- table(prob>0.5,affairs$naffairs)

the output is as follows:
          0 1
  FALSE   4 0
  TRUE    0 6


### seems like there is 100% true prediction which may seem impossible in real time scenarios . So the ROC curve is :




## Regression 
##  Multi Linear Regression
## Assignment 1
## BP:  Prepare a prediction model for profit of 50_startups data.
## Do transformations for getting better predictions of profit and
## Make a table containing R^2 value for each prepared model.
### 1.	Now, from the given data we can observe that there is qualitative data after analysing the data we can eliminate the qualitative data as it doesn’t have any effect on the output.
This can be done by using dummies and dummy packages.
### 2.	Now we have to create a multi linear model for this , by the formula :
### m2 <- lm(Profit ~ `Marketing Spend` + State + Administration)

On using summary (m2) we get,
Now and value of R2= 0.6097

EDA of the data is as follows:

	 
 

 



 

### 3.	 Now we have to try and build model , we can use variance inflation models,
If vif > 10 collinearity is good, but from the given values we can see that collinearity is on lower side, we cannot remove all, but can eliminate at least the least one.
So let’s check which factor is effecting the correlation to bring it down.

### Now on plotting added variable plots, we get as follows 
 
### From the following plots we can assume that, ads , multi , cd has been pulling down the value of correlation . But we cannot ### judge directly like that, so we use another method of regression called as Akaike information criterion model .

### on doing so we get as follows,
### Profit ~ `Marketing Spend` + State + Administration

                    Df   Sum of Sq        RSS       AIC
- State              2   2.6942e+08   3.1068e+10    1018.4
<none>                                3.0799e+10    1021.9
- Administration     1   4.0290e+09   3.4827e+10    1026.1
- Marketing Spend    1   4.3775e+10   7.4573e+10    1064.2

###  Step:  AIC=1018.37
###  Profit ~ `Marketing Spend` + Administration

                    Df   Sum of Sq        RSS      AIC
<none>                                 3.1068e+10   1018.4
- Administration     1   4.0256e+09    3.5094e+10   1022.5
- Marketing Spend    1   4.5330e+10    7.6398e+10   1061.4

Call:
lm(formula = Profit ~ `Marketing Spend` + Administration)

Coefficients:
      (Intercept)  `Marketing Spend`     Administration  
        2.022e+04          2.488e-01          3.237e-01 

### According to AIC regression, it is suggesting to remove the quantitative data column which is trying to reduce the collinearity.
### The value of R2 is = 0.6131.

### This is increased by a very small value.

### Now from the Plots we can observe that 47th entry is trying to reduce the collinearity, so let’s remove that and try to form the model

###  On doing so we get the value of R2 =0.683.
### We can observe that it has increased by a great value .




### To increase the value of R2 we can try some transformations.

###  The value before and after transformation are:


 	

### So we can conclude that after transformations, it’s getting even worse so, better not to apply transformations.


# SUPPORT VECTOR MACHINES 	
		                
## Assignment 1
## BP:   Prepare a classification model using SVM for salary data



## PROCEDURE:

## STEP 1: First we have to Exploratory Data Analysis which can be done by plotting scattered plot, box plots and summary.

age               workclass          education          educationno   
 Min.   :17.00   Length:30161       Length:30161       Min.   : 1.00  
 1st Qu.:28.00   Class :character   Class :character   1st Qu.: 9.00  
 Median :37.00   Mode  :character   Mode  :character   Median :10.00  
 Mean   :38.44                                         Mean   :10.12  
 3rd Qu.:47.00                                         3rd Qu.:13.00  
 Max.   :90.00                                         Max.   :16.00  
 
maritalstatus       occupation        relationship           race          
 Length:30161       Length:30161       Length:30161       Length:30161      
 Class :character   Class :character   Class :character   Class :character  
 Mode  :character   Mode  :character   Mode  :character   Mode  :character  
                                                                            
                                                                            
                                                                            
     sex             capitalgain     capitalloss      hoursperweek  
 Length:30161       Min.   :    0   Min.   :   0.0   Min.   : 1.00  
 Class :character   1st Qu.:    0   1st Qu.:   0.0   1st Qu.:40.00  
 Mode  :character   Median :    0   Median :   0.0   Median :40.00  
                    Mean   : 1092   Mean   :  88.3   Mean   :40.93  
                    3rd Qu.:    0   3rd Qu.:   0.0   3rd Qu.:45.00  
                    Max.   :99999   Max.   :4356.0   Max.   :99.00  
    native             Salary         
 Length:30161       Length:30161      
 Class :character   Class :character  
 Mode  :character   Mode  :character 

From the summary we can see that in capital gain and capital loss the difference between mean and max is        large so it may be right  skewed it can my confirmed by using Box Plot .

It can be confirmed that capital gain and capital loss is right Skewed.

 


Scatter Plot for the Following data frame is:


 
## STEP 2: Predicting the data using SVM techniques 











### Before building the model we need to install some packages required for SVM formation:

### install.packages("kernlab")

### library(kernlab)




Now after splitting the data into test and train , we can Build model on training data  which is given by  ( here we use vanilla dot mode ):
### salary_model <- ksvm(Salary~ ., data=SalaryData_Train_1_ , kernel="vanilladot")



 

Now predicting the model using some kernel techniques:


### salary_prediction <- predict(salary_model ,SalaryData_Test_1_)
> 
> 
### > head(salary_prediction)
[1] <=50K <=50K <=50K >50K  <=50K >50K 
Levels: <=50K >50K
### table(salary_prediction , SalaryData_Test_1_$Salary)
                 
salary_prediction <=50K  >50K
            <=50K 10599  1554
            >50K    761  2146

### agreement <- salary_prediction == SalaryData_Test_1_$Salary
> 
> 
### > table(agreement)
agreement
FALSE  TRUE 
 2315 12745
### > prop.table(table(agreement))
agreement
    FALSE      TRUE 
0.1537185 0.8462815 


### The Above prediction shows 0.84 % of true results , we can check with other models to improve accuracy .

### polydot model :

### salary_model2 <- ksvm(Salary ~ ., data=SalaryData_Train_1_ , kernel= "polydot" , parallel= TRUE)
 Setting default kernel parameters  
> salary_prediction2 <- predict(salary_model2 , SalaryData_Test_1_)
>  
> 
> 
### > salary_prediction2 <- predict(salary_model2 , SalaryData_Test_1_)
>  
> 
> 
### > head(salary_prediction2)
[1] <=50K <=50K <=50K >50K  <=50K >50K 
Levels: <=50K >50K
> 
> 
### > table(salary_prediction2 , SalaryData_Test_1_$Salary)
                  
### salary_prediction2 <=50K  >50K
             <=50K 10598  1553
             >50K    762  2147
### > agreement <- salary_prediction2 == SalaryData_Test_1_$Salary
### > table(agreement)
agreement
FALSE  TRUE 
 2315 12745 
### > agreement2 <- salary_prediction2 == SalaryData_Test_1_$Salary
### > table(agreement2)
agreement2
FALSE  TRUE 
 2315 12745 
### > prop.table(table(agreement2))
agreement2
    FALSE      TRUE 
0.1537185 0.8462815 



### Seems like there is no change in output so better to consider 1st model as we cannot afford the same efficiency with  so much increase in time period.


 












 








 
















