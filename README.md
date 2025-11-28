# experiment_4


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Image Gallery</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <h1>Interactive Image Gallery</h1>

    <!-- Main Image Display -->
    <div class="main-image-container">
        <img id="mainImage" src="images/image1.jpg" alt="Main Display Image">
    </div>

    <!-- Thumbnail Gallery -->
    <div class="thumbnail-container">
        <img class="thumbnail" src="images/image1_thumb.jpg" data-full="images/image1.jpg" alt="Thumbnail 1">
        <img class="thumbnail" src="images/image2_thumb.jpg" data-full="images/image2.jpg" alt="Thumbnail 2">
        <img class="thumbnail" src="images/image3_thumb.jpg" data-full="images/image3.jpg" alt="Thumbnail 3">
        <img class="thumbnail" src="images/image4_thumb.jpg" data-full="images/image4.jpg" alt="Thumbnail 4">
    </div>

    <script src="script.js"></script>
</body>
</html>


#style.css
body {
    font-family: Arial, sans-serif;
    text-align: center;
    background-color: #f7f7f7;
    margin: 0;
    padding: 20px;
}

h1 {
    color: #333;
}

.main-image-container {
    width: 80%;
    margin: 20px auto;
}

#mainImage {
    width: 100%;
    max-width: 600px;
    border-radius: 10px;
    border: 3px solid #ccc;
}

.thumbnail-container {
    margin-top: 20px;
    display: flex;
    justify-content: center;
    gap: 15px;
    flex-wrap: wrap;
}

.thumbnail {
    width: 120px;
    height: 80px;
    object-fit: cover;
    border-radius: 8px;
    cursor: pointer;
    transition: transform 0.2s, border 0.2s;
}

.thumbnail:hover {
    transform: scale(1.1);
    border: 2px solid #555;
}


#script.js
// Select the main image element
const mainImage = document.getElementById("mainImage");

// Select all thumbnails
const thumbnails = document.querySelectorAll(".thumbnail");

// Add click event to each thumbnail
thumbnails.forEach(thumb => {
    thumb.addEventListener("click", () => {
        // Get the full-size image from the data attribute
        const fullImage = thumb.getAttribute("data-full");
        
        // Set the main image source to the clicked thumbnail's full image
        mainImage.src = fullImage;
    });
});

