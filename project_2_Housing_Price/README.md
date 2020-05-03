# Project 2 - Ames Housing Data
_____________________________

1. datasets - folder with csv files
2. Ames_Housing_Regression_Kaggel.ipynb - Linear Regression modeling for Kaggle submission (many features (~300))
3. Ames_Housing_Regression_Submission.ipynb - Linear Regression modeling for Kaggle submission (few features (~30))

___________________________

Contents:
 - [Problem Statement](#Problem-Statement)
     - [Aim Of The Project](#Aim-Of-The-Project)
 - [Data Overview](#Data-Overview)
 - [Data Cleaning](#Data-Cleaning)
     - [Encoding Ordinal Columns Into Ints](#Encoding-Ordinal-Columns-Into-Ints)
     - [Missing Data](#Missing-Data)
     - [Data Type](#Data-Type)
     - [Clean Datasets As csv](#Clean-Datasets-As-csv)
     - [Data Dictionary](#Data-Dictionary)
 - [Exploratory Data Analysis](#Exploratory-Data-Analysis)
     - [Summary Statistics](#Summary-Statistics-Of-Train-Dataset)
     - [Outliers And Anomalies](#Outliers-And-Anomalies)
     - [Exploring Columns Relationship](#Exploring-Columns-Relationship)
 - [Feature Creating](#Feature-Creating)
 - [Feature Selection](#Feature-Selection)
     - [Backward Elimination](#Backward-Elimination)
     - [Recursive Feature Elimination](#Recursive-Feature-Elimination)
 - [Preprocessing Data](#Preprocessing-Data)
 - [Modeling And Evaluation](#Modeling-And-Evaluation)
     - [Lasso](#Lasso)
     - [Linear Regression](#Linear-Regression)
     - [Ridge](#Ridge)
 - [Pridictions](#Pridictions)
 - [Inference](#Inference)
 - [Conclusion](#Conclusion)
 - [Recommendations](#Recommendations)
 - [Further research suggestions](#Further-research-suggestions)
 
 ___________________________________
 
 ## Problem Statement
 
 A real estate market Dataset from Kaggle was used to identify and study the features which can contribute the most into the price (in dollars) prediction of property in Ames, Iowa, USA. The Dataset comprises sales from 2006 to 2010.

The Regression models (Linear Regression, Lasso Regression and Ridge Regression) were used for price prediction based on features from provided Dataset (CSV files). The performance of the model was gauged with R2 value.

The model is essential for all market stakeholders: house owners, landlords, real estate agents, their clients etc. It gives them the possibility of short-term and long-term financial planning as well as realistic property price.

### Aim Of The Project

1. Predict price based on feature provided (in dollars).
2. Select features which influence the price of the property.
3. Provide recommendations for stakeholders.

#### Answer the following questions:

1. With an increase of Overall Quality of property does price increase?
2. Does the price vary with different House Style?
3. Does older property cost less than newer ones?


## Data Sets (CSV files):
 - [train](https://raw.githubusercontent.com/April-DS/General_Assembly_Projects/master/project_2_Housing_Price/datasets/train.csv)
 - [test](https://raw.githubusercontent.com/April-DS/General_Assembly_Projects/master/project_2_Housing_Price/datasets/test.csv)
 - [sample_submission](https://raw.githubusercontent.com/April-DS/General_Assembly_Projects/master/project_2_Housing_Price/datasets/sample_sub_reg.csv)
 
## Data Dictionary 

|    Features     |                       Categories (str)                       |                  Categories representation                   | Type  |                         Description                          |
| :-------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :---: | :----------------------------------------------------------: |
|       pid       |                              -                               |                              -                               |  int  |            Property identification number (USA).             |
|   ms_subclass   | 1-STORY 1946 & NEWER ALL STYLES <br/>1-STORY 1945 & OLDER <br/>1-STORY W/FINISHED ATTIC ALL AGES <br/>1-1/2 STORY - UNFINISHED ALL AGES <br/>1-1/2 STORY FINISHED ALL AGES <br/>2-STORY 1946 & NEWER <br/>2-STORY 1945 & OLDER <br/>2-1/2 STORY ALL AGES <br/>SPLIT OR MULTI-LEVEL <br/>SPLIT FOYER <br/>DUPLEX - ALL STYLES AND AGES <br/>1-STORY PUD (Planned Unit Development) - 1946 & NEWER <br/>1-1/2 STORY PUD - ALL AGES <br/>2-STORY PUD - 1946 & NEWER <br/>PUD - MULTILEVEL - INCL SPLIT LEV/FOYER 190 2 FAMILY CONVERSION - ALL STYLES AND AGES | 20<br/>30<br/>40<br/>45<br/>50<br/>60<br/>70<br/>75<br/>80<br/>85<br/>90<br/>120<br/>150<br/>160<br/>180<br/>190 |  int  |                     The building class.                      |
|    ms_zoning    | Agriculture<br/>Commercial<br/>Floating Village Residential<br/>Industrial<br/>Residential High Density<br/>Residential Low Density<br/>Residential Low Density Park<br/>Residential Medium Density | RL<br/>RM<br/>FV<br/>C (all)<br/>A (agr)<br/>RH<br/>I (all)  |  str  |  Identifies the general zoning classification of the sale.   |
|    lot_area     |                              -                               |                              -                               |  int  |                   Lot size in square feet.                   |
|     street      |                       Gravel<br/>Paved                       |                        Grvl<br/>Pave                         |  str  |               Type of road access to property.               |
|      alley      |             Gravel<br/>Paved<br/>No alley access             |                    Grvl<br/>Pave<br/>None                    |  str  |              Type of alley access to property.               |
|    lot_shape    | Regular<br/>Slightly irregular<br/>Moderately Irregular<br/>Irregular |                 IR1<br/>Reg<br/>IR2<br/>IR3                  |  str  |                  General shape of property.                  |
|  land_contour   | Near Flat/Level<br/>Banked - Quick and significant rise from street grade to building<br/>Hillside - Significant slope from side to side<br/>Depression |                 Lvl<br/>HLS<br/>Bnk<br/>Low                  |  str  |                  Flatness of the property.                   |
|    utilities    | All public Utilities (E,G,W,& S)<br/>Electricity, Gas, and Water (Septic Tank)<br/>Electricity and Gas Only<br/>Electricity only |                        1<br/>2<br/>3                         |  int  |                 Type of utilities available.                 |
|   lot_config    | Inside lot<br/>Corner lot<br/>Cul-de-sac<br/>Frontage on 2 sides of property<br/>Frontage on 3 sides of property |        CulDSac<br/>Inside<br/>Corner<br/>FR2<br/>FR3         |  str  |                      Lot configuration.                      |
|   land_slope    |       Gentle slope<br/>Moderate Slope<br/>Severe Slope       |                     Gtl<br/>Sev<br/>Mod                      |  str  |                      Slope of property.                      |
|  neighborhood   | Bloomington Heights<br/>Bluestem<br/>Briardale<br/>Brookside<br/>Clear Creek<br/>College Creek<br/>Crawford<br/>Edwards<br/>Gilbert<br/>Iowa DOT and Rail Road<br/>Meadow Village<br/>Mitchell<br/>Names North Ames<br/>Northridge<br/>Northpark Villa<br/>Northridge Heights<br/>Northwest Ames<br/>Old Town<br/>South & West of Iowa State University<br/>Sawyer<br/>Sawyer West<br/>Somerset<br/>Stone Brook<br/>Timberland<br/>Veenker | 'Sawyer', 'SawyerW', 'NAmes', 'Timber', 'Edwards', 'OldTown',        'BrDale', 'CollgCr', 'Somerst', 'Mitchel', 'StoneBr', 'NridgHt',        'Gilbert', 'Crawfor', 'IDOTRR', 'NWAmes', 'Veenker', 'MeadowV',        'SWISU', 'NoRidge', 'ClearCr', 'Blmngtn', 'BrkSide', 'NPkVill',        'Blueste', 'GrnHill', 'Greens', 'Landmrk' |  str  |         Physical locations within Ames city limits.          |
|   condition_1   | Artery Adjacent to arterial street Feedr Adjacent to feeder street Norm Normal RRNn Within 200' of North-South Railroad RRAn Adjacent to North-South Railroad PosN Near positive off-site feature--park, greenbelt, etc. PosA Adjacent to postive off-site feature RRNe Within 200' of East-West Railroad RRAe Adjacent to East-West Railroad | 'RRAe', 'Norm', 'PosA', 'Artery', 'Feedr', 'PosN', 'RRAn', 'RRNe',        'RRNn' |  str  |             Proximity to main road or railroad.              |
|   condition_2   | Artery Adjacent to arterial street Feedr Adjacent to feeder street Norm Normal RRNn Within 200' of North-South Railroad RRAn Adjacent to North-South Railroad PosN Near positive off-site feature--park, greenbelt, etc. PosA Adjacent to postive off-site feature RRNe Within 200' of East-West Railroad RRAe Adjacent to East-West Railroad | 'Norm', 'RRNn', 'Feedr', 'Artery', 'PosA', 'PosN', 'RRAe', 'RRAn' |  str  | Proximity to main road or railroad (if a second is present)  |
|    bldg_type    | 1Fam Single-family Detached 2FmCon Two-family Conversion; originally built as one-family dwelling Duplx Duplex TwnhsE Townhouse End Unit TwnhsI Townhouse Inside Unit |        '1Fam', 'TwnhsE', 'Twnhs', '2fmCon', 'Duplex'         |  str  |                      Type of dwelling.                       |
|   house_style   | 1Story One story 1.5Fin One and one-half story: 2nd level finished 1.5Unf One and one-half story: 2nd level unfinished 2Story Two story 2.5Fin Two and one-half story: 2nd level finished 2.5Unf Two and one-half story: 2nd level unfinished SFoyer Split Foyer SLvl Split Level | '2Story', '1Story', '1.5Fin', 'SFoyer', 'SLvl', '2.5Unf', '2.5Fin',        '1.5Unf' |  str  |                      Style of dwelling.                      |
|  overall_qual   | 10 Very Excellent 9 Excellent 8 Very Good 7 Good 6 Above Average 5 Average 4 Below Average 3 Fair 2 Poor 1 Very Poor |   10<br/>9<br/>8<br/>7<br/>6<br/>5<br/>4<br/>3<br/>2<br/>1   |  int  |             Overall material and finish quality.             |
|  overall_cond   | 10 Very Excellent 9 Excellent 8 Very Good 7 Good 6 Above Average 5 Average 4 Below Average 3 Fair 2 Poor 1 Very Poor |   10<br/>9<br/>8<br/>7<br/>6<br/>5<br/>4<br/>3<br/>2<br/>1   |  int  |                   Overall condition rating                   |
|   year_built    |                              -                               |                              -                               |  int  |          Original construction date (1872 - 2010).           |
| year_remod/add  |                              -                               |                              -                               |  int  | Remodel date (same as construction date if no remodeling or additions)(1950-2010). |
|   roof_style    | Flat Flat Gable Gable Gambrel Gabrel (Barn) Hip Hip Mansard Mansard Shed Shed |     'Gable', 'Hip', 'Flat', 'Mansard', 'Shed', 'Gambrel'     |  str  |                        Type of roof.                         |
|    roof_matl    |                                                              | 'CompShg', 'WdShngl', 'Tar&Grv', 'WdShake', 'Membran', 'ClyTile' |  str  |                        Roof material.                        |
|  exterior_1st   | AsbShng Asbestos Shingles AsphShn Asphalt Shingles BrkComm Brick Common BrkFace Brick Face CBlock Cinder Block CemntBd Cement Board HdBoard Hard Board ImStucc Imitation Stucco MetalSd Metal Siding Other Other Plywood Plywood PreCast PreCast Stone Stone Stucco Stucco VinylSd Vinyl Siding Wd Sdng Wood Siding WdShing Wood Shingles | 'HdBoard', 'VinylSd', 'Wd Sdng', 'BrkFace', 'Plywood', 'MetalSd',        'AsbShng', 'CemntBd', 'WdShing', 'Stucco', 'BrkComm', 'Stone',        'CBlock', 'ImStucc', 'AsphShn' |  str  |                 Exterior covering on house.                  |
|  exterior_2nd   | AsbShng Asbestos Shingles AsphShn Asphalt Shingles BrkComm Brick Common BrkFace Brick Face CBlock Cinder Block CemntBd Cement Board HdBoard Hard Board ImStucc Imitation Stucco MetalSd Metal Siding Other Other Plywood Plywood PreCast PreCast Stone Stone Stucco Stucco VinylSd Vinyl Siding Wd Sdng Wood Siding WdShing Wood Shingles | 'Plywood', 'VinylSd', 'Wd Sdng', 'HdBoard', 'MetalSd', 'AsbShng',        'CmentBd', 'Wd Shng', 'BrkFace', 'Stucco', 'Brk Cmn', 'ImStucc',        'Stone', 'CBlock', 'AsphShn' |  str  |   Exterior covering on house (if more than one material).    |
|  mas_vnr_type   | BrkCmn Brick Common BrkFace Brick Face CBlock Cinder Block None None Stone Stone |       'BrkFace', 'None', 'Missing', 'Stone', 'BrkCmn'        |  str  |                     Masonry veneer type                      |
|  mas_vnr_area   |                              -                               |                              -                               | float |             Masonry veneer area in square feet.              |
|   exter_qual    |   Ex Excellent Gd Good TA Average/Typical Fa Fair Po Poor    |                  4<br/>3<br/>2<br/>1<br/>0                   |  int  |                  Exterior material quality.                  |
|   exter_cond    |   Ex Excellent Gd Good TA Average/Typical Fa Fair Po Poor    |               5<br/>4<br/>3<br/>2<br/>1<br/>0                |  int  |      Present condition of the material on the exterior.      |
|   foundation    | BrkTil Brick & Tile CBlock Cinder Block PConc Poured Contrete Slab Slab Stone Stone Wood Wood |     'CBlock', 'PConc', 'BrkTil', 'Slab', 'Stone', 'Wood'     |  str  |                     Type of foundation.                      |
|    bsmt_qual    | Ex Excellent (100+ inches) Gd Good (90-99 inches) TA Typical (80-89 inches) Fa Fair (70-79 inches) Po Poor (<70 inches) NA No Basement |               5<br/>4<br/>3<br/>2<br/>1<br/>0                |  int  |                   Height of the basement.                    |
|    bsmt_cond    | Ex Excellent Gd Good TA Typical - slight dampness allowed Fa Fair - dampness or some cracking or settling Po Poor - Severe cracking, settling, or wetness NA No Basement |               5<br/>4<br/>3<br/>2<br/>1<br/>0                |  int  |              General condition of the basement.              |
|  bsmt_exposure  | Gd Good Exposure Av Average Exposure (split levels or foyers typically score average or above) Mn Mimimum Exposure No No Exposure NA No Basement |                  4<br/>3<br/>2<br/>1<br/>0                   |  int  |           Walkout or garden level basement walls.            |
| bsmtfin_type_1  | GLQ Good Living Quarters ALQ Average Living Quarters BLQ Below Average Living Quarters Rec Average Rec Room LwQ Low Quality Unf Unfinshed NA No Basement |            6<br/>5<br/>4<br/>3<br/>2<br/>1<br/>0             |  int  |              Quality of basement finished area.              |
|  bsmtfin_sf_1   |                              -                               |                              -                               | float |                 Type 1 finished square feet.                 |
| bsmtfin_type_2  | GLQ Good Living Quarters ALQ Average Living Quarters BLQ Below Average Living Quarters Rec Average Rec Room LwQ Low Quality Unf Unfinshed NA No Basement |       'Unf', 'Rec', 'None', 'BLQ', 'GLQ', 'LwQ', 'ALQ'       |  str  |         Quality of second finished area (if present)         |
|  bsmtfin_sf_2   |                              -                               |                              -                               | float |                 Type 2 finished square feet.                 |
|   bsmt_unf_sf   |                              -                               |                              -                               | float |           Unfinished square feet of basement area.           |
|  total_bsmt_sf  |                              -                               |                              -                               | float |             Total square feet of basement area.              |
|     heating     | Floor Floor Furnace GasA Gas forced warm air furnace GasW Gas hot water or steam heat Grav Gravity furnace OthW Hot water or steam heat other than gas Wall Wall furnace |            'GasA', 'GasW', 'Grav', 'Wall', 'OthW'            |  str  |                       Type of heating.                       |
|   heating_qc    |   Ex Excellent Gd Good TA Average/Typical Fa Fair Po Poor    |                  4<br/>3<br/>2<br/>1<br/>0                   |  int  |                Heating quality and condition.                |
|   central_air   |                          N No Y Yes                          |                           0<br/>1                            |       |                  Central air conditioning.                   |
|   electrical    | SBrkr Standard Circuit Breakers & Romex FuseA Fuse Box over 60 AMP and all Romex wiring (Average) FuseF 60 AMP Fuse Box and mostly Romex wiring (Fair) FuseP 60 AMP Fuse Box and mostly knob & tube wiring (poor) Mix Mixed |          'SBrkr', 'FuseF', 'FuseA', 'FuseP', 'Mix'           |  str  |                      Electrical system.                      |
|   1st_flr_sf    |                              -                               |                              -                               |  int  |                   First Floor square feet.                   |
|   2nd_flr_sf    |                              -                               |                              -                               |  int  |                  Second floor square feet.                   |
| low_qual_fin_sf |                              -                               |                              -                               |  int  |        Low quality finished square feet (all floors).        |
|   gr_liv_area   |                              -                               |                              -                               |  int  |        Above grade (ground) living area square feet.         |
| bsmt_full_bath  |                              -                               |                              -                               | float |                   Basement full bathrooms.                   |
| bsmt_half_bath  |                              -                               |                              -                               | float |                   Basement half bathrooms.                   |
|    full_bath    |                              -                               |                              -                               |  int  |                 Full bathrooms above grade.                  |
|    half_bath    |                              -                               |                              -                               |  int  |                   Half baths above grade.                    |
|  bedroom_abvgr  |                              -                               |                              -                               |  int  |           Number of bedrooms above basement level.           |
|  kitchen_abvgr  |                              -                               |                              -                               |  int  |                     Number of kitchens.                      |
|  kitchen_qual   |   Ex Excellent Gd Good TA Typical/Average Fa Fair Po Poor    |               5<br/>4<br/>3<br/>2<br/>1<br/>0                |  int  |                       Kitchen quality.                       |
|  totrms_abvgrd  |                              -                               |                              -                               |  int  |     Total rooms above grade (does not include bathrooms)     |
|   functional    | Typ Typical Functionality Min1 Minor Deductions 1 Min2 Minor Deductions 2 Mod Moderate Deductions Maj1 Major Deductions 1 Maj2 Major Deductions 2 Sev Severely Damaged Sal Salvage only |  'Typ', 'Mod', 'Min2', 'Maj1', 'Min1', 'Sev', 'Sal', 'Maj2'  |  str  |                  Home functionality rating                   |
|   fireplaces    |                              -                               |                              -                               |  int  |                    Number of fireplaces.                     |
|  fireplace_qu   | Ex Excellent - Exceptional Masonry Fireplace Gd Good - Masonry Fireplace in main level TA Average - Prefabricated Fireplace in main living area or Masonry Fireplace in basement Fa Fair - Prefabricated Fireplace in basement Po Poor - Ben Franklin Stove NA No Fireplace |               5<br/>4<br/>3<br/>2<br/>1<br/>0                |  int  |                      Fireplace quality.                      |
|   garage_type   | 2Types More than one type of garage Attchd Attached to home Basment Basement Garage BuiltIn Built-In (Garage part of house - typically has room above garage) CarPort Car Port Detchd Detached from home NA No Garage | 'Attchd', 'Detchd', 'BuiltIn', 'Basment', 'None', '2Types',        'CarPort' |  str  |                       Garage location.                       |
|  garage_yr_blt  |                              -                               |                              -                               |  int  |                    Year garage was built.                    |
|  garage_finish  | Fin Finished RFn Rough Finished Unf Unfinished NA No Garage  |                 'RFn', 'Unf', 'Fin', 'None'                  |  str  |                Interior finish of the garage.                |
|   garage_cars   |                              -                               |                              -                               | float |               Size of garage in car capacity.                |
|   garage_area   |                              -                               |                              -                               | float |                Size of garage in square feet.                |
|   garage_qual   | Ex Excellent Gd Good TA Typical/Average Fa Fair Po Poor NA No Garage |               5<br/>4<br/>3<br/>2<br/>1<br/>0                |  int  |                       Garage quality.                        |
|   garage_cond   | Ex Excellent Gd Good TA Typical/Average Fa Fair Po Poor NA No Garage |               5<br/>4<br/>3<br/>2<br/>1<br/>0                |  int  |                      Garage condition.                       |
|   paved_drive   |           Y Paved P Partial Pavement N Dirt/Gravel           |                        'Y', 'N', 'P'                         |  str  |                       Paved driveway.                        |
|  wood_deck_sf   |                              -                               |                              -                               |  int  |                Wood deck area in square feet.                |
|  open_porch_sf  |                              -                               |                              -                               |  int  |               Open porch area in square feet.                |
| enclosed_porch  |                              -                               |                              -                               |  int  |             Enclosed porch area in square feet.              |
|   3ssn_porch    |                              -                               |                              -                               |  int  |           Three season porch area in square feet.            |
|  screen_porch   |                              -                               |                              -                               |  int  |              Screen porch area in square feet.               |
|    pool_area    |                              -                               |                              -                               |  int  |                  Pool area in square feet.                   |
|     pool_qc     |  Ex Excellent Gd Good TA Average/Typical Fa Fair NA No Pool  |               5<br/>4<br/>3<br/>2<br/>1<br/>0                |  int  |                        Pool quality.                         |
|      fence      | GdPrv Good Privacy MnPrv Minimum Privacy GdWo Good Wood MnWw Minimum Wood/Wire NA No Fence |                  4<br/>3<br/>2<br/>1<br/>0                   |  int  |                        Fence quality.                        |
|  misc_feature   | Elev Elevator Gar2 2nd Garage (if not described in garage section) Othr Other Shed Shed (over 100 SF) TenC Tennis Court NA None |        'None', 'Shed', 'TenC', 'Gar2', 'Othr', 'Elev'        |  str  |    Miscellaneous feature not covered in other categories.    |
|    misc_val     |                              -                               |                              -                               |  int  |               $ Value of miscellaneous feature               |
|     mo_sold     |            1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12             |                                                              |  int  |                          Month Sold                          |
|     yr_sold     |                              -                               |                              -                               |  int  |                          Year Sold                           |
|    sale_type    | WD Warranty Deed - Conventional CWD Warranty Deed - Cash VWD Warranty Deed - VA Loan New Home just constructed and sold COD Court Officer Deed/Estate Con Contract 15 prcnt Down payment regular terms ConLw Contract Low Down payment and low interest ConLI Contract Low Interest ConLD Contract Low Down Oth Other | 'WD ', 'New', 'COD', 'ConLD', 'Con', 'CWD', 'Oth', 'ConLI',        'ConLw' |  str  |                         Type of sale                         |

|    saleprice    |                              -                               |                              -                               |  int  |                         Sale Price $                         |


______________________________________________

## Three type of modeling will be deploied: Lasso Linear Regression, Multilinear regression and Ridge Linear Regression.


Linear Regression evaluation.

The R2 score is a bit higher (0.8965824658431704) than Lasso (0.8961671756077313).

        --- Baseline model scores ---
        Root mean squared error RMSE: 79309.30582989656
        R2: 0.0
        
        --- Lasso model scores ---
        Root mean squared error RMSE: 25555.91779216108
        R2: 0.8961671756077313
        
        --- LR model scores ---
        Root mean squared error RMSE: 25504.75980561859
        R2: 0.8965824658431704
        
        --- Ridge model scores ---
        Root mean squared error RMSE: 25596.84391872191
        R2: 0.8958343463996501


R2 scores are consistent what can be interpreted that the model is not overfitting.

The scores are high enough to say that the model is not underfitting.

The RMSE is a bit smaller than Lasso, that means that LR model fits the data better.

It can be seen that residuals distributed homoscedastic, but not really random due to outliers.

#### All models gave very similar results, but the LR model perform slightly better. The decision is to keep the first model of Linear Regression due to best R2 and RMSE score.¶

__________________________________________

## Conclusion

Answering question of our project:
    
 1. With an increase of Overall Quality of property does price increase?
**Yes, the price of the property increase**
 - The overall quality of property highly correlated with a sale price (0.804683). The coefficient is positive what means that with an increase in overall quality the sale price also increases.
 - overall quality one of the most influencing features. With an increase in 1 grade of quality the price increase on $ 13986.

 2. Does the price vary with different House Style?
 **Yes, price differ**
 - From the scatterplot above we could see that the median and distribution of sale price vary regarding different house style.
 - 'One story' House style is cost more than other styles.

 3. Does older property cost less than newer ones?
**Yes, the older property cost less**
 - The positive correlation coefficient for year_built (0.573751) demonstrates that newer properties cost higher than older ones.
 - With an increase in one year the property rise in price in $ 5069.
 
 ## Recommendations
 
 **To House Owners, Landlords, Real Estate Agents:**

Features which increase the price of your property:
1. Basement and the overall area of the property.
2. Overall material and finish quality.
3. A number of fireplaces.
4. 'One story' house style.


**To House Buyers:**
1. Houses which were built earlier cost less.
2. Kitchen quality influence on sale price. The cost of renovation of the kitchen should be considered. With an increase in kitchen quality on 1 point, the price rise in $ 6183.

3. Exterior material quality increase price not so drastically, on $ 3879 with better quality. It means that the exterior can be misleading.

## Further research suggestions

The built model of the prediction sale price of property of Ames should be explored on other datasets. It is possible that the model will show worse prediction in other locations.

Further research should consider:
- To evaluate the generalizability of the model more data required.
- Prices higher than $ 500,000 should be explored separately. The model shows worse predictions for such a high price. More data should be collected for high price property separately.
- Features with a negative slope. Additional models should be built to evaluate the influence of the features on price.
- Use more complicated models for prediction.
____________________________________

### Late submission scores:
Public Score now: 28980.29521
    
Public Score for Kaggle: 25888.84521
    
Private Score now: 33462.61116

Private Score for Kaggle: 34211.28292 
