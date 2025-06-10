from zipfile import ZipFile
import os

project_files = {
    "index.html": """<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Shobhana | Where East Meets West</title>
  <link rel="stylesheet" href="styles.css" />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display&family=Quicksand&display=swap" rel="stylesheet">
  <link href="https://cdn.jsdelivr.net/npm/aos@2.3.4/dist/aos.css" rel="stylesheet">
</head>
<body>
  <header>
    <div class="logo">Shobhana</div>
    <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Shop</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>
  </header>

  <section class="hero" data-aos="fade-in">
    <div class="hero-text">
      <h1>Shobhana</h1>
      <p>Where East Meets West with a Glare of Elegance</p>
      <a href="#" class="cta-button">Explore the Collection</a>
    </div>
  </section>

  <section class="vertical-gallery" data-aos="fade-up">
    <h2>Signature Looks</h2>
    <div class="gallery-column">
      <div class="gallery-card" data-aos="fade-up" data-aos-delay="100">
        <img src="https://via.placeholder.com/400x600" alt="Look 1">
        <p>Men’s Royal Urban Fusion</p>
      </div>
      <div class="gallery-card" data-aos="fade-up" data-aos-delay="200">
        <img src="https://via.placeholder.com/400x600" alt="Look 2">
        <p>Women's Ethno-Contemporary Grace</p>
      </div>
      <div class="gallery-card" data-aos="fade-up" data-aos-delay="300">
        <img src="https://via.placeholder.com/400x600" alt="Look 3">
        <p>Vintage Kurta Revival</p>
      </div>
    </div>
  </section>

  <section class="about-us" data-aos="fade-up">
    <div class="about-content">
      <h2>About Shobhana</h2>
      <p><strong>Shobhana</strong> is a Sanskrit term meaning <em>“beautiful”</em> or <em>“attractive”</em>. It describes not just surface beauty, but elegance of form, grace in motion, and the refined allure of presence.</p>
      <p>Born at the intersection of tradition and innovation, <strong>Shobhana</strong> is a clothing brand where East meets West — blending timeless Indian textiles and silhouettes with contemporary Western cuts and styling. Our creations carry the warmth of heritage, the freshness of modern fashion, and an unmistakable aesthetic of elegance.</p>
      <p>We invite you to explore a wardrobe that honors roots while embracing the new — designed to be worn, remembered, and loved.</p>
    </div>
  </section>

  <footer>
    <p>© 2025 Shobhana. All rights reserved.</p>
  </footer>

  <script src="https://cdn.jsdelivr.net/npm/aos@2.3.4/dist/aos.js"></script>
  <script>
    AOS.init({ duration: 1000, once: true });
  </script>
</body>
</html>
""",
    "styles.css": """/* Your full styles.css content goes here (same as shared earlier) */"""
}

# Create ZIP
with ZipFile("shobhana-website.zip", 'w') as zipf:
    for filename, content in project_files.items():
        with open(filename, 'w', encoding='utf-8') as f:
            f.write(content)
        zipf.write(filename)
        os.remove(filename)

print("ZIP file created: shobhana-website.zip")
