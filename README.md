# Ex.05 Design a Website for Server Side Processing
## Date:02/12/2024

## AIM:
 To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side. 


## FORMULA:
P = I<sup>2</sup>R
<br> P --> Power (in watts)
<br> I --> Intensity
<br> R --> Resistance

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :

```
math.html

<!DOCTYPE html>
<html>
<head>
<meta charset='utf-8'>
<meta http-equiv='X-UA-Compatible' content='IE=edge'>
<title>POWER CALCULATOR</title>
<meta name='viewport' content='width=device-width, initial-scale=1'>
<style type="text/css">
body {
    background-color: rgb(9, 68, 151);
     
}
.box{
    border-radius: 20px;
}
.edge {
    width: 100%;
    padding-top: 250px;
    text-align: center;

}
.box {
    display: inline-block;
    border: BLUE;
    width: 600px;
    min-height: 400px;
    font-size: 20px;
    background-color: rosybrown;
}
.formlet{
    margin-top: 20px;
    font-style: oblique;
    font-weight: bold;
}
#formelt {
   border-radius: 5px; 
   margin-top: 20px;
   font-style: oblique;
    font-weight: bold;

}
h1 {
    color: RED;
    padding-top: 20px;
}
.i1{
    font-style: oblique;
    font-weight: bold;
    margin-left: 50px;
    margin-top: 10px;
   
}
#i1{
    border-radius: 32px;
    height: 20px;
    width:220px;
    text-align: none;
}
.r1{
    font-style: oblique;
    font-weight: bold;
    margin-bottom: 20px;
    margin-top: 30px;
}
#r1{
    border-radius: 32px;
    height: 20px;
    width:220px;
    text-align:none
}
.c1{
    font-style: oblique;
    font-weight: bold;
    
}
#c1{
    border-radius: 5px;
    background: rgb(32, 136, 216);
    height: 30px;
    color: white;
    width: 100px;
    border: none;
}
.owner{
    color : rgb(22, 207, 176)
}
p{
    padding-top: 50px;
    font-size: x-large;
    color: azure;
}

</style>
</head>
<body>
    
    <center>
    <h2 class="owner"> <b>DHANUSHKUMAR (24901013)</b></h2>
    <p class="about">Electric power is the rate of transfer of electrical energy within a circuit. Its SI unit is the watt, the general unit of power, defined as one joule per second.</p>
</center>
<div class="edge">
    <div class="box">
        <h1>POWER OF LAMP FILAMENT</h1>
        <form method="POST">
            {% csrf_token %}
            <div class="i1">
                Intensity: <input type="text" name="Intensity" placeholder="Enter Intensity" value="{{i}}" id="i1" > amperes (A)<br/>
            </div>
            <div class="r1">
                Resistance: <input type="text" name="Resistance" placeholder="Enter resistance" value="{{r}}" id="r1"> ohm(Ω)<br/>
            </div>
            <div class="c1">
                <input type="submit" value="Calculate" id="c1"><br/>
            </div>
            <div class="formelt">
                Power: <input type="text" name="power" value="{{power}}" id="formelt">  watts (W)<br/>
            </div>
        </form>
    </div>
</div>
</body>
</html>

views.py

from django.shortcuts import render 
def power(request): 
    context={} 
    context['power'] = "0" 
    context['r'] = "0" 
    context['i'] = "0" 
    if request.method == 'POST': 
        print("POST method is used")
        r = request.POST.get('Resistance','0')
        i = request.POST.get('Intensity','0')
        print('request=',request) 
        print('Resistance=',r) 
        print('Intensity=',i) 
        power = int(r) *int(i) *int(i) 
        context['power'] = power
        context['r'] = r
        context['i'] = i
        print('power=',power) 
    return render(request,'mathapp/math.html',context)

urls.py

from django.contrib import admin 
from django.urls import path 
from mathapp import views 
urlpatterns = [ 
    path('admin/', admin.site.urls), 
    path('power/',views.power,name="calculatepower"),
    path('',views.power,name="calculatepower")
]

```


## SERVER SIDE PROCESSING:


![alt text](<serverside processing (2).png>)

## HOMEPAGE:

![alt text](<home page.png>)


## RESULT:
The program for performing server side processing is completed successfully.
