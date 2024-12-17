# Ex.08 Design of Interactive Image Gallery
## Date:16-12-2024

## AIM:
To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for positioning and styling.

### Step 4:
Write JavaScript program for implementing interactivity.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
gallery.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Celebrity Photo Gallery</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            background-color: #111;
            color: #fff;
        }
        h1 {
            text-align: center;
            margin: 20px 0;
            font-size: 2.5rem;
        }
        .gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
            padding: 20px;
        }
        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            cursor: pointer;
        }
        .gallery-item img {
            width: 200px;
            height: 400px;
            object-fit: cover;
            transition: transform 0.3s ease-in-out, box-shadow 0.3s;
        }
        .gallery-item:hover img {
            transform: scale(1.1);
            box-shadow: 0 8px 15px rgba(255, 255, 255, 0.2);
        }
        .caption {
            position: absolute;
            bottom: 0;
            background: rgba(255, 254, 254, 0.6);
            width: 100%;
            text-align: center;
            padding: 10px;
            font-size: 1.1rem;
            transition: transform 0.3s;
        }
        .gallery-item:hover .caption {
            transform: translateY(-10px);
        }
        
        /* Lightbox */
        #lightbox {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            align-items: center;
            justify-content: center;
            z-index: 1000;
        }
        #lightbox img {
            max-width: 90%;
            max-height: 90%;
            border: 3px solid #fff;
            border-radius: 10px;
        }
        #lightbox:target {
            display: flex;
        }
        
        #lightbox span {
            position: absolute;
            top: 20px;
            right: 30px;
            font-size: 2rem;
            color: #fff;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Photo Gallery</h1>
    <div class="gallery">
        <a href="#lightbox1" class="gallery-item">
            <img src="jr.jpg" alt="Jayam Ravi">
            <div class="caption">Jayam Ravi</div>
        </a>
        <a href="#lightbox2" class="gallery-item">
            <img src="str.jpg" alt="Simbu">
            <div class="caption">Simbu</div>
        </a>
        <a href="#lightbox3" class="gallery-item">
            <img src="vijay.jpg" alt="Thalapathy Vijay">
            <div class="caption">Thalapathy Vijay</div>
        </a>
        <a href="#lightbox4" class="gallery-item">
            <img src="sk.jpg" alt="Siva Karthikeyan">
            <div class="caption">Siva Karthikeyan</div>
        </a>
        <a href="#lightbox5" class="gallery-item">
            <img src="ajith.jpg" alt="Ajith Kumar">
            <div class="caption">Ajith Kumar</div>
        </a>
    </div>
</body>
</html>

```

## OUTPUT:
![alt text](<Screenshot (19).png>)
## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
