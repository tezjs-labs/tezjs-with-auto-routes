## Tezjs-with-auto-routes

Tezjs provides file-based routing to automatically create whole application routes. 
When we talk about URL routing then many use cases may arise, like

**1.**  **I wish to create this `/` URL page.**

For that make index.vue file under pages directory.

- Here is the folder structure for that.   
```
    --| pages/  
    -----| index.vue  
```
you can access the above page on URL **localhost:3000/**.  


**2.** **I wish to create `/sign-in` url page.**

For making a sing-in page, make a sing-in.vue file under pages directory.  

- here is the folder structure to make a sign-in page.
```
    --| pages/  
    -----| sign-in.vue  
```
you can access the above page on URL **localhost:3000/sign-in**.

**3.** **I wish to create /users and users/bharat  URL page, But one interesting thing is users/bharat is not the static page, this is a dynamic page as the user-name would change on every user like in mentioned URL bharat is the user name.**

To make such use cases first create one directory with name users and add one file under it 
whose name will be **_user-name.vue**. make sure you add an underscore before the username file. This
is a simple way to add a dynamic page in tezjs

- Here is the folder structure to make a dynamic username page.
```
    --| pages/  
    -----| user/   
    --------| _user-name.vue 
```
you can access above page on URL **localhost:3000/user/anyusername**

**4.** **I wish to show the product-wise comments, so my URL before the forward slash prefix would be dynamic for example `iPhone-se/comments.**

To make such use cases like to make a common page for different products. 
  
- Here are steps to achieve the above goal:  
    1. Add **_productname** directory under pages directory. Make sure you add an underscore before 
       the directory name.
    2. Add **comments.vue** file under _productname directory.  

- here is the folder structure to make a dynamic directory with a common page.  
  
```
    --| pages/  
    -----| _product-name/   
    -------- | commets.vue
```
you can access the above page on URL **localhost:3000/any product name/comments**


**5.** **I wish to create three level dynamic URL.**

- In such use cases let's take an example you want some product page to show all products
when the user clicks on the product you want to show that product's details within the product-details page dynamically.

- Here are steps to achieve the above things:  
     1. create a products directory.
     2. create **index.vue** file under **products** directory.
     3. create a dynamic directory with the name **_productname**
     4. create **index.vue** under __productname directory  

  
here is the folder structure to make a dynamic product details page with a specific product name.
```
    --| pages/  
    -------|products/    
    -----------| _product-name/  
    ----------------| index.vue  
    -----------| index.vue
```

you can access the above products-list on URL **localhost:3000/products** and can access the specific product-details page on URL **localhost:3000/products/any product name**

**Note:**  Use the **tez-link** component to navigate between your project pages  
```
<template>   
    <tez-link to="/">Home</tex-link>    
</template>    
```

**Note:** You can access all dynamic route's params with `$tezRoute.params['your params]`
