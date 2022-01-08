# ExploratoryDataAnalysis-Regression-HousePricePrediction
Solving the Famous House Price Challenge with Detailed Exploratory Data Analysis and Regression Techniques
# The Very Famous House Price Prediction Problem:

## Problem Statement: With 79 explanatory variables describing (almost) every aspect of

## residential homes in Ames, Iowa, this competition challenges you to predict the final price of

## each home.

### Linning up my Strategy to Win this Challenge:

```
1. Understand the problem by knowing your data
```
```
2. Univariate data analysis.
```
```
3. Multivariate data analysis.
```
```
4. Check for missing data.
```
```
5. Finding the outliers in the data.
```
```
6. Checking Skewness in the data.
```
```
7. Convert Categorical data items into numerical data items.
```
```
8. Scaling the data
```
```
9. Training Model on this data.
```
## Step 1: Understand the problem by knowing the data.

```
This Step involves having a look at the shape of the data, the content of the data, different type of datatypes present in the data. Also
```
```
gathering some knowledge about problem by studies articles, blogs, researches on market trends about this problem.
```
```
Index(['Id', 'MSSubClass', 'MSZoning', 'LotFrontage', 'LotArea', 'Street',
```
```
'Alley', 'LotShape', 'LandContour', 'Utilities', 'LotConfig',
```
```
'LandSlope', 'Neighborhood', 'Condition1', 'Condition2', 'BldgType',
```
```
'HouseStyle', 'OverallQual', 'OverallCond', 'YearBuilt', 'YearRemodAdd',
```
```
'RoofStyle', 'RoofMatl', 'Exterior1st', 'Exterior2nd', 'MasVnrType',
```
```
'MasVnrArea', 'ExterQual', 'ExterCond', 'Foundation', 'BsmtQual',
```
```
'BsmtCond', 'BsmtExposure', 'BsmtFinType1', 'BsmtFinSF1',
```
```
'BsmtFinType2', 'BsmtFinSF2', 'BsmtUnfSF', 'TotalBsmtSF', 'Heating',
```
```
'HeatingQC', 'CentralAir', 'Electrical', '1stFlrSF', '2ndFlrSF',
```
```
'LowQualFinSF', 'GrLivArea', 'BsmtFullBath', 'BsmtHalfBath', 'FullBath',
```
```
'HalfBath', 'BedroomAbvGr', 'KitchenAbvGr', 'KitchenQual',
```
```
'TotRmsAbvGrd', 'Functional', 'Fireplaces', 'FireplaceQu', 'GarageType',
```
```
'GarageYrBlt', 'GarageFinish', 'GarageCars', 'GarageArea', 'GarageQual',
```
```
'GarageCond', 'PavedDrive', 'WoodDeckSF', 'OpenPorchSF',
```
```
'EnclosedPorch', '3SsnPorch', 'ScreenPorch', 'PoolArea', 'PoolQC',
```
```
'Fence', 'MiscFeature', 'MiscVal', 'MoSold', 'YrSold', 'SaleType',
```
```
'SaleCondition', 'SalePrice'],
```
```
dtype='object')
```
```
<class 'pandas.core.frame.DataFrame'>
```
```
RangeIndex: 1460 entries, 0 to 1459
```
```
Data columns (total 81 columns):
```
```
# Column Non-Null Count Dtype
```
#### --- ------ -------------- -----

```
0 Id 1460 non-null int
```
```
1 MSSubClass 1460 non-null int
```
```
2 MSZoning 1460 non-null object
```
```
3 LotFrontage 1201 non-null float
```
```
4 LotArea 1460 non-null int
```
```
5 Street 1460 non-null object
```
```
6 Alley 91 non-null object
```
```
7 LotShape 1460 non-null object
```
```
8 LandContour 1460 non-null object
```
```
9 Utilities 1460 non-null object
```
```
10 LotConfig 1460 non-null object
```
```
11 LandSlope 1460 non-null object
```
```
12 Neighborhood 1460 non-null object
```
```
13 Condition1 1460 non-null object
```
```
14 Condition2 1460 non-null object
```
```
15 BldgType 1460 non-null object
```
```
16 HouseStyle 1460 non-null object
```
```
17 OverallQual 1460 non-null int
```
```
18 OverallCond 1460 non-null int
```
```
19 YearBuilt 1460 non-null int
```
```
20 YearRemodAdd 1460 non-null int
```
```
21 RoofStyle 1460 non-null object
```
```
22 RoofMatl 1460 non-null object
```
```
23 Exterior1st 1460 non-null object
```
```
24 Exterior2nd 1460 non-null object
```
```
25 MasVnrType 1452 non-null object
```
```
26 MasVnrArea 1452 non-null float
```
```
27 ExterQual 1460 non-null object
```
```
28 ExterCond 1460 non-null object
```
```
29 Foundation 1460 non-null object
```
```
30 BsmtQual 1423 non-null object
```
```
31 BsmtCond 1423 non-null object
```
```
32 BsmtExposure 1422 non-null object
```
```
33 BsmtFinType1 1423 non-null object
```
```
34 BsmtFinSF1 1460 non-null int
```
```
35 BsmtFinType2 1422 non-null object
```
```
36 BsmtFinSF2 1460 non-null int
```
```
37 BsmtUnfSF 1460 non-null int
```
```
38 TotalBsmtSF 1460 non-null int
```
```
39 Heating 1460 non-null object
```
```
40 HeatingQC 1460 non-null object
```
```
41 CentralAir 1460 non-null object
```
```
42 Electrical 1459 non-null object
```
```
43 1stFlrSF 1460 non-null int
```
```
44 2ndFlrSF 1460 non-null int
```
```
45 LowQualFinSF 1460 non-null int
```
```
46 GrLivArea 1460 non-null int
```
```
47 BsmtFullBath 1460 non-null int
```
```
48 BsmtHalfBath 1460 non-null int
```
```
49 FullBath 1460 non-null int
```
```
50 HalfBath 1460 non-null int
```
```
51 BedroomAbvGr 1460 non-null int
```
```
52 KitchenAbvGr 1460 non-null int
```
```
53 KitchenQual 1460 non-null object
```
```
54 TotRmsAbvGrd 1460 non-null int
```
```
55 Functional 1460 non-null object
```
```
56 Fireplaces 1460 non-null int
```
```
57 FireplaceQu 770 non-null object
```
```
58 GarageType 1379 non-null object
```
```
59 GarageYrBlt 1379 non-null float
```
```
60 GarageFinish 1379 non-null object
```
```
61 GarageCars 1460 non-null int
```
```
62 GarageArea 1460 non-null int
```
```
63 GarageQual 1379 non-null object
```
```
64 GarageCond 1379 non-null object
```
```
65 PavedDrive 1460 non-null object
```
```
66 WoodDeckSF 1460 non-null int
```
```
67 OpenPorchSF 1460 non-null int
```
```
68 EnclosedPorch 1460 non-null int
```
```
69 3SsnPorch 1460 non-null int
```
```
70 ScreenPorch 1460 non-null int
```
```
71 PoolArea 1460 non-null int
```
```
72 PoolQC 7 non-null object
```
```
73 Fence 281 non-null object
```
```
74 MiscFeature 54 non-null object
```
```
75 MiscVal 1460 non-null int
```
```
76 MoSold 1460 non-null int
```
```
77 YrSold 1460 non-null int
```
```
78 SaleType 1460 non-null object
```
```
79 SaleCondition 1460 non-null object
```
```
80 SalePrice 1460 non-null int
```
```
dtypes: float64(3), int64(35), object(43)
```
```
memory usage: 924.0+ KB
```
#### (1460, 81)

