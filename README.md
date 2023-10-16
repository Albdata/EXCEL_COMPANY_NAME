# EXCEL_COMPANY_PHONE


Let's analyze the profit that a Company Phone has through Excel. I edited this DB by adding new columns either taking them from other DataBases or creating them from zero.

This is a DB which consists of Clients info (ID,Nombre completo, Fecha de nacimiento, Dirección, Localidad y Código postal, Teléfono,
Correo electrónico, Fecha de alta, Grupo de clientes. This is going to be what I called "Raw Data" in my project since I find it appropiate to add more columns in order to make a more exhaustive analysis.

Now, I'm going to explain all the steps I took to complete the DB.

1) Creating new columns:
   
   1.1) Edad --> =SIFECHA(C2;HOY();"y"), the column C2 is "Fecha de nacimiento".
   
   1.2) Ciudad --> Madrid, Barcelona, Varsovia, París, Marsella, Berlín, Liverpool, and Londres.
   
   1.3) País --> =SI(O(E2="Madrid"; E2="Barcelona"); "España"; SI(O(E2="Londres"; E2="Liverpool"); "Inglaterra"; SI(O(E2="París"; E2="Marsella"); "Francia"; 
        SI(E2="Varsovia"; "Polonia"; SI(E2="Berlín"; "Alemania"))))).
   
   1.4) Año Alta --> =AÑO(G2), the column G2 is Fecha de Alta.
   
   1.5) Added Precio Venta Producto from another DB.
   
   1.6) Precio Proveedor --> =I2*0,4, what I did here is to add the former price the company gets the products from the supplier by taking into account the company 
        gets a 40% tota income.
   
   1.7) Beneficio --> =I2-J2; Precio Venta producto, Precio Proveedor. This is the real profit I get taking into account all the costs; it's not the income, which 
        is the benefit I would get if I just calculated the amount by which my products are sold.
   
   1.8) Grupo Clientes, I modified this column by addinf thre new categories: Golden , Silver and Bronze. And how did I established this? by keeping in mind the 
        entry date of my clients so, --> =SI(H2<=2009;"Golden";SI(Y(H2>=2010;H2<=2015);"Silver";SI(H2>=2016;"Bronze"))).
   
   1.9) I added Fecha Pedido, Id Pedido, and Fecha Envío from another DB.
   
   1.10) I extracted the month from the Fecha de Envío column --> =TEXTO(O2;"MMMM").
   
   1.11) Período de Espera --> = O2-M2 (Fecha Envio - Fecha Pedido).
   
   1.12) Prioridad Pedido --> =SI(Q2<=5;"Máxima";SI(Q2<=20;"Normal";"Baja")); so, depending on the time the client receives their order, there is a type of order 
         (Baja , Normal, Máxima).
   
   1.13) Producto y Marca "=IZQUIERDA(S2;ENCONTRAR(" "; S2) - 1)". I created the column Productos by creating another column with random numbers and then 
         associating them with the new column --> ALEATORIO().
   

2) Cleaning DATA:
   
   2.1) Remove Duplicates.
   
   2.2) Find and Replace Data.
   
   2.3) Create new categories to simplify the Data.


3) Pivot Table.

   3.1) Once, I do have the DataBase ready, I inserted a few pivot tables to organize the information; I'm going to dispay in a Dashboard later.
   
   3.2) I created an area chart to display the profit by brand (Apple, Samsung, Xiaomi, etc...)
   
   3.3) A pie chart to display the total profit by country.
   
   3.4) A bar chart to display the profit by entry date.
   
   3.5) A line chart to display the total benefit per month.
   
   3.6) Finally, to complete the information I inserted three slicers (País, Clientes, Pedidos).


4) Dashboard:

   4.1) The last step is to display all the information the company needs in order to increase its efficiency.
   
   4.2.) I chose a combination of a dark blue and yellow to stand out the most important information from the graphs.

I'll split the project into four parts: Raw Data, Working Sheet, Pivot Table, and Dashboard.
   


   


   


   

