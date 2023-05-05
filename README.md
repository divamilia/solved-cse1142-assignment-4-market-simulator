Download Link: https://assignmentchef.com/product/solved-cse1142-assignment-4-market-simulator
<br>
In this homework, you will simulate a market. The market buys food from a set of firms. It keeps track of firms and bought food in txt files which makes it difficult to store and manage records <a href="http://tureng.com/en/turkish-english/systematical">systematicall</a>y. Therefore, the owner of the market needs a program which can read txt files and store/manage information as he/she wants.

Your program should read two files: <strong>firms.txt</strong> and <strong>products.txt</strong>. The details of both files are given below.

<ol>

 <li>Each firm with a unique id and name is recorded in the <strong>firms.txt</strong> file and format of the file is given below:</li>

</ol>

 [id of the firm] [name of the firm] ◦ For example; &#x25aa; 101 eti

&#x25aa; 102 ulker etc.

<ol>

 <li>You will read <em>id</em> and <em>name</em> of the firms from the <strong>txt</strong> file and store in a <strong>linked list</strong>. To create the linked list, you will use the <strong>Firm</strong> struct with the following data fields:

  <ul>

   <li><em>firmID</em> (int) : id of the firm</li>

   <li><em>firmName</em> (char array of size 100) : name of the firm  <em>struct Firm *nextfirm</em> : pointer to next firm.</li>

   <li>Typedef struct Firm to firm.</li>

  </ul></li>

 <li>To read the file you will write a function with name</li>

</ol>

<strong>firm *readFirms(char filename[])</strong>

◦ <em>filename[] :</em> name of the file to be read

◦ This function should be called by your main function with the <strong>firms.txt</strong> file.

◦ In this function, you will read the file whose name is given as argument <em>filename.</em>

◦ You will create a <strong>linked list</strong> of the firms by using <em>firm </em>struct. Each time you read a firm from the file you will create a firm struct by using <strong>malloc</strong> and store read values in it.

Then, you should add it as a new member to the linked list.

◦ While adding a new member to the linked list, <strong>id</strong> fields of the firms should be arranged in descending order. For example,

&#x25aa; Firstly, you read “101 eti” and this firm becomes the first element of the linked list.

&#x25aa; Secondly, you read “300 ulker”. At this point, <em>ulker</em> becomes the first element of the linked list and <em>eti</em> becomes the second element of the linked list because of having smaller id than <em>ulker</em>.

&#x25aa; Then, if you read “273 pinar”, <em>pinar</em> should be placed between <em>ulker</em> and <em>eti</em>. Consequently, <em>ulker</em> becomes the first, <em>pinar</em> becomes the second and <em>eti</em> becomes the third element of the linked list.

◦ This function returns a pointer that points to the beginning of the linked list.

<ol start="2">

 <li>After constructing the linked list of the firms, you will print all firms in the linked list and their alldata fields by using <strong>printFirms</strong></li>

</ol>

<strong>void printFirms(firm *firmptr)</strong>

<ul>

 <li>This function takes a pointer of type firm (<em>firmptr</em>) and prints all firms and their all data fields in the linked list pointed by</li>

 <li>For example, if the content of the firms.txt file is as given below</li>

</ul>

101 eti

300 superfresh

502 pinar 91 banvit then, the output is

502 pinar

300 superfresh

101 eti

91 banvit

<ol start="3">

 <li>Information about bought food is stored in <strong>txt</strong> file and format of the file is given below:  [name of the firm] [name of the food] [type of the food] [amount of food]

  <ul>

   <li>For example, if the market buys <em>5 </em>packages of a food of type <em>biscuit</em> with name <em>burcak</em> from firm <em>eti</em>, this purchase is written in the file as</li>

  </ul></li>

</ol>

◦ eti burcak biscuit 5

<ul>

 <li>You will read the products from the <strong>txt</strong> file and store read values in a<strong> linked list. </strong></li>

</ul>

<ol>

 <li>To create a linked list, you will use the <strong>FoodStock</strong> struct FoodStock contains another struct inside it which is <em>struct <strong>Food. Food </strong></em>will be used to keep name and expire date of each food since they are kept by the market also.  Expire date will be stored in day, month and year format. Create a Food struct with following data fields :</li>

</ol>

◦ <em>prod_name</em> (char array of size 400) : name of the food

◦ <em>exp_day </em>(int) : day of expire date

◦ <em>exp_month </em>(int) : month of expire date ◦ <em>exp_year</em> (int) : year of the expire date ◦ Typedef struct Food to food.

<ol>

 <li>Content of the <strong>FoodStock</strong> struct is given below

  <ul>

   <li><em>struct Food ffood</em> : struct to store information about a specific food  <em>struct FoodStock *nextfood</em> : pointer to the next food  Typedef struct FoodStock to foodstock.</li>

  </ul></li>

</ol>

<ol>

 <li>c) To read the <strong>txt</strong> file you will use the <strong>readFoods</strong> function. This function should be called by your main function. <strong>foodstock *readFoods(char filename[])</strong></li>

</ol>

<ul>

 <li><em>filename[] : </em>name of the file to be read</li>

 <li>In this function you will create a linked list of read products. For example,</li>

</ul>

◦ Firstly, you read “<em>eti burcak biscuit 5</em>” from the file. You will create a linked list with <em>5 foodstock </em>elements (you will use <strong>malloc</strong> to create structs) and <em>prod_name</em> of these elements will be “<em>eti burcak biscuit</em>”. For expire date information of each <em>ffood</em>  field of <em>foodstock </em>struct, you will assign 2018 or 2019 to <em>exp_year</em> randomly. You will assign 1,2,3 or 4 randomly for <em>exp_month</em> and a number created randomly between 1 and 14 will be assigned to <em>exp_day</em>.