```
Index(['Id', 'MSSubClass', 'LotFrontage', 'LotArea', 'OverallQual',
```
```
'OverallCond', 'YearBuilt', 'YearRemodAdd', 'MasVnrArea', 'BsmtFinSF1',
```
```
'BsmtFinSF2', 'BsmtUnfSF', 'TotalBsmtSF', '1stFlrSF', '2ndFlrSF',
```
```
'LowQualFinSF', 'GrLivArea', 'BsmtFullBath', 'BsmtHalfBath', 'FullBath',
```
```
'HalfBath', 'BedroomAbvGr', 'KitchenAbvGr', 'TotRmsAbvGrd',
```
```
'Fireplaces', 'GarageYrBlt', 'GarageCars', 'GarageArea', 'WoodDeckSF',
```
```
'OpenPorchSF', 'EnclosedPorch', '3SsnPorch', 'ScreenPorch', 'PoolArea',
```
```
'MiscVal', 'MoSold', 'YrSold', 'SalePrice'],
```
```
dtype='object')
```
```
Index(['MSZoning', 'Street', 'Alley', 'LotShape', 'LandContour', 'Utilities',
```
```
'LotConfig', 'LandSlope', 'Neighborhood', 'Condition1', 'Condition2',
```
```
'BldgType', 'HouseStyle', 'RoofStyle', 'RoofMatl', 'Exterior1st',
```
```
'Exterior2nd', 'MasVnrType', 'ExterQual', 'ExterCond', 'Foundation',
```
```
'BsmtQual', 'BsmtCond', 'BsmtExposure', 'BsmtFinType1', 'BsmtFinType2',
```
```
'Heating', 'HeatingQC', 'CentralAir', 'Electrical', 'KitchenQual',
```
```
'Functional', 'FireplaceQu', 'GarageType', 'GarageFinish', 'GarageQual',
```
```
'GarageCond', 'PavedDrive', 'PoolQC', 'Fence', 'MiscFeature',
```
```
'SaleType', 'SaleCondition'],
```
```
dtype='object')
```
## Step 2: Univariate data analysis.

```
count 1460.
```
```
mean 180921.
```
```
std 79442.
```
```
min 34900.
```
#### 25% 129975.

#### 50% 163000.

#### 75% 214000.

```
max 755000.
```
```
Name: SalePrice, dtype: float
```
```
Observations drawn looking at the Histogram
```
```
Deviate from the normal distribution.
```
```
Have appreciable positive skewness.
```
```
Show peakedness.
```
```
Skewness: 1.
```
```
Kurtosis: 6.
```
## 3. Bivariate Data Analysis

### Analysing all Against Saleprice (target)

## Part 1: For Numerical Features

### Correlation: Finding How closely one variable relate with another i.e. How strongly the value of the variable

### increase or decrease with change in value of another variable

```
There is 10 strongly correlated value with SalePrice:
```
```
OverallQual 0.
```
```
GrLivArea 0.
```
```
GarageCars 0.
```
```
GarageArea 0.
```
```
TotalBsmtSF 0.
```
```
1stFlrSF 0.
```
```
FullBath 0.
```
```
TotRmsAbvGrd 0.
```
```
YearBuilt 0.
```
```
YearRemodAdd 0.
```
```
Name: SalePrice, dtype: float
```
```
There is 8 loosely correlated value with SalePrice:
```
```
YrSold -0.
```
```
LowQualFinSF -0.
```
```
Id -0.
```
```
MiscVal -0.
```
```
BsmtHalfBath -0.
```
```
BsmtFinSF2 -0.
```
```
3SsnPorch 0.
```
```
MoSold 0.
```
```
Name: SalePrice, dtype: float
```
### As Sale price value is almost independent of values of above variables, they might be excluded from analysis for

### prediction house prices, but let's look further before making any haste

### Plotting all Numerical Columns against Sale Price to get a more clear picture

```
We see that a lot of features have too many values zero, this might disrupt out calculations and conclusions of correlation
```
```
Looking at scatter plots excluding zero
```
```
I find 'OverallCond' is somehow linearly correlated to SalePrice
```
```
But 'LowQualFinSF','YrSold'','MiscVal','Id','BsmtHalfBath','BsmtFinSF2' still do not show any relation and are still eligible to be dropped
```
```
but let's do further analysis
```
## Part 2: For Categorical Features

#### RL 1151

#### RM 218

#### FV 65

#### RH 16

```
C (all) 10
```
```
Name: MSZoning, dtype: int
```
#### ##################################################

```
Pave 1454
```
```
Grvl 6
```
```
Name: Street, dtype: int
```
#### ##################################################

```
Grvl 50
```
```
Pave 41
```
```
Name: Alley, dtype: int
```
#### ##################################################

```
Reg 925
```
#### IR1 484

#### IR2 41

#### IR3 10

```
Name: LotShape, dtype: int
```
#### ##################################################

```
Lvl 1311
```
```
Bnk 63
```
#### HLS 50

```
Low 36
```
```
Name: LandContour, dtype: int
```
#### ##################################################

```
AllPub 1459
```
```
NoSeWa 1
```
```
Name: Utilities, dtype: int
```
#### ##################################################

```
Inside 1052
```
```
Corner 263
```
```
CulDSac 94
```
#### FR2 47

#### FR3 4

```
Name: LotConfig, dtype: int
```
#### ##################################################

```
Gtl 1382
```
```
Mod 65
```
```
Sev 13
```
```
Name: LandSlope, dtype: int
```
#### ##################################################

```
NAmes 225
```
```
CollgCr 150
```
```
OldTown 113
```
```
Edwards 100
```
```
Somerst 86
```
```
Gilbert 79
```
```
NridgHt 77
```
```
Sawyer 74
```
```
NWAmes 73
```
```
SawyerW 59
```
```
BrkSide 58
```
```
Crawfor 51
```
```
Mitchel 49
```
```
NoRidge 41
```
```
Timber 38
```
#### IDOTRR 37

```
ClearCr 28
```
#### SWISU 25

```
StoneBr 25
```
```
Blmngtn 17
```
```
MeadowV 17
```
```
BrDale 16
```
```
Veenker 11
```
```
NPkVill 9
```
```
Blueste 2
```
```
Name: Neighborhood, dtype: int
```
#### ##################################################

```
Norm 1260
```
```
Feedr 81
```
```
Artery 48
```
```
RRAn 26
```
```
PosN 19
```
```
RRAe 11
```
```
PosA 8
```
```
RRNn 5
```
```
RRNe 2
```
```
Name: Condition1, dtype: int
```
#### ##################################################

