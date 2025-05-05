# Grocery-Inventory-dataset

Overall, this dataset provides a versatile resource for those interested in inventory management, sales analysis, and supply chain optimization. By leveraging the structured data, businesses can make data-driven decisions to enhance operational efficiency and maximize profitability.

1. search 2. collect 3. analyse 4. clean dataset 5. organized informations

https://www.kaggle.com/datasets/willianoliveiragibin/grocery-inventory/data

Sales Dataset Inventory and Sales Data for Grocery Store Management.

1. Data Cleaning
Missing/null values
Duplicates
Inconsistent formatting (e.g., text casing, whitespace)
Proper data types

2. Analysis
Identify numerical (continuous) vs categorical columns
Summary statistics (mean, median, count, etc.)
Group-wise aggregation (e.g., by category or supplier)

3. Visualization
Bar plots for counts by category/supplier
Pie chart of category distribution
Histograms or box plots for price/cost/distribution
Time trends if dates are involved (e.g., expiry, stock updates)

1. Data Cleaning
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 990 entries, 0 to 989
Data columns (total 17 columns):
 #   Column                   Non-Null Count  Dtype 
---  ------                   --------------  ----- 
 0   product_name             990 non-null    object
 1   category                 989 non-null    object    - CONTAINS 1 NULL VALUE
 2   supplier_name            990 non-null    object
 3   warehouse_location       990 non-null    object
 4   status                   990 non-null    object
 5   product_id               990 non-null    object
 6   supplier_id              990 non-null    object
 7   date_received            990 non-null    object
 8   last_order_date          990 non-null    object
 9   expiration_date          990 non-null    object
 10  stock_quantity           990 non-null    int64 
 11  reorder_level            990 non-null    int64 
 12  reorder_quantity         990 non-null    int64 
 13  unit_price               990 non-null    object
 14  sales_volume             990 non-null    int64 
 15  inventory_turnover_rate  990 non-null    int64 
 16  percentage               990 non-null    object
dtypes: int64(5), object(12)
memory usage: 131.6+ KB

category_null= df[df['category'].isna()]
print(category_null)

 product_name category supplier_name  warehouse_location        status  \
572      Cabbage      NaN         Rooxo  2 Butterfield Pass  Discontinued   

      product_id  supplier_id date_received last_order_date expiration_date  \
572  10-378-9729  83-941-9620    12/23/2024      11/26/2024       9/21/2024   

     stock_quantity  reorder_level  reorder_quantity unit_price  sales_volume  \
572              69             21                68     $66.55            36   

     inventory_turnover_rate percentage  
572                       35        22%  

df.loc[df['product_name'] == 'Cabbage', 'category'] = 'Vegetables'
Empty DataFrame
Columns: [product_name, category, supplier_name, warehouse_location, status, product_id, supplier_id, date_received, last_order_date, expiration_date, stock_quantity, reorder_level, reorder_quantity, unit_price, sales_volume, inventory_turnover_rate, percentage]
Index: []
-------------------------------------------------------------------------------------------------------
df.isna().sum()

product_name               0
category                   0
supplier_name              0
warehouse_location         0
status                     0
product_id                 0
supplier_id                0
date_received              0
last_order_date            0
expiration_date            0
stock_quantity             0
reorder_level              0
reorder_quantity           0
unit_price                 0
sales_volume               0
inventory_turnover_rate    0
percentage                 0
dtype: int64

after cleaning:
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 990 entries, 0 to 989
Data columns (total 17 columns):
 #   Column                   Non-Null Count  Dtype         
---  ------                   --------------  -----         
 0   product_name             990 non-null    object        
 1   category                 990 non-null    object        
 2   supplier_name            990 non-null    object        
 3   warehouse_location       990 non-null    object        
 4   status                   990 non-null    object        
 5   product_id               990 non-null    object        
 6   supplier_id              990 non-null    object        
 7   date_received            990 non-null    datetime64[ns]
 8   last_order_date          990 non-null    datetime64[ns]
 9   expiration_date          990 non-null    datetime64[ns]
 10  stock_quantity           990 non-null    int64         
 11  reorder_level            990 non-null    int64         
 12  reorder_quantity         990 non-null    int64         
 13  unit_price               990 non-null    object        
 14  sales_volume             990 non-null    int64         
 15  inventory_turnover_rate  990 non-null    int64         
 16  percentage               990 non-null    object        
dtypes: datetime64[ns](3), int64(5), object(9)
memory usage: 131.6+ KB


2. Analysis
   
Identify numerical (continuous) vs categorical columns
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 990 entries, 0 to 989
Data columns (total 17 columns):
 #   Column                   Non-Null Count  Dtype         
---  ------                   --------------  -----         
 0   product_name             990 non-null    object        		-category
 1   category                 990 non-null    object        		-category
 2   supplier_name            990 non-null    object        		-category
 3   warehouse_location       990 non-null    object        		-category
 4   status                   990 non-null    object        		-category
 5   product_id               990 non-null    object        		-category
 6   supplier_id              990 non-null    object        		-category
 7   date_received            990 non-null    object			      -date and time  -need to change it to date and time
 8   last_order_date          990 non-null    object		      	-date and time 	-need to change it to date and time
 9   expiration_date          990 non-null    object			      -date and time  -need to change it to date and time
 10  stock_quantity           990 non-null    int64         		-continuous
 11  reorder_level            990 non-null    int64         		-continuous
 12  reorder_quantity         990 non-null    int64         		-continuous
 13  unit_price               990 non-null    object        		-continuous  -need to change it to float
 14  sales_volume             990 non-null    int64         		-continuous
 15  inventory_turnover_rate  990 non-null    int64         		-continuous
 16  percentage               990 non-null    object        		-continuous  -need to change it to float		
dtypes: datetime64[ns](3), int64(5), object(9)
memory usage: 131.6+ KB


