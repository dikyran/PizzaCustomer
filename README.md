# PizzaCustomer
Visualization of Pizza Data Sales with Power BI

Data Visualisasi adalah representasi grafis dari informasi dan data. Tujuan utamanya adalah menyampaikan informasi dengan cara yang mudah dipahami dan dapat diinterpretasikan secara visual. 
Dengan menggunakan elemen visual seperti grafik, diagram, peta, dan warna, data visualisasi membantu mengidentifikasi pola, tren, dan wawasan dari kumpulan data yang kompleks.

Dalam membuat Visualisasi pada data penjualan Pizza, pertama-tama saya mengolah file csv(Comma-Separated Values) nya terlebih dahulu menggunakan SQL Server Management Studio. Setelah itu, saya
melakukan running code SQL untuk mencari KPI's (Key Performance Indicator) untuk mendapat insight pada pembuatan visualisasi data bisnis. Selanjutnya, file csv tersebut saya import ke Power BI
serta melakukan cleaning data menggunakan Power Query pada Power BI. 
![image](https://github.com/dikyran/PizzaCustomer/assets/113019725/9dde2fae-667d-4c8d-911d-5b3a6599aa22)



**Berikut merupakan code SQL untuk mencari KPI's:**

1. Total Revenue:
SELECT SUM(total_price) AS Total_Revenue FROM pizza_sales

![image](https://github.com/dikyran/PizzaCustomer/assets/113019725/f48e878f-36a0-412a-995a-6981f97c51e8)



2. Average Order Value
SELECT (SUM(total_price) / COUNT(DISTINCT order_id)) AS Avg_order_Value FROM pizza_sales

![image](https://github.com/dikyran/PizzaCustomer/assets/113019725/3aeabf0b-027b-4691-a5f9-ceb6a211c830)


3. Total Pizzas Sold
SELECT SUM(quantity) AS Total_pizza_sold FROM pizza_sales

![image](https://github.com/dikyran/PizzaCustomer/assets/113019725/c4b13ddc-775a-407b-958c-cae205660eaf)




4. Total Orders
SELECT COUNT(DISTINCT order_id) AS Total_Orders FROM pizza_sales

![image](https://github.com/dikyran/PizzaCustomer/assets/113019725/f20d3b2d-31aa-4612-9ec2-61a36d6024e5)




5. Average Pizzas Per Order
SELECT CAST(CAST(SUM(quantity) AS DECIMAL(10,2)) / 
CAST(COUNT(DISTINCT order_id) AS DECIMAL(10,2)) AS DECIMAL(10,2))
AS Avg_Pizzas_per_order
FROM pizza_sales

![image](https://github.com/dikyran/PizzaCustomer/assets/113019725/7111fd11-0418-4d8c-99c0-fefe163f3902)




