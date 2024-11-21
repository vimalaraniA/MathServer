# Ex.05 Design a Website for Server Side Processing
## AIM:
To design a website to find surface area of a Right Cylinder in server side.

## FORMULA:
Surface Area = 2Πrh + 2Πr<sup>2</sup>
<br>r --> Radius of Right Cylinder
<br>h --> Height of Right Cylinder

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
<html>
<head>
<meta charset='utf-8'>
<meta http-equiv='X-UA-Compatible' content='IE=edge'>
<title>Area of Surface</title>
<meta name='viewport' content='width=device-width, initial-scale=1'>
<style type="text/css">
body {
    background-color: #0d8d88f2;
}
.edge {
    width: 100%;
    padding-top: 180px;
    text-align: center;
}
.box {
    display: inline-block;
    border: thick dashed #cd4f8e;
    width: 500px;
    min-height: 300px;
    font-size: 20px;
    background-color: rgb(67, 122, 204);
}
.formelt {
    color: black;
    text-align: center;
    margin-top: 8px;
    margin-bottom: 6px;
}
h1 {
    color: black;
    padding-top: 20px;
}
</style>
</head>
<body>
<div class="edge">
    <div class="box">
        <h1>Surface Area of Right Cylinder</h1>
        <h3>jaswanth S (212223220037)</h3>
        <form method="POST">
            {% csrf_token %}
            <div class="formelt">
                Radius: <input type="text" name="radius" value="{{r}}"></input>m<br/>
            </div>
            <div class="formelt">
                Height: <input type="text" name="height" value="{{h}}"></input>m<br/>
            </div>
            <div class="formelt">
                <input type="submit" value="Calculate"></input><br/>
            </div>
            <div class="formelt">
                Area: <input type="text" name="area" value="{{area}}">m<sup>2</sup><br/>
            </div>
        </form>
    </div>
</div>
</body>
</html>
```
```
views.py

from django.shortcuts import render
def surfacearea(request):
    context = {}
    context['area'] = "0"
    context['r'] = "0"
    context['h'] = "0"
    if request.method == 'POST':
        print("POST method is used")
        print('request.POST:', request.POST)
        r = request.POST.get('radius', '0') 
        h = request.POST.get('height', '0') 
        print('radius =', r)
        print('height =', h)
        area = 2 * 3.14 * int(r) * int(h) + 2*3.14*int(r)*int(r)
        context['area'] = area
        context['r'] = r
        context['h'] = h
        print('Area =', area)
    
    return render(request, 'mathapp/math.html',context)
```
```
urls.py

from django.contrib import admin
from django.urls import path
from mathapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('surfacearea/',views.surfacearea,name="surfacearea"),
    path('',views.surfacearea,name="surfcaearea")
]
```


## SERVER SIDE PROCESSING:
![image](https://github.com/23013633/MathServer/assets/150005961/d00a40b8-0483-4a23-b009-7a83d74113c9)


## HOMEPAGE:
![Screenshot 2024-05-09 091709](https://github.com/23013633/MathServer/assets/150005961/c8f50202-3207-4ba1-988b-f4625ca3fa32)



## RESULT:
The program for performing server side processing is completed successfully.

