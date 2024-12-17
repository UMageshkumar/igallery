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
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Photo Gallery</title>
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            background: linear-gradient(135deg, #1f1f1f, #3d3d3d);
            color: #fff;
            overflow-x: hidden;
        }
        h1 {
            text-align: center;
            margin: 20px 0;
            font-size: 3rem;
            letter-spacing: 2px;
            text-transform: uppercase;
            background: -webkit-linear-gradient(45deg, #0e98dd, #0ab4df);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            padding: 20px;
            margin: 0 auto;
            max-width: 1200px;
        }
        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 15px;
            transition: transform 0.4s ease-in-out, box-shadow 0.4s;
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.5);
        }
        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.4s ease-in-out;
        }
        .gallery-item:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 20px rgba(255, 107, 107, 0.3);
        }
        .gallery-item:hover img {
            transform: scale(1.2);
        }
        .caption {
            position: absolute;
            bottom: 0;
            background: rgba(0, 0, 0, 0.7);
            width: 100%;
            text-align: center;
            padding: 12px 0;
            font-size: 1.2rem;
            text-transform: capitalize;
            transition: all 0.4s ease-in-out;
        }
        .gallery-item:hover .caption {
            background: rgba(255, 107, 107, 0.8);
        }
        #lightbox {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.95);
            align-items: center;
            justify-content: center;
            z-index: 1000;
        }
        #lightbox img {
            max-width: 90%;
            max-height: 90%;
            border: 4px solid #f94c10;
            border-radius: 12px;
        }
        #lightbox span {
            position: absolute;
            top: 20px;
            right: 30px;
            font-size: 2rem;
            color: #fff;
            cursor: pointer;
            transition: color 0.3s;
        }
        #lightbox span:hover {
            color: #f94c10;
        }
        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <h1>Celebrity Photo Gallery</h1>
    <div class="gallery" id="gallery">
        <!-- Celebrity Images -->
        <div class="gallery-item">
            <img src="jr.jpg" alt="Chris Hemsworth">
            <div class="caption">Jayam Ravi</div>
        </div>
        <div class="gallery-item">
            <img src="str.jpg" alt="Ryan Reynolds">
            <div class="caption">Simbu</div>
        </div>
        <div class="gallery-item">
            <img src="vijay.jpg" alt="Tom Holland">
            <div class="caption">Thalapathy Vijay</div>
        </div>
        <div class="gallery-item">
            <img src="sk.jpg" alt="Brad Pitt">
            <div class="caption">Siva Karthikayen</div>
        </div>
        <div class="gallery-item">
            <img src="ajith.jpg" alt="Robert Downey Jr.">
            <div class="caption">Thala Ajith</div>
        </div>
    </div>
    <div id="lightbox">
        <span id="closeLightbox">&times;</span>
        <img src="" alt="Large Image" id="lightboxImg">
    </div>

    <script>
        const galleryItems = document.querySelectorAll('.gallery-item img');
        const lightbox = document.getElementById('lightbox');
        const lightboxImg = document.getElementById('lightboxImg');
        const closeLightbox = document.getElementById('closeLightbox');
        let currentIndex = 0;

        function openLightbox(index) {
            currentIndex = index;
            lightboxImg.src = galleryItems[index].src.replace('300x400', '600x800');
            lightbox.style.display = 'flex';
        }

        function close() {
            lightbox.style.display = 'none';
        }

        function showNext() {
            currentIndex = (currentIndex + 1) % galleryItems.length;
            openLightbox(currentIndex);
        }

        function showPrevious() {
            currentIndex = (currentIndex - 1 + galleryItems.length) % galleryItems.length;
            openLightbox(currentIndex);
        }

        galleryItems.forEach((img, index) => {
            img.addEventListener('click', () => openLightbox(index));
        });

        closeLightbox.addEventListener('click', close);

        document.addEventListener('keydown', (e) => {
            if (lightbox.style.display === 'flex') {
                if (e.key === 'Escape') close();
                if (e.key === 'ArrowRight') showNext();
                if (e.key === 'ArrowLeft') showPrevious();
            }
        });

        lightbox.addEventListener('click', (e) => {
            if (e.target === lightbox) close();
        });
    </script>
</body>
</html>


```

## OUTPUT:
![Screenshot (20)](https://github.com/user-attachments/assets/65ae8a6a-a421-4369-866c-0f7353a703ab)

## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
