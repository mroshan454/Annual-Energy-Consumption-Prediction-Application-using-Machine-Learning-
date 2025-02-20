# Annual-Energy-Consumption-Prediction-Application-using-Machine-Learning-
This project is an energy prediction application which predicts annual energy consumption in KW/H after getting the user inputs from Homeowners/Renters. The model was trained on using EPC(Energy Performance Certificates) of Domestic Buildings Dataset of England and Wales. 

## 1. Problem Statement:
CO2 Emission and Energy Consumption are one of the major factors affecting the environment. As a homeowner or a renter it is really hard to get an estimate of what an annual energy consumption of their home will be like. Also apart from that it would be good if the user will get any suggestions to reduce their annual energy consumption which will help to reduce the amount of bills they are paying. Also , in this time of climate change it is essential to know the CO2 Emission from your home/building which is a major contributing factor of the environemental issues.

This project will be the attempt to predict/estimate the annual energy(KW/H) and CO2 emission of a residential building using the models trained on real world dataset, which I hope will help the end users find it useful to get valuable insights of their own homes and how to improve their energy consumption

## 2. Dataset :
The dataset we are using for this project is called `Energy Performance Certificate(EPC)` dataset from the website of the UK's official Department for Levelling Up, Housing & Communities. This is an open data published by the UK Government and had published the data from 2008 Oct 1, and are updated monthly. The data can be downloaded from here: https://epc.opendatacommunities.org

### 2.1 Dataset Description
This is a very big dataset which contains the Energy Performance data of each residential buildings in the England and Wales, and we have the option to download the data of each towns from the England and Wales.
The data are of two types :
* Domestic EPC (Residential Buildings and Houses)
* Non-Domestic EPC (Non-Residential Buildings, Offices, Businesses etc.)

Since we are focusing on Residential Buildings we are using the Domestic EPCs .

### 2.2 What is inside the Dataset?

The EPC dataset is a very big and comprehensive dataset which contains top to bottom details of a building , the dataset comes with a glossary of what's inside the data , which is a long list of details I will put here:


#### Glossary: Domestic EPCs
The glossary contains the what each column is and their respective column names and data types

The Following the is formatted like this :

- **NAME** - `COLUMN_NAME (DATA TYPE)` Description

Below is the glossary of what is inside this dataset.