```
Norm 1445
```
```
Feedr 6
```
```
PosN 2
```
```
Artery 2
```
```
RRNn 2
```
```
PosA 1
```
```
RRAn 1
```
```
RRAe 1
```
```
Name: Condition2, dtype: int
```
#### ##################################################

```
1Fam 1220
```
```
TwnhsE 114
```
```
Duplex 52
```
```
Twnhs 43
```
```
2fmCon 31
```
```
Name: BldgType, dtype: int
```
#### ##################################################

```
1Story 726
```
```
2Story 445
```
```
1.5Fin 154
```
```
SLvl 65
```
```
SFoyer 37
```
```
1.5Unf 14
```
```
2.5Unf 11
```
```
2.5Fin 8
```
```
Name: HouseStyle, dtype: int
```
#### ##################################################

```
Gable 1141
```
```
Hip 286
```
```
Flat 13
```
```
Gambrel 11
```
```
Mansard 7
```
```
Shed 2
```
```
Name: RoofStyle, dtype: int
```
#### ##################################################

```
CompShg 1434
```
```
Tar&Grv 11
```
```
WdShngl 6
```
```
WdShake 5
```
```
Roll 1
```
```
Membran 1
```
```
ClyTile 1
```
```
Metal 1
```
```
Name: RoofMatl, dtype: int
```
#### ##################################################

```
VinylSd 515
```
```
HdBoard 222
```
```
MetalSd 220
```
```
Wd Sdng 206
```
```
Plywood 108
```
```
CemntBd 61
```
```
BrkFace 50
```
```
WdShing 26
```
```
Stucco 25
```
```
AsbShng 20
```
```
BrkComm 2
```
```
Stone 2
```
```
CBlock 1
```
```
AsphShn 1
```
```
ImStucc 1
```
```
Name: Exterior1st, dtype: int
```
#### ##################################################

```
VinylSd 504
```
```
MetalSd 214
```
```
HdBoard 207
```
```
Wd Sdng 197
```
```
Plywood 142
```
```
CmentBd 60
```
```
Wd Shng 38
```
```
Stucco 26
```
```
BrkFace 25
```
```
AsbShng 20
```
```
ImStucc 10
```
```
Brk Cmn 7
```
```
Stone 5
```
```
AsphShn 3
```
```
CBlock 1
```
```
Other 1
```
```
Name: Exterior2nd, dtype: int
```
#### ##################################################

```
None 864
```
```
BrkFace 445
```
```
Stone 128
```
```
BrkCmn 15
```
```
Name: MasVnrType, dtype: int
```
#### ##################################################

#### TA 906

```
Gd 488
```
```
Ex 52
```
```
Fa 14
```
```
Name: ExterQual, dtype: int
```
#### ##################################################

#### TA 1282

```
Gd 146
```
```
Fa 28
```
```
Ex 3
```
```
Po 1
```
```
Name: ExterCond, dtype: int
```
#### ##################################################

```
PConc 647
```
```
CBlock 634
```
```
BrkTil 146
```
```
Slab 24
```
```
Stone 6
```
```
Wood 3
```
```
Name: Foundation, dtype: int
```
#### ##################################################

#### TA 649

```
Gd 618
```
```
Ex 121
```
```
Fa 35
```
```
Name: BsmtQual, dtype: int
```
#### ##################################################

#### TA 1311

```
Gd 65
```
```
Fa 45
```
```
Po 2
```
```
Name: BsmtCond, dtype: int
```
#### ##################################################

```
No 953
```
```
Av 221
```
```
Gd 134
```
```
Mn 114
```
```
Name: BsmtExposure, dtype: int
```
#### ##################################################

```
Unf 430
```
#### GLQ 418

#### ALQ 220

#### BLQ 148

```
Rec 133
```
```
LwQ 74
```
```
Name: BsmtFinType1, dtype: int
```
#### ##################################################

```
Unf 1256
```
```
Rec 54
```
```
LwQ 46
```
#### BLQ 33

#### ALQ 19

#### GLQ 14

```
Name: BsmtFinType2, dtype: int
```
#### ##################################################

```
GasA 1428
```
```
GasW 18
```
```
Grav 7
```
```
Wall 4
```
```
OthW 2
```
```
Floor 1
```
```
Name: Heating, dtype: int
```
#### ##################################################

```
Ex 741
```
#### TA 428

```
Gd 241
```
```
Fa 49
```
```
Po 1
```
```
Name: HeatingQC, dtype: int
```
#### ##################################################

#### Y 1365

#### N 95

```
Name: CentralAir, dtype: int
```
#### ##################################################

```
SBrkr 1334
```
```
FuseA 94
```
```
FuseF 27
```
```
FuseP 3
```
```
Mix 1
```
```
Name: Electrical, dtype: int
```
#### ##################################################

#### TA 735

```
Gd 586
```
```
Ex 100
```
```
Fa 39
```
```
Name: KitchenQual, dtype: int
```
#### ##################################################

```
Typ 1360
```
```
Min2 34
```
```
Min1 31
```
```
Mod 15
```
```
Maj1 14
```
```
Maj2 5
```
```
Sev 1
```
```
Name: Functional, dtype: int
```
#### ##################################################

```
Gd 380
```
#### TA 313

```
Fa 33
```
```
Ex 24
```
```
Po 20
```
```
Name: FireplaceQu, dtype: int
```
#### ##################################################

```
Attchd 870
```
```
Detchd 387
```
```
BuiltIn 88
```
```
Basment 19
```
```
CarPort 9
```
```
2Types 6
```
```
Name: GarageType, dtype: int
```
#### ##################################################

```
Unf 605
```
```
RFn 422
```
```
Fin 352
```
```
Name: GarageFinish, dtype: int
```
#### ##################################################

#### TA 1311

```
Fa 48
```
```
Gd 14
```
```
Po 3
```
```
Ex 3
```
```
Name: GarageQual, dtype: int
```
#### ##################################################

#### TA 1326

```
Fa 35
```
```
Gd 9
```
```
Po 7
```
```
Ex 2
```
```
Name: GarageCond, dtype: int
```
#### ##################################################

#### Y 1340

#### N 90

#### P 30

```
Name: PavedDrive, dtype: int
```
#### ##################################################

```
Gd 3
```
```
Fa 2
```
```
Ex 2
```
```
Name: PoolQC, dtype: int
```
#### ##################################################

```
MnPrv 157
```
```
GdPrv 59
```
```
GdWo 54
```
```
MnWw 11
```
```
Name: Fence, dtype: int
```
#### ##################################################

```
Shed 49
```
```
Othr 2
```
```
Gar2 2
```
```
TenC 1
```
```
Name: MiscFeature, dtype: int
```
#### ##################################################

#### WD 1267

```
New 122
```
#### COD 43

```
ConLD 9
```
```
ConLw 5
```
```
ConLI 5
```
#### CWD 4

