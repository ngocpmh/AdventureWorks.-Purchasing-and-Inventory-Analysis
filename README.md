# Project Background
AdventureWorks is a large-scale bicycle manufacturing and sales company that produces bicycles made from metal and synthetic materials. The company operates in North America, Europe, and Asia, with its headquarters in Bothell, Washington, and a large workforce. 

The company has significant amounts of data on its sales, purchasing, product offerings, inventory, and operational efficiency that has been previously underutilized. This project thoroughly analyzes and synthesizes this data in order to uncover critical insights that will improve AdventureWorks's commercial success. 

Insights and recommendations are provided on the following key areas:
- **Inventory Management:** ensure real-time tracking of inventory status, value, and storage locations, while proactively detecting reorder points to trigger timely purchases.
- **Purchasing Performance Analysis:** include purchase order tracking and price tracking over time to detect anomalies. Regularly analyze spending across products, categories, and regions to optimize budgeting.
- **Supllier Performance Management:** assess supplier performance based on key metrics like on-time delivery rate, lead time, and product quality to minimize procurement risks.

Tools used: SQL, Excel, SSIS, SSAS, PowerBI
# Data structure
AdventureWorks's database structure includes different function from Sales, Purchasing, Manufacturing, Human Resources etc. With nearly 20.000 customers, over 70.000 orders and 500 products there is enough data for further analysis.

<img width="700" height="433" alt="AdvWorksOLTPSchemaVisio_small" src="https://github.com/user-attachments/assets/ed5bd530-a377-4c85-8c93-2c28ae7a6cf1" />

The project focuses on addressing the business requirements of the **Purchasing and Inventory Department**. First, stakeholder requirements are identified, followed by the definition of KPIs to meet those needs. Based on this, we determine the necessary data from the database to fulfill these requirements, as shown in the data flow below.

![data flow](https://github.com/user-attachments/assets/628809eb-59a7-4af7-bc8e-abf6ec307045)

# Data Warehouse Design
The project used Galaxy Schema to support multidimensional analysis requirements:

<img width="759" height="682" alt="Screenshot 2025-07-23 080719" src="https://github.com/user-attachments/assets/f4fc30f5-420b-447d-a705-059c39d7bb64" />

- **Fact Tables**: Fact InventoryManagement, Fact Purchasing.
- **Dimension Tables**: DimProduct, DimGeography, DimTime, DimShipMethod, DimProductVendor, DimVendor, DimLocation.

# Executive Summary 
**Overview of Findings**
1. **Inventory Management**:

The Inventory Management Dashboard provides a consolidated view of the company’s current inventory status to support decision-making about stock control, replenishment, and storage efficiency. It tracks key metrics such as product quantity, total inventory value, and availability status, helping teams monitor performance and spot early signs of stock shortages.
Additionally, the dashboard highlights which products are below reorder point and need to be reordered whether through external purchasing or internal production. It also visualizes how inventory is distributed across storage locations, offering insights for optimizing warehouse usage and minimizing operational bottlenecks.

<img width="1452" height="833" alt="Screenshot 2025-07-23 083436" src="https://github.com/user-attachments/assets/7927798a-c187-49db-9357-df99fb6bad9e" />

**Insights**: 
- 7 products have fallen below their reorder thresholds and are categorized as critical, which poses an immediate risk of stockout. 4 products are already out of stock, need immediate attention.
- Three locations hold the vast majority of inventory are Subassembly,  Miscellaneous Storage, and Tool Crib (74,88% of total units) => The company’s inventory system relies heavily on intermediate production and staging areas.
- High inventory quantity does not always mean high financial value, as seen in Subassembly and Tool Crib => important for inventory risk management. Zones with high volume require space and workflow optimization, while high-value zones demand stronger controls, security, and financial oversight.
- The Unknown category contains the largest volume of stock, reaching 260,000 unit. These items represent raw materials and semi-finished goods that have not been fully classified into final categories. In contrast, the Bikes category holds only 20,000 units, represents $15 million in inventory value => Bikes are high-value, capital-intensive product.

By looking further into each category,  we can assess the stock status of the products and decide whether to purchase more items.

<img width="871" height="586" alt="image" src="https://github.com/user-attachments/assets/ec7ed1ba-b566-477f-b467-831fbad50e84" />

**Recommendations**:
- For **"Component"** category: For externally sourced components, only 68.42 percent are in Sufficient status. The critical item, ML Mountain Seat/Saddle, has only 355 units in stock, falling below its reorder point of 375, requiring immediate procurement and other at-risk items need attention to ensure timely replinishment.
- For **"Unknown"** Category: the Unknown category functions as a critical source of production materials. To reduce risk, tighter monitoring and earlier supplier coordination should be applied to externally sourced items within this group.

2. **Purchasing Performance Analysis**:

The Purchasing Performance Dashboard is designed to provide an overview of the purchasing efficiency. Its primary goal is to help track and assess key metrics related to procurement, spending, and operational performance, including factors such as total purchase orders, purchase spending, freight costs, return rates, and product availability. These metrics support decision-making to optimize purchasing processes, reduce costs, and improve overall business performance.




 