◦ Then, if you read “<em>ulker golf ice_cream 4</em>”, you will add <em>4 foodstock </em>elements to the end of the linked list (immediately after the eti burcak biscuits). Each of them will have <em>prod_name</em> of “<em>ulker golf ice_cream</em>” and you will assign random day, month and year values for the expire date as explained above.

◦ After adding above items, you should have a linked list with 9 <strong>foodstock </strong>structs.

◦ Each time you read a new food from <strong>products.txt</strong> file you will add them to the end of the linked list.

◦ You will return a pointer that points to the beginning of the linked list.

<ol start="4">

 <li>To print information about food, you will use the <strong>printFood</strong></li>

</ol>

<strong>void printFood(foodstock *foodptr, char filename[])</strong>

<ul>

 <li><em>foodptr</em> : pointer to a linked list</li>

 <li><em>filename[]</em> : name of the file to which the output will be written.</li>

 <li>This function reads all elements and their data fields in a linked list pointed by <em>foodptr </em>and writes this information to a txt file whose name is taken as argument</li>

</ul>

<ol start="5">

 <li>The market periodically controls expired products and expired products should be removed from the list of foods. To remove expired products, you will use the <strong>stockOut</strong></li>

</ol>

<strong>foodstock *stockOut(foodstock *foodptr, int day, int month, int year)</strong>

<ul>

 <li><em>foodptr </em>: pointer to linked list of foods</li>

 <li><em>day, month, year </em>: day, month and year of the expire date according to which the expired foods are detected. These values will be given by the user.</li>

 <li>For example, if day = 3, month = 1 and year = 2019, the products that have expire date before 3/1/2019 will be deleted from the linked list.</li>

 <li>Pointer to the new state of the linked list is returned.</li>

</ul>

<ol start="6">

 <li>In the main function of your program, implement the following scenario.

  <ul>

   <li>Create a <strong><em>firms</em></strong> pointer of type <strong>firm</strong>.</li>

   <li>Read the firms by using the <strong>readFirms</strong> function from <strong>txt</strong> file and update the value of <strong><em>firms</em></strong> pointer as the return value of <strong>readFirms</strong> function.</li>

   <li>Print firms by using the <strong>printFirms</strong></li>

   <li>Create a <strong><em>stocks</em></strong> pointer of type <strong>foodstock</strong>.</li>

   <li>Read the products from the <strong>txt</strong> file by using the <strong>readFoods</strong> function and update the value of <strong><em>stocks</em></strong> pointer as the return value of <strong>readFoods</strong> function.</li>

   <li>Print the initial situation of the linked list pointed by <strong><em>stocks</em></strong><em> by </em>calling<em> <strong>printFoods</strong> </em>function and name of the output file will be<em> <strong>“initial_stock.txt” </strong></em> Print the following message on console display:</li>

  </ul></li>

</ol>

<em>“Please enter the day, month and year to be checked” </em>

Then, take the <em>day, month </em>and<em> year </em>from the user that will be used as the expire date for the <strong>stockOut</strong> function.

<ul>

 <li>Call the <strong>stockOut</strong> function with <strong><em>stocks</em></strong> pointer and the expire date entered by the user. The updated version of the linked list will be pointed by <strong><em>stocks</em></strong></li>

 <li>Print the updated version of the linked list pointed by <strong><em>stocks</em></strong> pointer by using <strong>printFoods</strong> function and the name of the output file will be <strong><em>“final_stock.txt” </em></strong>for the second time<em>.</em></li>

</ul>

<ol start="7">

 <li><em>Sample output:</em>

  <ul>

   <li>Assume that content of the <strong>txt</strong> file is as given below</li>

  </ul></li>

</ol>

101 eti

300 superfresh

502 pinar

91 banvit

<ul>

 <li>Assume that content of the <strong>txt</strong> file is as given below <em>eti burcak biscuit 4 ulker golf ice_cream 2 sutas kaymakli yoghurt 3</em></li>

 <li>Your program should print the firms to the screen and requests an expire date from the user as shown below:</li>

</ul>

Firms :

firm no 502           firm name pinar firm no 300      firm name superfresh firm no 101     firm name eti

firm no 91            firm name banvit

Please enter the day, month and year to be checked:

1 4 2019

<ul>

 <li>Content of the <strong>txt</strong> file will become as shown below eti burcak biscuit EXP : 2/3/2019 eti burcak biscuit EXP : 6/2/2019 eti burcak biscuit EXP : 11/1/2019 eti burcak biscuit EXP : 4/3/2019 ulker golf ice_cream EXP : 7/4/2019 ulker golf ice_cream EXP : 1/1/2018 sutas kaymakli yoghurt EXP : 3/1/2019 sutas kaymakli yoghurt EXP : 1/4/2019 sutas kaymakli yoghurt EXP : 3/3/2018</li>

 <li>Content of the <strong>txt</strong> file will become as shown below ulker golf ice_cream EXP : 7/4/2019 sutas kaymakli yoghurt EXP : 1/4/2019</li>

</ul>

<strong>This is a simple scenario to test your  implementation. There might be other test cases too. Therefore, please pay attention to use the same function and variable names in your implementations. You can not decrease the number of functions.</strong>