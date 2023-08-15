# **Web Design Tips**

**What is the most popular desktop screen size in 2023?**  
1920 x 1080  

**What is the most used tablet resolution in website design?**  
768 × 1024  

**What is the most used mobile resolution in website design?**  
360 x 800  


## Center a div 5 methods

```console
<div class="h-screen bg-gray-200 w-full ">
    <div class="w-40 h-40 bg-red-600 top-1/2 left-1/2 absolute transform -translate-x-1/2">
     </div>
 </div>





 <div class="h-screen bg-gray-200 w-full grid place-items-center">
     <div class="w-40 h-40 bg-red-600 ">
         </div>
  </div>



// Fir newsletter etc.

<div class="h-screen bg-gray-200 w-full ">
    <div class="w-40 h-40 bg-red-600 top-1/2 left-1/2 absolute transform -translate-x-1/2">
        </div>
  </div>




<div class="h-screen bg-gray-200 w-full">
    <div class="w-40 h-40 bg-red-600 mx-auto">
        </div>
   </div>



<div class="h-screen bg-gray-200 w-full text-center">
    <div class="w-40 h-40 bg-red-600 inline-block">
        </div>
 </div>
```



Note: The best way to center a div is to use flexbox or grid in TailwindCSS.