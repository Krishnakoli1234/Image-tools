# Image-tools
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Compress your images online with our fully responsive image compression tool. Optimize images for web use with adjustable compression levels.">
    <meta name="keywords" content="image compression, optimize images, image optimizer, online image compressor">
    <meta name="Krishna" content="Your Name">
    <title>Image Compression Tool - Optimize Your Images Online</title>
    <style>
        /* Global Styles */
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f7f6;
            color: #333;
            line-height: 1.6;
        }

        header {
            background: linear-gradient(135deg, #007BFF, #00a8ff);
            color: #fff;
            padding: 60px 20px;
            text-align: center;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }

        header h1 {
            margin: 0;
            font-size: 2.5rem;
            font-weight: 600;
        }

        header p {
            margin: 10px 0 0;
            font-size: 1.1rem;
            opacity: 0.9;
        }

        main {
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
        }

        /* Compression Tool Section */
        #compression-tool {
            background-color: #fff;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        #compression-tool input[type="file"] {
            display: none;
        }

        #compression-tool label[for="image-input"] {
            display: inline-block;
            background: linear-gradient(135deg, #007BFF, #00a8ff);
            color: #fff;
            padding: 12px 30px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1rem;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            box-shadow: 0 4px 10px rgba(0, 123, 255, 0.3);
        }

        #compression-tool label[for="image-input"]:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 15px rgba(0, 123, 255, 0.4);
        }

        #compression-level {
            width: 80%;
            margin: 25px 0;
            cursor: pointer;
            accent-color: #007BFF;
        }

        #compress-btn {
            background: linear-gradient(135deg, #28a745, #2ecc71);
            color: #fff;
            border: none;
            padding: 12px 30px;
            border-radius: 50px;
            font-size: 1rem;
            cursor: pointer;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            box-shadow: 0 4px 10px rgba(40, 167, 69, 0.3);
        }

        #compress-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 15px rgba(40, 167, 69, 0.4);
        }

        /* Output Section */
        #output-container {
            margin-top: 25px;
            display: none;
            text-align: center;
        }

        #output-image {
            max-width: 100%;
            height: auto;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
        }

        #download-link {
            display: inline-block;
            margin-top: 20px;
            background: linear-gradient(135deg, #007BFF, #00a8ff);
            color: #fff;
            padding: 10px 25px;
            border-radius: 50px;
            text-decoration: none;
            font-size: 1rem;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            box-shadow: 0 4px 10px rgba(0, 123, 255, 0.3);
        }

        #download-link:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 15px rgba(0, 123, 255, 0.4);
        }

        /* Ad Space */
        #ad-space {
            margin-top: 30px;
            text-align: center;
        }

        /* Footer */
        footer {
            background-color: #333;
            color: #fff;
            text-align: center;
            padding: 15px;
            margin-top: 30px;
            font-size: 0.9rem;
        }

        /* Responsive Design */
        @media (max-width: 600px) {
            header h1 {
                font-size: 2rem;
            }

            header p {
                font-size: 1rem;
            }

            #compression-tool {
                padding: 20px;
            }

            #compression-level {
                width: 90%;
            }

            #compress-btn, #compression-tool label[for="image-input"], #download-link {
                width: 100%;
                padding: 12px 20px;
            }
        }
    </style>
    <!-- Google AdSense -->
    <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-YOUR_AD_UNIT_ID" crossorigin="anonymous"></script>
</head>
<body>
    <header>
        <h1>Image Compression Tool</h1>
        <p>Optimize your images for web use with adjustable compression levels.</p>
    </header>

    <main>
        <section id="compression-tool">
            <label for="image-input">Choose Image</label>
            <input type="file" id="image-input" accept="image/*">
            <label for="compression-level">Compression Level: <span id="compression-value">0.5</span></label>
            <input type="range" id="compression-level" min="0" max="1" step="0.1" value="0.5">
            <button id="compress-btn">Compress Image</button>
            <div id="output-container">
                <img id="output-image" src="" alt="Compressed Image">
                <a id="download-link" href="" download>Download Compressed Image</a>
            </div>
        </section>

        <!-- Ad Space -->
        <section id="ad-space">
            <!-- Google AdSense Ad Unit -->
            <ins class="adsbygoogle"
                 style="display:block"
                 data-ad-client="ca-pub-YOUR_AD_UNIT_ID"
                 data-ad-slot="YOUR_AD_SLOT_ID"
                 data-ad-format="auto"
                 data-full-width-responsive="true"></ins>
            <script>
                 (adsbygoogle = window.adsbygoogle || []).push({});
            </script>
        </section>
    </main>

    <footer>
        <p>&copy; 2023 Image Compression Tool. All rights reserved.</p>
    </footer>

    <script>
        // JavaScript Functionality
        document.getElementById('compress-btn').addEventListener('click', function() {
            const fileInput = document.getElementById('image-input');
            const compressionLevel = parseFloat(document.getElementById('compression-level').value);
            const outputImage = document.getElementById('output-image');
            const downloadLink = document.getElementById('download-link');
            const outputContainer = document.getElementById('output-container');

            if (fileInput.files.length === 0) {
                alert('Please select an image to compress.');
                return;
            }

            const file = fileInput.files[0];
            const reader = new FileReader();

            reader.onload = function(e) {
                const img = new Image();
                img.src = e.target.result;

                img.onload = function() {
                    const canvas = document.createElement('canvas');
                    const ctx = canvas.getContext('2d');

                    // Set canvas dimensions
                    canvas.width = img.width;
                    canvas.height = img.height;

                    // Draw the image on the canvas
                    ctx.drawImage(img, 0, 0, canvas.width, canvas.height);

                    // Compress the image
                    canvas.toBlob(function(blob) {
                        const compressedImageUrl = URL.createObjectURL(blob);
                        outputImage.src = compressedImageUrl;
                        downloadLink.href = compressedImageUrl;
                        outputContainer.style.display = 'block';
                    }, 'image/jpeg', compressionLevel);
                };
            };

            reader.readAsDataURL(file);
        });

        // Update compression level value
        document.getElementById('compression-level').addEventListener('input', function() {
            document.getElementById('compression-value').textContent = this.value;
        });
    </script>
</body>
</html>