- **LMK KEY** - `LMK_KEY (VARCHAR 64)`
Individual lodgement identifier. Guaranteed to be unique and
can be used to identify a certificate in the downloads and
the API.
- **ADDRESS 1** - `ADDRESS1 (VARCHAR 84)`
First line of the address
- **ADDRESS 2** - `ADDRESS2 (VARCHAR 100)`
Second line of the address
- **ADDRESS 3** - `ADDRESS3 (VARCHAR 100)`
Third line of the address
- **POSTCODE** - `POSTCODE (VARCHAR 8)`
The postcode of the property
- **BUILDING REFERENCE NUMBER** - `BUILDING_REFERENCE_NUMBER`
VARCHAR 12
Unique identifier for the property.
- **CURRENT ENERGY RATING** - `CURRENT_ENERGY_RATING (VARCHAR 8)`
Current energy rating converted into a linear 'A to G' rating
(where A is the most energy efficient and G is the least
energy efficient)
- **POTENTIAL ENERGY RATING** - `POTENTIAL_ENERGY_RATING (VARCHAR
8)`
Estimated potential energy rating converted into a linear 'A
to G' rating (where A is the most energy efficient and G is
the least energy efficient)
- **CURRENT ENERGY EFFICIENCY** -  `CURRENT_ENERGY_EFFICIENCY(INT)`
Based on cost of energy, i.e. energy required for space
heating, water heating and lighting [in kWh/year] multiplied
by fuel costs. (£/m²/year where cost is derived from kWh).
- **POTENTIAL ENERGY EFFICIENCY** - `POTENTIAL_ENERGY_EFFICIENCY
(INT)`
The potential energy efficiency rating of the property.
- **PROPERTY TYPE** - `PROPERTY_TYPE (VARCHAR 10)`
Describes the type of property such as House, Flat,
Maisonette etc. This is the type differentiator for dwellings.
- **BUILT FORM** -` BUILT_FORM (VARCHAR 20)`
The building type of the Property e.g. Detached, Semi-
Detached, Terrace etc. Together with the Property Type, the
Build Form produces a structured description of the property
- **INSPECTION DATE** - `INSPECTION_DATE (DATE)`
The date that the inspection was actually carried out by the
energy assessor
- **LOCAL AUTHORITY** - `LOCAL_AUTHORITY (VARCHAR 9)`
Office for National Statistics (ONS) code. Local authority
area in which the building is located.
- **CONSTITUENCY**- `CONSTITUENCY (VARCHAR 9)`
Office for National Statistics (ONS) code. Parliamentary
constituency in which the building is located.
- **COUNTY** -`COUNTY (VARCHAR 24)`
County in which the building is located (where applicable)
- **LODGEMENT DATE** -`LODGEMENT_DATE (DATE)`
Date lodged on the Energy Performance of Buildings
Register
- **TRANSACTION TYPE** -`TRANSACTION_TYPE (VARCHAR 82)`
Type of transaction that triggered EPC. For example, one of:
marketed sale; non-marketed sale; new-dwelling; rental; not
sale or rental; assessment for Green Deal; following Green
Deal; FIT application; none of the above; RHI application;
ECO assessment. Where the reason for the assessment is
unknown by the energy assessor the transaction type will be
recorded as 'none of the above'. Transaction types may be
changed over time.
- **ENVIRONMENT IMPACT CURRENT** - `ENVIRONMENT_IMPACT_CURRENT
(INT)`
The Environmental Impact Rating. A measure of the
property's current impact on the environment in terms of
carbon dioxide (CO₂) emissions. The higher the rating the
lower the CO₂ emissions. (CO₂ emissions in tonnes / year)
- **ENVIRONMENT IMPACT POTENTIAL** - `ENVIRONMENT_IMPACT_POTENTIAL (INT)`
The potential Environmental Impact Rating. A measure of
the property's potential impact on the environment in terms
of carbon dioxide (CO₂) emissions after improvements have
been carried out. The higher the rating the lower the CO₂
emissions. (CO₂ emissions in tonnes / year)
- **ENERGY CONSUMPTION CURRENT** - `ENERGY_CONSUMPTION_CURRENT (FLOAT)`
Current estimated total energy consumption for the property
in a 12 month period (kWh/m2). Displayed on EPC as the
current primary energy use per square metre of floor area.
- **ENERGY CONSUMPTION POTENTIAL** - `ENERGY_CONSUMPTION_POTENTIAL (FLOAT)`
Estimated potential total energy consumption for the
Property in a 12 month period. Value is Kilowatt Hours per
Square Metre (kWh/m²)
- **CO₂ EMISSIONS CURRENT** - `CO2_EMISSIONS_CURRENT (DECIMAL)`
CO₂ emissions per year in tonnes/year.
- **CO₂ EMISS CURR PER FLOOR AREA** - `CO2_EMISS_CURR_PER_FLOOR_AREA (DECIMAL)`
CO₂ emissions per square metre floor area per year in kg/m²
- **CO₂ EMISSIONS POTENTIAL** - `CO2_EMISSIONS_POTENTIAL (DECIMAL)`
Estimated value in Tonnes per Year of the total CO₂
emissions produced by the Property in 12 month period.
- **LIGHTING COST CURRENT** - `LIGHTING_COST_CURRENT (FLOAT)`
GBP. Current estimated annual energy costs for lighting the
property.
- **LIGHTING COST POTENTIAL** - `LIGHTING_COST_POTENTIAL (FLOAT)`
GBP. Potential estimated annual energy costs for lighting
the property after improvements have been made.
- **HEATING COST CURRENT** -  `HEATING_COST_CURRENT (FLOAT)`
GBP. Current estimated annual energy costs for heating the
property.
- **HEATING COST POTENTIAL** - `HEATING_COST_POTENTIAL (FLOAT)`
GBP. Potential annual energy costs for lighting the property
after improvements have been made.
- **HOT WATER COST CURRENT** - `HOT_WATER_COST_CURRENT (FLOAT)`
GBP. Current estimated annual energy costs for hot water
- **HOT WATER COST POTENTIAL** - `HOT_WATER_COST_POTENTIAL (FLOAT)`
`GBP`. Potential estimated annual energy costs for hot water
after improvements have been made.
- **TOTAL FLOOR AREA** - `TOTAL_FLOOR_AREA (DECIMAL)`
The total useful floor area is the total of all enclosed spaces
measured to the internal face of the external walls, i.e. the
gross floor area as measured in accordance with the
guidance issued from time to time by the Royal Institute of
Chartered Surveyors or by a body replacing that institution.
`(m²)`
- **ENERGY TARIFF** -`ENERGY_TARIFF (VARCHAR 16)`
Type of electricity tariff for the property, e.g. single.
- **MAINS GAS FLAG** - `MAINS_GAS_FLAG (VARCHAR 1)`
Whether mains gas is available. Yes means that there is a
gas meter or a gas-burning appliance in the dwelling. A
closed-off gas pipe does not count.
- **FLOOR LEVEL** -`FLOOR_LEVEL (VARCHAR 13)`
Flats and maisonettes only. Floor level relative to the lowest
level of the property (0 for ground floor). If there is a
basement, the basement is level 0 and the other floors are
from 1 upwards
- **FLAT TOP STOREY** - `FLAT_TOP_STOREY (VARCHAR 1)`
Whether the flat is on the top storey
- **FLAT STOREY COUNT** - `FLAT_STOREY_COUNT (INT)`
The number of storeys in the apartment block.
- **MAIN HEATING CONTROLS** -`MAIN_HEATING_CONTROLS (VARCHAR 19)`
Type of main heating controls. Includes both main heating
systems if there are two.
- **MULTI GLAZE PROPORTION** -`MULTI_GLAZE_PROPORTION (FLOAT)`
The estimated banded range (e.g. 0% - 10%) of the total
glazed area of the Property that is multiple glazed.
- **GLAZED TYPE** - `GLAZED_TYPE (VARCHAR 45)`
The type of glazing. From British Fenestration Rating
Council or manufacturer declaration, one of; single; double;
triple.
- **GLAZED AREA** - `GLAZED_AREA (VARCHAR 22)`
Ranged estimate of the total glazed area of the Habitable
Area.
- **EXTENSION COUNT** - `EXTENSION_COUNT (FLOAT)`
The number of extensions added to the property. Between 0
and 4.
- **NUMBER HABITABLE ROOMS** -`NUMBER_HABITABLE_ROOMS (FLOAT)`
Habitable rooms include any living room, sitting room, dining
room, bedroom, study and similar; and also a non-separated
conservatory. A kitchen/diner having a discrete seating area
(with space for a table and four chairs) also counts as a
habitable room. A non-separated conservatory adds to the
habitable room count if it has an internal quality door
between it and the dwelling. Excluded from the room count
are any room used solely as a kitchen, utility room,
bathroom, cloakroom, en-suite accommodation and similar
and any hallway, stairs or landing; and also any room not
having a window.
- **NUMBER HEATED** - `ROOMS NUMBER_HEATED_ROOMS (FLOAT)`
The number of heated rooms in the property if more than
half of the habitable rooms are not heated.
- **LOW ENERGY LIGHTING** - `LOW_ENERGY_LIGHTING (INT)`
The percentage of low energy lighting present in the
property as a percentage of the total fixed lights in the
property. 0% indicates that no low-energy lighting is present.
- **NUMBER OPEN FIREPLACES** - `NUMBER_OPEN_FIREPLACES (INT)`
The number of Open Fireplaces in the Property. An Open
Fireplace is a fireplace that still allows air to pass between
the inside of the Property and the outside.
- **HOTWATER DESCRIPTION** - `HOTWATER_DESCRIPTION (VARCHAR 95)`
Overall description of the property feature
- **HOT WATER ENERGY EFF** - `HOT_WATER_ENERGY_EFF (VARCHAR 9)`
Energy efficiency rating. One of: very good; good; average;
poor; very poor. On actual energy certificate shown as one
to five star rating.
- **HOT WATER ENV EFF** - ` HOT_WATER_ENV_EFF (VARCHAR 9)`
Environmental efficiency rating. One of: very good; good;
average; poor; very poor. On actual energy certificate shown
as one to five star rating.
- **FLOOR DESCRIPTION** - `FLOOR_DESCRIPTION (VARCHAR 91)`
Overall description of the property feature
- **FLOOR ENERGY EFF** - `FLOOR_ENERGY_EFF (VARCHAR 9)`
Energy efficiency rating. One of: very good; good; average;
poor; very poor. On actual energy certificate shown as one
to five star rating.
- **FLOOR ENV EFF**-  `FLOOR_ENV_EFF (VARCHAR 9)`
Environmental efficiency rating. One of: very good; good;
average; poor; very poor. On actual energy certificate shown
as one to five star rating.
- **WINDOWS DESCRIPTION** - `WINDOWS_DESCRIPTION (VARCHAR 54)`
Overall description of the property feature
- **WINDOWS ENERGY EFF** -` WINDOWS_ENERGY_EFF (VARCHAR 9)`
Energy efficiency rating. One of: very good; good; average;
poor; very poor. On actual energy certificate shown as one
to five star rating.
- **WINDOWS ENV EFF** -` WINDOWS_ENV_EFF (VARCHAR 9)`
WINDOWS. Environmental efficiency rating. One of: very
good; good; average; poor; very poor. On actual energy
certificate shown as one to five star rating.
- **WALLS DESCRIPTION** - ` WALLS_DESCRIPTION (VARCHAR 121)`
Overall description of the property feature
- **WALLS ENERGY EFF** - `WALLS_ENERGY_EFF (VARCHAR 9)`
Energy efficiency rating. One of: very good; good; average;
poor; very poor. On actual energy certificate shown as one
to five star rating.
- **WALLS ENV EFF** -`WALLS_ENV_EFF (VARCHAR 9)`
Environmental efficiency rating. One of: very good; good;
average; poor; very poor. On actual energy certificate shown
as one to five star rating.
- **SECONDHEAT DESCRIPTION** - `SECONDHEAT_DESCRIPTION (VARCHAR)`
97
Overall description of the property feature
- **SHEATING ENERGY EFF** -`SHEATING_ENERGY_EFF (VARCHAR 9)`
Energy efficiency rating. One of: very good; good; average;
poor; very poor. On actual energy certificate shown as one
to five star rating.
- **SHEATING ENV EFF** - `SHEATING_ENV_EFF (VARCHAR 9)`
Environmental efficiency rating. One of: very good; good;
average; poor; very poor. On actual energy certificate shown
as one to five star rating.
- **ROOF DESCRIPTION** - `ROOF_DESCRIPTION (VARCHAR 92)`
Overall description of the property feature
- **ROOF ENERGY EFF** - `ROOF_ENERGY_EFF (VARCHAR 9)`
Energy efficiency rating. One of: very good; good; average;
poor; very poor. On actual energy certificate shown as one
to five star rating.
- **ROOF ENV EFF** -`ROOF_ENV_EFF (VARCHAR 9)`
Environmental efficiency rating. One of: very good; good;
average; poor; very poor. On actual energy certificate shown
as one to five star rating.
- **MAINHEAT DESCRIPTION** - `MAINHEAT_DESCRIPTION (VARCHAR 140)`
Overall description of the property feature
- **MAINHEAT ENERGY EFF** - `MAINHEAT_ENERGY_EFF (VARCHAR 9)`
Energy efficiency rating. One of: very good; good; average;
poor; very poor. On actual energy certificate shown as one
to five star rating.
- **MAINHEAT ENV EFF** -`MAINHEAT_ENV_EFF(VARCHAR 9)`
Environmental efficiency rating. One of: very good; good;
average; poor; very poor. On actual energy certificate shown
as one to five star rating.
- **MAINHEATCONT DESCRIPTION** - `MAINHEATCONT_DESCRIPTION
(VARCHAR 96)`
Overall description of the property feature
- **MAINHEATC ENERGY EFF** `MAINHEATC_ENERGY_EFF (VARCHAR 9)`
Energy efficiency rating. One of: very good; good; average;
poor; very poor. On actual energy certificate shown as one
to five star rating.
- **MAINHEATC ENV EFF** - `MAINHEATC_ENV_EFF (VARCHAR 9)`
Environmental efficiency rating. One of: very good; good;
average; poor; very poor. On actual energy certificate shown
as one to five star rating.
- **LIGHTING DESCRIPTION** -  `LIGHTING_DESCRIPTION (VARCHAR 91)`
Overall description of property feature. Total number of fixed
lighting outlets and total number of low-energy fixed lighting
outlets
- **LIGHTING ENERGY EFF** - `LIGHTING_ENERGY_EFF (VARCHAR 9)`
Energy efficiency rating. One of: very good; good; average;
poor; very poor. On actual energy certificate shown as one
to five star rating.
- **LIGHTING ENV EFF** - `LIGHTING_ENV_EFF (VARCHAR 9)`
Environmental efficiency rating. One of: very good; good;
average; poor; very poor. On actual energy certificate shown
as one to five star rating.
- **MAIN FUEL**- `MAIN_FUEL (VARCHAR 93)`
The type of fuel used to power the central heating e.g. Gas,
Electricity
- **WIND TURBINE COUNT** - `WIND_TURBINE_COUNT (FLOAT)`
Number of wind turbines; 0 if none.
- **HEAT LOSS CORRIDOR** - `HEAT_LOSS_CORRIDOR (VARCHAR 17)`
Flats and maisonettes only. Indicates that the flat contains a
corridor through which heat is lost. Heat loss corridor, one
of: no corridor; heated corridor; unheated corridor
- **UNHEATED CORRIDOR LENGTH** - `UNHEATED_CORRIDOR_LENGTH
(DECIMAL)`
The total length of unheated corridor in the flat. Only
populated if flat or maisonette contains unheated corridor. If
unheated corridor, length of sheltered wall (m²).
- **FLOOR HEIGHT** -`FLOOR_HEIGHT (DECIMAL)`
Average height of the storey in metres.
- **PHOTO SUPPLY** - `PHOTO_SUPPLY (FLOAT)`
Percentage of photovoltaic area as a percentage of total
roof area. 0% indicates that a Photovoltaic Supply is not
present in the property.
- **SOLAR WATER HEATING FLAG** - `SOLAR_WATER_HEATING_FLAG
(VARCHAR 1)`
Indicates whether the heating in the Property is solar
powered.
- **MECHANICAL VENTILATION** - `MECHANICAL_VENTILATION (VARCHAR 30)`
Identifies the type of mechanical ventilation the property
has. This is required for the RdSAP calculation.
- **ADDRESS** - `ADDRESS`
Field containing the concatenation of address1, address2
and address3. Note that post code is recorded separately.
- **LOCAL AUTHORITY NAME** - `LOCAL_AUTHORITY_LABEL`
The name of the local authority area in which the building is
located. This field is for additional information only and
should not be relied upon: please refer to the Local Authority
ONS Code.
- **CONSTITUENCY NAME** - `CONSTITUENCY_LABEL`
The name of the parliamentary constituency in which the
building is located. This field is for additional information
only and should not be relied upon: please refer to the
Constituency ONS Code.
- **POST TOWN** - `POSTTOWN (VARCHAR 37)`
The post town of the property
- **CONSTRUCTION AGE BAND** - `CONSTRUCTION_AGE_BAND (VARCHAR 31)`
Age band when building part constructed. England & Wales
only. One of: before 1900; 1900-1929; 1930-1949;
1950-1966; 1967-1975; 1976-1982; 1983-1990; 1991-1995;
1996-2002; 2003-2006; 2007-2011; 2012 onwards.
- **LODGEMENT DATETIME** - `LODGEMENT_DATETIME (DATETIME2)`
Date and time lodged on the Energy Performance of
Buildings Register.
- **TENURE** - `TENURE (VARCHAR 100)`
Describes the tenure type of the property. One of: Owneroccupied;
Rented (social); Rented (private).
- **FIXED LIGHTING OUTLETS COUNT** - `FIXED_LIGHTING_OUTLETS_COUNT (FLOAT)`
The number of fixed lighting outlets.
- **LOW ENERGY FIXED LIGHTING OUTLETS COUNT** -
`LOW_ENERGY_FIXED_LIGHT_COUNT (FLOAT)`
The number of low-energy fixed lighting outlets.
- **UPRN** - `UPRN (INT)`
The UPRN submitted by an assessor or alternatively from
the department’s address matching algorithm.
- **UPRN SOURCE** - `UPRN_SOURCE (VARCHAR 15)`
Populated with the values "Energy Assessor" or "Address
Matched" to show how the UPRN was populated.



