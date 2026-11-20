# Logistics-Transportation_Fleet-Performance-Delivery-Efficiency
Fleet Operation Dashboard
Fix missing fuel consumption values (Average per Vehicle Type)- since no null value is identified so no action taken
Relate Trips with Vehicle Master- In Power BI Model View, connect Trips[Vehicle_ID] with Vehicle Master[Vehicle_ID] using a One-to-Many (1:*) relationship.
DAX Measures - Go to Modeling → New Measure and enter:- Fuel Efficiency = Distance / Fuel Consumed. [Syntax Fuel effiency = DIVIDE(sum('-trip data Power Query Table'[Distance_km]), sum('-trip data Power Query Table'[Fuel_Consumed_L]),0)}
DAX Measures - On-Time Delivery % = On-Time Trips / Total Trips:- Go to Modeling → New Measure and enter:- [Syntax On-Time Delivery % = On-time Delivery % = divide(calculate(COUNTROWS('-trip data Power Query Table'),'-trip data Power Query Table'[Delivery_Status]="On-Time"), COUNTROWS('-trip data Power Query Table'),0)]
DAX Measures - Cost per km = (Fuel Cost + Maintenance Cost) / Distance- Go to Modeling → New Measure and enter, Syntax Cost per KM = DIVIDE(sum('-trip data Power Query Table'[Fuel Cost]),SUM('-trip data Power Query Table'[Distance_km]),0)
Bar chart: On-Time Delivery % by Route- Clustered Bar Chart, given Route to Y-axis and On-Time Delivery % to X-axis column
Line chart: Fuel Efficiency trend by month- Line Chart, given Delivery_Date to X-axis and Fuel Efficiency to Y-axis.
KPI cards: Avg. Delivery Time, Cost per km- Selected Card visual and drag Avg. Delivery Time measure and selected the Card visual and given Cost per km measure into it.
Map visual: Delivery performance by route (Origin → Destination)- Selected Map visual, add Origin as starting location, Destination as destination, and On-Time Delivery % as performance value
