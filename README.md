# Design a Website for Server Side Processing

## AIM:
To design a website to perform mathematical calculations in server side.

## DESIGN STEPS:

## Step 1:

Desing your website for calculation using wireframe work.

## Step 2:

Then to execute the wireframe work desing use html,css

## Step 3:

Use views.py to execute the coding in serverside.

## Step 4:

Mention the path of the website in urls.py.

## Step 5:

Publish the website in the given URL'jayabharathi3.student.saveetha.in'

## Step 6:

Publish the website in the given URL.

## PROGRAM :
```
DEVELOPED BY: JAYABHARATHI.S
REGISTER NUMBER : 212222100013

## math.html

<html>
<head>
<meta charset='utf-8'>
<meta http-equiv='X-UA-Compatible' content='IE=edge'>
<title>Area of Triangle</title>
<meta name='viewport' content='width=device-width,initial-scales=1'>
<style>
body {
background-color:cyan;
}
.edge {
width: 1080px;
margin-left: auto;
margin-right: auto;
padding-top: 200px;
padding-left: 300px;
}
.box {
display:block;
border: Thick dashed lime;
width: 600px;
min-height: 300px;
font-size: 20px;
background-color:pink;
}
.formelt{
color: red;
text-align: center;
margin-top: 10px;
margin-bottom: 10px;
}
h1{
color: yellow;
text-align: center;
padding-top: 30px;
}
</style>
</head>
<body>
<div class="edge">
<div class="box">
<h1>Area of a Triangle</h1>
<form method="POST">
{% csrf_token %}
<div class="formelt">
Breadth : <input type="text" name="breadth" value="{{b}}"></input>(in m)<br/>
<div clss="formelt">
Height : <input type="text" name="height" value="{{h}}"></input>(in m)<br/></div>
<div class="formelt">
<input type="submit" value="calculate"></input><br/>
</div>
<div class="formelt">
Area :  <input type="text" name="area" value="{{area}}"></input>m<sup>2</sup><br/>
</div>
</form>
</div>
</div>
</body>
</html>


## views.py

from django.shortcuts import render
def triarea(request):
    context={}
    context['area']="0"
    context['b']="0"
    context['h']="0"
    if request.method == 'POST':
        print("POST method is used")
        b = request.POST.get('breadth','0')
        h = request.POST.get('height','0')
        print('request=',request)
        print('Breadth=',b)
        print('height=',h)
        area = (int(b) * int(h))/2
        context['area'] = area
        context['b'] = b
        context['h'] = h
        print('Area=',area)
    return render(request,'myapp/math.html',context) 


## urls.py

from django.contrib import admin
from django.urls import path
from myapp import views


urlpatterns = [
    path('admin/', admin.site.urls),
    path('areaoftriangle/',views.triarea,name="areaoftriangle"),
    path('',views.triarea,name="areaoftriangleroot")
]

```

## CLIENT OUTPUT:

![areaoftri](https://github.com/Jayabharathi3/serversideprocessing/assets/120367796/e537db5a-15ea-48c7-b1c9-8c2e74e346a7)


## SERVER OUTPUT:

![servertri](https://github.com/Jayabharathi3/serversideprocessing/assets/120367796/fbe4a640-363c-4455-b997-ddee511e2cbf)


## Result:

A website to perform mathematical calculations in server side is created
