<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>আমার ওয়েবসাইট</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 0; padding: 0; background-color: #f4f4f4; }
        header { background: #333; color: #fff; padding: 1rem 0; text-align: center; }
        main { padding: 2rem; max-width: 1200px; margin: auto; }
        .form-container { background: #fff; padding: 1.5rem; border-radius: 8px; margin-bottom: 2rem; box-shadow: 0 2px 5px rgba(0,0,0,0.1); }
        .form-container input { width: 100%; padding: 10px; margin: 10px 0; border: 1px solid #ddd; border-radius: 4px; box-sizing: border-box; }
        .form-container button { padding: 10px 15px; background: #28a745; color: #fff; border: none; border-radius: 4px; cursor: pointer; }
        .product-container { display: flex; flex-wrap: wrap; gap: 20px; justify-content: center; }
        .product-card { background: #fff; border: 1px solid #ddd; border-radius: 8px; padding: 1rem; width: 250px; text-align: center; box-shadow: 0 2px 5px rgba(0,0,0,0.1); position: relative; }
        .product-card img { max-width: 100%; height: auto; border-radius: 4px; }
        .product-card h3 { margin: 10px 0; color: #333; }
        .product-card .price { font-weight: bold; color: #e91e63; margin-bottom: 10px; }
        .delete-btn { padding: 5px 10px; background: #dc3545; color: #fff; border: none; border-radius: 4px; cursor: pointer; position: absolute; top: 10px; right: 10px; }
    </style>
</head>
<body>
    <header>
        <h1>Ador-মা ওয়েবসাইটে আপনাকে স্বাগতম</h1>
        <p>এটি আমার প্রথম ওয়েবসাইট</p>
    </header>
    <main>
        <div class="form-container">
            <h2>নতুন প্রোডাক্ট যোগ করুন</h2>
            <input type="text" id="product-name" placeholder="প্রোডাক্টের নাম">
            <input type="text" id="product-price" placeholder="প্রোডাক্টের দাম">
            <input type="text" id="product-img" placeholder="ছবির লিংক (URL)">
            <button onclick="addProduct()">প্রোডাক্ট যোগ করুন</button>
        </div>
        <div class="product-container" id="product-container">
            <!-- প্রোডাক্টগুলো এখানে প্রদর্শিত হবে -->
        </div>
    </main>
    <script>
        function addProduct() {
            const name = document.getElementById('product-name').value;
            const price = document.getElementById('product-price').value;
            const img = document.getElementById('product-img').value;
            if (name === '' || price === '' || img === '') {
                alert('অনুগ্রহ করে সবগুলো ঘর পূরণ করুন');
                return;
            }
            const container = document.getElementById('product-container');
            const card = document.createElement('div');
            card.className = 'product-card';
            card.innerHTML = `
                <button class="delete-btn" onclick="this.parentElement.remove()">ডিলিট</button>
                <img src="${img}" alt="${name}">
                <h3>${name}</h3>
                <div class="price">${price} টাকা</div>
            `;
            container.appendChild(card);
            document.getElementById('product-name').value = '';
            document.getElementById('product-price').value = '';
            document.getElementById('product-img').value = '';
        }
    </script>
</body>
</html>