```
Oth 3
```
```
Con 2
```
```
Name: SaleType, dtype: int
```
#### ##################################################

```
Normal 1198
```
```
Partial 125
```
```
Abnorml 101
```
```
Family 20
```
```
Alloca 12
```
```
AdjLand 4
```
```
Name: SaleCondition, dtype: int
```
#### ##################################################

### Plotting Box Plots which are Generally Good Visual representation to Observe how categorical values are

### distributed

```
Id MSSubClass MSZoning LotFrontage LotArea Street Alley LotShape LandContour Utilities LotConfig LandSlope Neighborhood C
```
```
0 1 60 RL 65.0 8450 Pave NaN Reg Lvl AllPub Inside Gtl CollgCr
```
```
1 2 20 RL 80.0 9600 Pave NaN Reg Lvl AllPub FR2 Gtl Veenker
```
```
2 3 60 RL 68.0 11250 Pave NaN IR1 Lvl AllPub Inside Gtl CollgCr
```
```
3 4 70 RL 60.0 9550 Pave NaN IR1 Lvl AllPub Corner Gtl Crawfor
```
```
4 5 60 RL 84.0 14260 Pave NaN IR1 Lvl AllPub FR2 Gtl NoRidge
```
```
Id MSSubClass LotFrontage LotArea OverallQual OverallCond YearBuilt YearRemodAdd MasVnrArea BsmtFinSF
```
```
count 1460.000000 1460.000000 1201.000000 1460.000000 1460.000000 1460.000000 1460.000000 1460.000000 1452.000000 1460.
```
```
mean 730.500000 56.897260 70.049958 10516.828082 6.099315 5.575342 1971.267808 1984.865753 103.685262 443.
```
```
std 421.610009 42.300571 24.284752 9981.264932 1.382997 1.112799 30.202904 20.645407 181.066207 456.
```
```
min 1.000000 20.000000 21.000000 1300.000000 1.000000 1.000000 1872.000000 1950.000000 0.000000 0.
```
```
25% 365.750000 20.000000 59.000000 7553.500000 5.000000 5.000000 1954.000000 1967.000000 0.000000 0.
```
```
50% 730.500000 50.000000 69.000000 9478.500000 6.000000 5.000000 1973.000000 1994.000000 0.000000 383.
```
```
75% 1095.250000 70.000000 80.000000 11601.500000 7.000000 6.000000 2000.000000 2004.000000 166.000000 712.
```
```
max 1460.000000 190.000000 313.000000 215245.000000 10.000000 9.000000 2010.000000 2010.000000 1600.000000 5644.
```
```
Id MSSubClass LotFrontage LotArea OverallQual OverallCond YearBuilt YearRemodAdd MasVnrArea BsmtFinSF1 BsmtFinSF2 BsmtUn
```
```
0 1 60 65.0 8450 7 5 2003 2003 196.0 706 0 1
```
```
1 2 20 80.0 9600 6 8 1976 1976 0.0 978 0 2
```
```
2 3 60 68.0 11250 7 5 2001 2002 162.0 486 0 4
```
```
3 4 70 60.0 9550 7 5 1915 1970 0.0 216 0 5
```
```
4 5 60 84.0 14260 8 5 2000 2000 350.0 655 0 4
```
In [117...
_#importing useful libraries_

```
import pandas as pd
```
```
import matplotlib.pyplot as plt
```
```
import seaborn as sns
```
```
import numpy as np
```
```
from scipy.stats import norm
```
```
from sklearn.preprocessing import StandardScaler
```
```
from sklearn.linear_model import LinearRegression
```
```
from sklearn.model_selection import train_test_split
```
```
from scipy import stats
```
```
import warnings
```
```
warnings. filterwarnings('ignore')
```
```
%matplotlib inline
```
```
pd. set_option('display.max_columns', None )
```
In [118...
df_train **=** pd**.** read_csv('./train.csv')

```
df_test = pd. read_csv('./test.csv')
```
In [119...
_# Getting names of all the columns in the dataset_

```
df_train. columns
```
Out[119...

In [120...
_# Printing the first 5 Rows of the data_

```
df_train. head( 5 )
```
Out[120...

In [121...
_# Getting information about each Column in the data_

```
df_train. info()
```
In [122...
_# Getting a statistical picture of the data items in terms of count, mean, standard deviation, distribution of_

```
df_train. describe()
```
Out[122...

In [123...
df_train**.** shape

Out[123...

In [124...
_# Numerical Features_

```
num_feat = df_train. select_dtypes(exclude = ['object']). columns
```
```
print(num_feat)
```
In [125...
_# Categorical Features_

```
cat_feat = df_train. select_dtypes(include = ['object']). columns
```
```
print(cat_feat)
```
In [126...
_# For the variable Saleprice, understanding its values using different statistical terms like_

```
# mean, count, standard deviation
```
```
df_train['SalePrice']. describe()
```
Out[126...

In [127...
_#plotting a histogram to check how the different values of saleprice are distributed_

```
sns. distplot(df_train['SalePrice']);
```
In [128...
_#skewness and kurtosis_

```
print("Skewness: %f" % df_train['SalePrice']. skew())
```
```
print("Kurtosis: %f" % df_train['SalePrice']. kurt())
```
In [129...
_# Filtering out the numerical features in a different data frame_

```
df_train_num = df_train[num_feat]
```
```
df_train_num. head( 5 )
```
Out[129...

In [130...
_# Checking the variables whose absolute correlation with Saleprice is more than 0._

```
df_corr = df_train_num. corr()['SalePrice'][: - 1 ]
```
```
high_corr_feat = df_corr[abs(df_corr) > 0.5]. sort_values(ascending =False )
```
```
print("There is {} strongly correlated value with SalePrice:\n{}". format(len(high_corr_feat), high_corr_feat))
```
In [131...
_# Checking the variables whose absolute correlation with Saleprice is less than 0._

```
less_corr_feat = df_corr[abs(df_corr) < 0.05]. sort_values(ascending =True )
```
```
print("There is {} loosely correlated value with SalePrice:\n{}". format(len(less_corr_feat), less_corr_feat))
```
In [132...
**for** i **in** range( 0 , len(df_train_num**.** columns), 5 ):

```
sns. pairplot(data = df_train_num,
```
```
x_vars = df_train_num. columns[i:i + 5 ],
```
```
y_vars = ['SalePrice'])
```
In [133...
_# Getting list of different categories which each categorical feature belong too_

```
for catg in list(cat_feat) :
```
```
print(df_train[catg]. value_counts())
```
```
print('#' * 50 )
```
In [134...
li_cat_feats **=** list(cat_feat)

```
nr_rows = 12
```
```
nr_cols = 2
```
```
fig, axs = plt. subplots(nr_rows, nr_cols, figsize = (nr_cols * 7 ,nr_rows * 4 ))
```
```
for r in range( 0 ,nr_rows):
```
```
for c in range( 0 ,nr_cols):
```
```
i = r * nr_cols + c
```
```
if i < len(li_cat_feats):
```
```
sns. boxplot(x = li_cat_feats[i], y = 'SalePrice', data = df_train, ax = axs[r][c])
```
```
plt. tight_layout()
```
```
plt. show()
```

### Many Good Conclusions can be Drawn From this :

### House in Pave Street are Costilier than house in Grvl street.

### House with Central air are Costilier than house without central air.

### Many Categorical Featues like Electrical, heatingQC, BsmtFinType1 and many more are much helpful in

### classifying the house to a specific price segment.

### Many features have outliers which will require treatment

## Step 4: Multivariate Data Analysis

### This Step involves learning relationships between every pair of variable in dataset

### Best place to start with is to draw a Correlation Matrix (heatmap) filtering pairs which have high absolute

### correlation

### Observations:

### Below features have Shown high correlation to one another:

```
#### 'GrLivArea' and 'TotRmsAbvGrd' #### 'GarageCars' and 'GarageArea' #### 'TotalBsmtSF' and '1stFlrSF' #### 'YearBuilt' and
```
```
'GarageYrBlt' #### Of these similar features we drop the one that has smaller correlation coeffiecient to Target.
```
```
<AxesSubplot:>
```
### Therefore Marked for Dropping are:

### GrLivArea, TotRmsAbvGrd, GarageArea, 1stFlrSF, GarageYrBlt

### from Before

### 'LowQualFinSF','YrSold'','MiscVal','Id','BsmtHalfBath','BsmtFinSF2'

## Step 5: Missing Data Analysis

```
Total Percent
```
```
PoolQC 1453 99.
```
```
MiscFeature 1406 96.
```
```
Alley 1369 93.
```
```
Fence 1179 80.
```
```
FireplaceQu 690 47.
```
```
LotFrontage 259 17.
```
```
GarageYrBlt 81 5.
```
```
GarageCond 81 5.
```
```
GarageType 81 5.
```
```
GarageFinish 81 5.
```
```
GarageQual 81 5.
```
```
BsmtFinType2 38 2.
```
```
BsmtExposure 38 2.
```
```
BsmtQual 37 2.
```
```
BsmtCond 37 2.
```
```
BsmtFinType1 37 2.
```
```
MasVnrArea 8 0.
```
```
MasVnrType 8 0.
```
```
Electrical 1 0.
```
```
Id 0 0.
```
### Filling missing values

### For a few columns there is lots of NaN entries.

### However, reading the data description we find this is not missing data:

### For PoolQC, NaN is not missing data but means no pool, likewise for Fence, FireplaceQu etc

#### (2919, 80)

#### (1460, 81)

#### (1460,)

### MSZoning, Utilities, Exteriors, Electrical, Functional, Utilities and SaleType

### There are not many missing values, so we will just go with the mode of the neighbourhood.

### Lot frontage

### My best guess is that it depends somewhat strongly on the configuration of the lot (inside/corner/cul/2-

### frontage/3-frontage).

### KitchenQual

### Again, very few missing values. We will substitute in this case with the 'OverallQual' value.

### Basement, garage, fireplaces and other features

### We can interpret an NA in all these things as "the house does not have this feature".

#### (2919, 80)

#### (2919, 81)

#### (2919, 81)

```
Total Percent
```
```
Id 0.0 0.
```
```
MSSubClass 0.0 0.
```
```
GarageType 0.0 0.
```
```
FireplaceQu 0.0 0.
```
```
Fireplaces 0.0 0.
```
```
Functional 0.0 0.
```
```
TotRmsAbvGrd 0.0 0.
```
```
KitchenQual 0.0 0.
```
```
KitchenAbvGr 0.0 0.
```
```
BedroomAbvGr 0.0 0.
```
```
HalfBath 0.0 0.
```
```
FullBath 0.0 0.
```
```
BsmtHalfBath 0.0 0.
```
```
BsmtFullBath 0.0 0.
```
```
GrLivArea 0.0 0.
```
```
LowQualFinSF 0.0 0.
```
```
2ndFlrSF 0.0 0.
```
```
1stFlrSF 0.0 0.
```
```
Electrical 0.0 0.
```
```
GarageYrBlt 0.0 0.
```
### All Missing Data has been Dealth with

#### (2919, 69)

```
Index(['MSSubClass', 'MSZoning', 'LotFrontage', 'LotArea', 'Street', 'Alley',
```
```
'LotShape', 'LandContour', 'Utilities', 'LotConfig', 'LandSlope',
```
```
'Neighborhood', 'Condition1', 'Condition2', 'BldgType', 'HouseStyle',
```
```
'OverallQual', 'OverallCond', 'YearBuilt', 'YearRemodAdd', 'RoofStyle',
```
```
'RoofMatl', 'Exterior1st', 'Exterior2nd', 'MasVnrType', 'MasVnrArea',
```
```
'ExterQual', 'ExterCond', 'Foundation', 'BsmtQual', 'BsmtCond',
```
```
'BsmtExposure', 'BsmtFinType1', 'BsmtFinSF1', 'BsmtFinType2',
```
```
'BsmtUnfSF', 'TotalBsmtSF', 'Heating', 'HeatingQC', 'CentralAir',
```
```
'Electrical', '2ndFlrSF', 'BsmtFullBath', 'FullBath', 'HalfBath',
```
```
'BedroomAbvGr', 'KitchenAbvGr', 'KitchenQual', 'Functional',
```
```
'Fireplaces', 'FireplaceQu', 'GarageType', 'GarageFinish', 'GarageCars',
```
```
'GarageQual', 'GarageCond', 'PavedDrive', 'WoodDeckSF', 'OpenPorchSF',
```
```
'EnclosedPorch', '3SsnPorch', 'ScreenPorch', 'PoolArea', 'PoolQC',
```
```
'Fence', 'MiscFeature', 'MoSold', 'SaleType', 'SaleCondition'],
```
```
dtype='object')
```
```
Adjusting the type of variable First, there are a few features that are not represented with the right type of variable:
```
```
'MSSubClass': represented as an integer, when it is just a category label (we will use 'object' for now) 'MoSold': represented as an integer, a
```
```
month is just a category label out of 12 possibilities (we will use 'object' for now) 'BsmtFullBath', 'BsmtHalfBath': these two represent
```
```
integers and not floats (or I at least I do not know what a third of half bathroom is) years: a year, in the context of this dataset, is an integer,
```
```
and not a float 'GarageCars': represented as a float, it is an actual integer (nobody wants to have 0.5 car at home)
```
## Step 6: Finding the Outliers in the data

### Outlier handling is done using the mean and the standard deviation. We have taken three features which have

### highest correlation to the sale price based on which outliers have been removed.

#### (2919, 319)

## Step 7: Finding Skewness in Data

```
The point here is to test 'SalePrice' in a very lean way. We'll do this paying attention to:
```
```
We will draw boxplot - Kurtosis and skewness. Normal probability plot - Data distribution should closely follow the diagonal that
```
```
represents the normal distribution.
```
```
PoolArea 18.
```
```
LotArea 13.
```
```
3SsnPorch 11.
```
```
KitchenAbvGr 4.
```
```
EnclosedPorch 4.
```
```
ScreenPorch 3.
```
```
MasVnrArea 2.
```
```
OpenPorchSF 2.
```
```
WoodDeckSF 1.
```
```
LotFrontage 1.
```
```
BsmtFinSF1 0.
```
```
BsmtUnfSF 0.
```
```
2ndFlrSF 0.
```
```
Fireplaces 0.
```
```
HalfBath 0.
```
```
BsmtFullBath 0.
```
```
OverallCond 0.
```
```
age 0.
```
```
TotalBsmtSF 0.
```
```
BedroomAbvGr 0.
```
```
OverallQual 0.
```
```
FullBath 0.
```
```
GarageCars -0.
```
```
YearRemodAdd -0.
```
```
YearBuilt -0.
```
```
dtype: float
```
### Let's visualize skewed variable using boxplots and distplot

In [135...
corr **=** df_train_num**.** drop('SalePrice', axis **=** 1 )**.** corr() _# We already examined SalePrice correlations_

```
plt. figure(figsize = ( 30 , 10 ))
```
```
sns. heatmap(corr[(corr >= 0.5) | (corr <= - 0.4)],
```
```
cmap = 'viridis', vmax = 1.0, vmin =- 1.0, linewidths = 0.1,
```
```
annot =True , annot_kws = {"size": 8 }, square =True );
```
In [136...
df_temp **=** df_train[['SalePrice','GrLivArea','TotRmsAbvGrd','GarageCars','GarageArea','TotalBsmtSF','1stFlrSF','Ye

```
df_temp. corr()['SalePrice']. plot(kind = 'bar')
```
Out[136...

In [137...
_# Finding the Percentage of values missing_

```
total = df_train. isnull(). sum(). sort_values(ascending =False )
```
```
percent = (df_train. isnull(). sum() * 100 / df_train. isnull(). count()). sort_values(ascending =False )
```
```
missing_data = pd. concat([total, percent], axis = 1 , keys = ['Total', 'Percent'])
```
```
missing_data. head( 20 )
```
Out[137...

In [138...
df_train['SalePrice'] **=** np**.** log1p(df_train['SalePrice'])

In [148...
df_train1 **=** df_train**.** drop('SalePrice',axis **=** 1 )

```
df_all = pd. concat([df_train1,df_test]). reset_index(drop =True )
```
```
df_all. shape
```
Out[148...

In [140...
df_train**.** shape

Out[140...

In [77]:
y_train **=** df_train['SalePrice']

```
y_train. shape
```
Out[77]:

In [150...
feats **=** ['MSZoning', 'Utilities', 'Exterior1st', 'Exterior2nd', 'Electrical', 'Functional',

```
'SaleType']
```
```
model = df_train. groupby('Neighborhood')[feats]. apply( lambda x: x. mode(). iloc[ 0 ])
```
```
for f in feats:
```
```
df_all[f]. fillna(df_all['Neighborhood']. map(model[f]), inplace =True )
```
In [153...
df_all['LotFrontage'] **=** df_all['LotFrontage']**.** fillna(df_train['LotFrontage']**.** median())

In [154...
df_all['KitchenQual']**.** fillna(df_all['OverallQual'], inplace **=True** )

In [155...
bsmt **=** ['BsmtQual', 'BsmtCond', 'BsmtExposure', 'BsmtFinType1',

```
'BsmtFinSF1', 'BsmtFinType2', 'BsmtFinSF2', 'BsmtUnfSF', 'BsmtFullBath',
```
```
'BsmtHalfBath',
```
```
'TotalBsmtSF']
```
```
fire = ['Fireplaces', 'FireplaceQu']
```
```
garage = ['GarageQual', 'GarageCond', 'GarageType', 'GarageFinish', 'GarageCars',
```
```
'GarageArea', 'GarageYrBlt']
```
```
masn = ['MasVnrType', 'MasVnrArea']
```
```
others = ['Alley', 'Fence', 'PoolQC', 'MiscFeature']
```
```
cats = df_all. columns[df_all. dtypes == 'object']
```
```
nums = list(set(df_all. columns) - set(cats))
```
```
# Be sure the category 'None' is also handled here
```
```
df_all['MasVnrType']. replace({'None': np. nan}, inplace =True )
```
```
df_all[cats] = df_all[cats]. fillna('0')
```
```
df_all[nums] = df_all[nums]. fillna( 0 )
```
In [156...
df_all**.** shape

Out[156...

In [78]:
df_all['age'] **=** df_all['YrSold'] **-** df_all['YearBuilt']

```
# Some of the non-numeric predictors are stored as numbers; convert them into strings
```
```
#will convert those columns into dummy variables later.
```
```
df_all[['MSSubClass']] = df_all[['MSSubClass']]. astype(str)
```
```
df_all['YrSold'] = df_all['YrSold']. astype(str) #year
```
```
df_all['MoSold'] = df_all['MoSold']. astype(str) #month
```
```
df_all. shape
```
Out[78]:

In [79]:
df_all['GarageCars'] **=** df_all['GarageCars']**.** fillna(df_all**.** groupby('GarageArea')['GarageCars']**.** transform('mean')

```
df_all['GrLivArea'] = df_all['GrLivArea']. fillna(df_all. groupby('TotRmsAbvGrd')['GrLivArea']. transform('mean'))
```
```
df_all['TotalBsmtSF'] = df_all['TotalBsmtSF']. fillna(df_all. groupby('1stFlrSF')['TotalBsmtSF']. transform('mean'
```
```
df_all['GarageYrBlt'] = df_all['GarageYrBlt']. fillna(df_all. groupby('YearBuilt')['GarageYrBlt']. transform('mean
```
In [80]:
_#Functional: Home functionality (Assume typical unless deductions are warranted)_

```
df_all['Functional'] = df_all['Functional']. fillna('Typ')
```
```
df_all['Electrical'] = df_all['Electrical']. fillna('SBrkr') #Filling with modef
```
```
# data description states that NA refers to "No Pool"
```
```
df_all["PoolQC"] = df_all["PoolQC"]. fillna("None")
```
```
# Replacing the missing values with 0, since no garage = no cars in garage inferred from data dictionary
```
```
df_all['GarageYrBlt'] = df_all['GarageYrBlt']. fillna( 0 )
```
```
df_all['KitchenQual'] = df_all['KitchenQual']. fillna("TA")
```
```
df_all['Exterior1st'] = df_all['Exterior1st']. fillna(df_all['Exterior1st']. mode()[ 0 ])
```
```
df_all['Exterior2nd'] = df_all['Exterior2nd']. fillna(df_all['Exterior2nd']. mode()[ 0 ])
```
```
df_all['SaleType'] = df_all['SaleType']. fillna(df_all['SaleType']. mode()[ 0 ])
```
```
# Replacing the missing values with None inferred from data dictionary
```
```
for col in ['GarageType', 'GarageFinish', 'GarageQual', 'GarageCond']:
```
```
df_all[col] = df_all[col]. fillna('None')
```
```
# Replacing the missing values with None
```
```
# NaN values for these categorical basement df_all, means there's no basement
```
```
for col in ('BsmtQual', 'BsmtCond', 'BsmtExposure', 'BsmtFinType1', 'BsmtFinType2'):
```
```
df_all[col] = df_all[col]. fillna('None')
```
```
#Replacing missing value it with median beacuse of outliers
```
```
df_all['LotFrontage'] = df_all. groupby('Neighborhood')['LotFrontage']. transform( lambda x: x. fillna(x. median()))
```
```
# Replacing the missing values with None
```
```
# We have no particular intuition around how to fill in the rest of the categorical df_all
```
```
# So we replace their missing values with None
```
```
objects = []
```
```
for i in df_all. columns:
```
```
if df_all[i]. dtype == object:
```
```
objects. append(i)
```
```
df_all. update(df_all[objects]. fillna('None'))
```
```
numeric_dtypes = [ 'int64','float64']
```
```
numerics = []
```
```
for i in df_all. columns:
```
```
if df_all[i]. dtype in numeric_dtypes:
```
```
numerics. append(i)
```
```
df_all. update(df_all[numerics]. fillna( 0 ))
```
```
df_all['MSZoning'] = df_all. groupby('MSSubClass')['MSZoning']. transform( lambda x: x. fillna(x. mode()[ 0 ]))
```
```
df_all['LotFrontage'] = df_all['LotFrontage']. transform( lambda x: x. fillna(x. median()))
```
In [81]:
df_all**.** shape

Out[81]:

In [157...
_#missing data_

```
total = df_all. isnull(). sum(). sort_values(ascending =False )
```
```
percent = (df_all. isnull(). sum() * 100 / df_train. isnull(). count()). sort_values(ascending =False )
```
```
missing_data = pd. concat([total, percent], axis = 1 , keys = ['Total', 'Percent'])
```
```
missing_data. head( 20 )
```
Out[157...

In [158...
_#Now Dropping the Columns we have Marked for deletion_

```
df_all = df_all. drop(['GrLivArea','TotRmsAbvGrd','GarageArea','1stFlrSF','GarageYrBlt','LowQualFinSF','YrSold','M
```
In [159...
df_all**.** shape

Out[159...

In [160...
df_all**.** columns

Out[160...

In [165...
years **=** ['YearBuilt', 'YearRemodAdd']

```
df_all['MSSubClass'] = df_all['MSSubClass']. astype('object', copy =False )
```
```
df_all['MoSold'] = df_all['MoSold']. astype('object', copy =False )
```
```
df_all['BsmtFullBath'] = df_all['BsmtFullBath']. astype('int64', copy =False )
```
```
df_all['GarageCars'] = df_all['GarageCars']. astype('int64', copy =False )
```
```
df_all[years] = df_all[years]. astype('int64', copy =False )
```
In [86]:
outlier_features **=** ["OverallQual","GarageCars","TotalBsmtSF"]

```
means,sds = np. mean(df_all[outlier_features]),np. std(df_all[outlier_features])
```
```
lower,upper = means - 2.5 * sds , means + 2.5 * sds
```
```
def compare(x):
```
```
count = 0
```
```
for col in outlier_features:
```
```
if x[col] > lower[col] and x[col] < upper[col]:
```
```
count = count + 1
```
```
if count == len(outlier_features):
```
```
return True
```
```
else :
```
```
return False
```
```
index = len(df_train)
```
```
y = y_train. array
```
```
sub_data = df_all. loc[:index - 1 ]
```
```
test_1 = df_all. loc[index:,:]
```
```
data_train_new = sub_data. loc[sub_data. apply( lambda x: compare(x),axis = 1 )]
```
```
y = y[sub_data. apply( lambda x: compare(x),axis = 1 )]
```
```
index = len(data_train_new)
```
```
df_all = pd. concat([data_train_new,test_1]). reset_index(drop =True )
```
In [170...
df_all**.** shape

Out[170...

In [87]:
**from** scipy.stats **import** skew,boxcox_normmax

```
from scipy.special import boxcox1p
```
```
df_all_num = df_all. select_dtypes(include = ['int64','float64'])
```
```
skew_features = df_all_num. apply( lambda x: skew(x)). sort_values(ascending =False )
```
```
high_skew = skew_features[skew_features > 0.5]
```
```
skew_index = high_skew. index
```
```
skewness = pd. DataFrame({'Skew' :high_skew})
```
```
skew_features
```
Out[87]:

In [88]:
f, ax **=** plt**.** subplots(figsize **=** ( 8 , 7 ))

```
ax. set_xscale("log")
```
```
ax = sns. boxplot(data = df_all_num , orient = "h", palette = "Set1")
```
```
ax. xaxis. grid( False )
```
```
ax. set(ylabel = "Feature names")
```
```
ax. set(xlabel = "Numeric values")
```
```
ax. set(title = "Numeric Distribution of Features")
```
```
sns. despine(trim =True , left =True )
```
In [89]:
num_feat **=** df_all**.** select_dtypes(exclude **=** ['object'])**.** columns

```
li_num_feats = list(num_feat)
```
```
nr_rows = 15
```
```
nr_cols = 2
```
```
df_all_copy = df_all. copy()
```
```
fig, axs = plt. subplots(nr_rows, nr_cols, figsize = (nr_cols * 7 ,nr_rows * 4 ))
```
```
for r in range( 0 ,nr_rows):
```
```
for c in range( 0 ,nr_cols):
```
```
i = r * nr_cols + c
```
```
if i < len(li_num_feats):
```
```
sns. distplot(df_all[li_num_feats[i]],ax = axs[r][c]);
```
```
plt. tight_layout()
```
```
plt. show()
```

```
PoolArea 16.
```
```
3SsnPorch 8.
```
```
KitchenAbvGr 3.
```
```
ScreenPorch 3.
```
```
EnclosedPorch 2.
```
```
MasVnrArea 0.
```
```
2ndFlrSF 0.
```
```
WoodDeckSF 0.
```
```
HalfBath 0.
```
```
BsmtFullBath 0.
```
```
OpenPorchSF 0.
```
```
Fireplaces 0.
```
```
OverallCond 0.
```
```
BsmtFinSF1 0.
```
```
BedroomAbvGr 0.
```
```
TotalBsmtSF 0.
```
```
OverallQual 0.
```
```
FullBath 0.
```
```
LotFrontage 0.
```
```
BsmtUnfSF 0.
```
```
age 0.
```
```
LotArea -0.
```
```
GarageCars -0.
```
```
YearRemodAdd -0.
```
```
YearBuilt -0.
```
```
dtype: float
```
### Rechecking if skewness is fixed

## Step 8: Converting Categorical Values into Numerical Values

#### (2919, 319)

## Step 9: Scaling the Data

```
Scaler class: Machine learning algorithm that works on numbers does not know what that number represents. A weight of 10 grams and a
```
```
price of 10 dollars are two different things, but for mode it is the just the same numbers.
```
```
The problem is that if 1 feature is much bigger than other feature, then the assumption algorithm makes that since first feature is bigger
```
```
than second one, than it is more important.
```
```
We can solve this problem by getting all features in same not big range. Let's say −1≤xi≤1 , where xi is a feature
```
```
There are many scalers, but we will be using Min-Max scaler.
```
```
xnew=x−xminxmax−xmin
```
```
MinMaxScaler scales all the data features in the range [0,1]
```
## Step 10: Training Models on this data.

## A.LinearRegression

```
coefficient of determination - rsquare - on training data : 0.
```
```
TotalBsmtSF.............. 1.5517e-
```
```
RoofMatl_ClyTile......... -2.1815e+
```
```
2ndFlrSF................. 9.8110e-
```
```
OverallQual.............. 6.0376e-
```
```
GarageCars............... 2.8345e-
```
## B. Linear regression, L1 regularisation¶

```
LassoCV()
```
```
LotFrontage LotArea OverallQual OverallCond YearBuilt YearRemodAdd MasVnrArea BsmtFinSF1 BsmtUnfSF TotalBsmtSF 2ndFlrSF Bs
```
```
0 65.0 8450 7 5 2003 2003 196.0 706.0 150.0 856.0 854
```
```
1 80.0 9600 6 8 1976 1976 0.0 978.0 284.0 1262.0 0
```
```
2 68.0 11250 7 5 2001 2002 162.0 486.0 434.0 920.0 866
```
In [90]:
_# Normalize skewed features using a Box-Cox power transformation, we can use other techniques but am using boxp_

```
# as it works very well on this dataset
```
```
for i in skew_index:
```
```
df_all[i] = boxcox1p(df_all[i], boxcox_normmax(df_all[i] + 1.002))
```
In [91]:
df_all_num **=** df_all**.** select_dtypes(include **=** ['int64','float64'])

```
skew_features = df_all_num. apply( lambda x: skew(x)). sort_values(ascending =False )
```
```
high_skew = skew_features[skew_features > 0.5]
```
```
skew_index = high_skew. index
```
```
skewness = pd. DataFrame({'Skew' :high_skew})
```
```
skew_features
```
Out[91]:

In [92]:
li_num_feats **=** list(num_feat)

```
nr_rows = 30
```
```
nr_cols = 2
```
```
fig, axs = plt. subplots(nr_rows, nr_cols, figsize = (nr_cols * 7 ,nr_rows * 4 ))
```
```
for r in range( 0 ,nr_rows):
```
```
i = r
```
```
if i < len(li_num_feats):
```
```
sns. distplot(df_all_copy[li_num_feats[i]],ax = axs[r][ 0 ]);
```
```
sns. distplot(df_all[li_num_feats[i]],ax = axs[r][ 1 ]);
```
```
plt. tight_layout()
```
```
plt. show()
```
In [93]:
_# Let's make sure we handled all the skewed values_

```
f, ax = plt. subplots(figsize = ( 8 , 7 ))
```
```
ax. set_xscale("log")
```
```
ax = sns. boxplot(data = df_all[skew_index] , orient = "h", palette = "Set1")
```
```
ax. xaxis. grid( False )
```
```
ax. set(ylabel = "Feature names")
```
```
ax. set(xlabel = "Numeric values")
```
```
ax. set(title = "Numeric Distribution of Features")
```
```
sns. despine(trim =True , left =True )
```
In [169...
df_all_num **=** df_all**.** select_dtypes(include **=** ['float64','int64'])**.** columns _# Numerical columns_

```
df_all_cat = df_all. select_dtypes(exclude = ['float64','int64']) # selecting object and categorical features only
```
```
df_all_dummy = pd. get_dummies(df_all_cat)
```
```
df_all = pd. concat([df_all,df_all_dummy],axis = 1 ) # joining converted dummy feature and original df_all dataset
```
```
df_all = df_all. drop(df_all_cat. columns,axis = 1 ) #removing original categorical columns
```
```
df_all. shape
```
Out[169...

In [171...
df_all**.** head( 3 )

Out[171...

In [172...
x_train1 **=** df_all[:len(df_train)] _#converted into train data_

```
x_test1 = df_all[len(df_train):] #test data
```
In [175...
sc **=** StandardScaler()

```
x_train = sc. fit_transform(x_train1)
```
```
x_test = sc. transform(x_test1)
```
In [223...
lr **=** LinearRegression()**.** fit(x_train, y_train)

In [218...
r_sq **=** lr**.** score(x_train, y_train)

```
print('coefficient of determination - rsquare - on training data :', r_sq)
```
In [219...
maxcoef **=** np**.** argsort( **-** np**.** abs(Rr**.** coef_))

```
coef = lr. coef_[maxcoef]
```
```
for i in range( 0 , 5 ):
```
```
print("{:.<025} {:< 010.4e}". format(df_all. columns[maxcoef[i]], coef[i]))
```
In [220...
**from** sklearn.linear_model **import** LinearRegression, RidgeCV, LassoCV, ElasticNetCV

```
from sklearn.model_selection import cross_val_score
```
In [221...
_# Create linear regression object_

```
Ls = LassoCV()
```
```
# Train the model using the training sets
```
```
Ls. fit(x_train, y_train)
```
Out[221...


```
coefficient of determination - rsquare - on training data : 0.
```
```
OverallQual.............. 9.7745e-
```
```
TotalBsmtSF.............. 9.3288e-
```
```
2ndFlrSF................. 5.7333e-
```
```
Condition2_PosN.......... -4.8166e-
```
```
GarageCars............... 4.2297e-
```
## C. Linear regression, L2 regularisation¶

```
RidgeCV(alphas=array([ 0.1, 1. , 10. ]))
```
```
coefficient of determination - rsquare - on training data : 0.
```
```
TotalBsmtSF.............. 9.5422e-
```
```
2ndFlrSF................. 6.7126e-
```
```
OverallQual.............. 5.9949e-
```
```
Condition2_PosN.......... -5.2500e-
```
```
OverallCond.............. 4.6214e-
```
In [224...
r_sq **=** Ls**.** score(x_train, y_train)

```
print('coefficient of determination - rsquare - on training data :', r_sq)
```
In [225...
maxcoef **=** np**.** argsort( **-** np**.** abs(Ls**.** coef_))

```
coef = Ls. coef_[maxcoef]
```
```
for i in range( 0 , 5 ):
```
```
print("{:.<025} {:< 010.4e}". format(df_all. columns[maxcoef[i]], coef[i]))
```
In [226...
_# Create linear regression object_

```
Rr = RidgeCV()
```
```
# Train the model using the training sets
```
```
Rr. fit(x_train, y_train)
```
Out[226...

In [227...
r_sq **=** Rr**.** score(x_train, y_train)

```
print('coefficient of determination - rsquare - on training data :', r_sq)
```
In [228...
maxcoef **=** np**.** argsort( **-** np**.** abs(Rr**.** coef_))

```
coef = Rr. coef_[maxcoef]
```
```
for i in range( 0 , 5 ):
```
```
print("{:.<025} {:< 010.4e}". format(df_all. columns[maxcoef[i]], coef[i]))
```

