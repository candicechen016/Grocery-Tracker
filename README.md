# Grocery Tracker

Here is the [demo](https://mediaspace.illinois.edu/media/t/1_hlkk0j03) vedio for demonstration of all fuctionalities. 

Our application consists of three tabs:
* At Home
* To Buy
* Find Stores  

We created 10 tables of relational database using MySQL database.
</br>
## Application Introduciton

### At Home
The main page for users to manage their purchased items.
We provide three storage spaces, fridge, freezer, and pantry for users to manage their purchased items. Each row has item name, amount, and expiration date. Users can edit all of the information. 
![AtHome](https://user-images.githubusercontent.com/89559531/186767080-ef6dc220-67c7-46f1-9fa3-25a5b44763bd.png)
![Product - AddToHome](https://user-images.githubusercontent.com/89559531/186768065-66802140-75db-48c5-b3cc-786de636ae3a.png)



### To Buy
Users can create their own shopping list, like **Frequent Items** or **birthday party** and put items into the lists. 
![ToBuy (short)](https://user-images.githubusercontent.com/89559531/186767678-2a99f3fa-385a-45fc-8b8c-82ff502fd4c7.png)
![Product - AddToBuy](https://user-images.githubusercontent.com/89559531/186768122-7b6d7b15-177e-4738-818a-294df1492e86.png)



### Find Stores
Users can search grocery stores information at this page. 
![FindStores](https://user-images.githubusercontent.com/89559531/186767799-a1ea40f5-009d-4ec9-a8f8-85c49b11c216.png)


## Advanced Database Functions
### Stored procedure
For our stored procedure, we wanted to provide the users a good estimate of how much they would be spending per shopping list in the To Buy tab. To achieve this we used two stored procedures. The first store procedure takes the product name as the input, and it returns the minimal price of the given product sold in all available stores. The reason for this store procedure is that we believe customers always would like to know what is the cheapest price of the products they are interested in. 
 
The second store procedure takes the shopping list as the input, and it calculates a sum of all the estimated prices given the shopping list. For each product in the shopping list, the procedure will find the minimum price of that product in all available area, and then the estimated price will be multiplied by the total amount to get the total price for that product. By iterating through all products in the shopping list, the procedure will return the lower bound of the total price of that shopping list.

### Trigger 
We has a trigger which executes after inserting a new row in the has table. A new row will be inserted into the has table when the user buys an item (controlled by user interface). The trigger will automatically create an inventory list if the list that was added in the has table does not exist. Our main goal is to trace where the food is stored, so every item the users bought should be in the inventory list.

