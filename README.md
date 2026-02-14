<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>INVERSE SA</title>
<style>
    body { font-family: Arial; margin:0; padding:0; text-align:center; background:#fff; color:#000;}
    header { padding:20px; box-shadow:0 2px 5px rgba(0,0,0,0.1);}
    header h1 { font-size:2.5rem; text-shadow:2px 2px #888;}
    .logo { width:300px; max-width:60%; margin:20px auto;}
    .about { font-size:1.1rem; margin:20px; line-height:1.5;}
    .gallery { display:flex; flex-wrap:wrap; justify-content:center; gap:15px; padding:20px;}
    .gallery img { width:200px; height:200px; object-fit:cover; border:2px solid #000; border-radius:5px; cursor:pointer; transition: transform 0.2s;}
    .gallery img:hover { transform: scale(1.05);}
    .buttons { display:flex; justify-content:center; flex-wrap:wrap; gap:15px; margin:20px;}
    .btn { padding:12px 25px; font-size:1rem; border:none; border-radius:5px; cursor:pointer; color:#fff; transition: transform 0.2s;}
    .btn:hover { transform: scale(1.05);}
    .store-btn { background:#000; }
    .tiktok-btn { background:#000; }
    .instagram-btn { background:#000; }
    .whatsapp-btn { background:#25D366; }
    footer { font-size:0.9rem; color:#888; margin:30px 0; }

    /* Modal */
    .modal { display:none; position:fixed; z-index:100; left:0; top:0; width:100%; height:100%; background:rgba(0,0,0,0.8); padding-top:100px;}
    .modal-content { background:#fff; margin:auto; padding:20px; width:90%; max-width:400px; border-radius:10px; position:relative; text-align:center;}
    .modal img { width:80%; margin-bottom:15px; }
    .close { color:#aaa; position:absolute; top:10px; right:20px; font-size:28px; font-weight:bold; cursor:pointer;}
    .close:hover { color:#000; }
    .buy-btn { background:#000; color:#fff; padding:10px 20px; font-size:1rem; border:none; border-radius:5px; cursor:pointer; margin-top:10px;}
    .buy-btn:hover { transform: scale(1.05); }
</style>
</head>
<body>

<header>
    <h1>INVERSE SA</h1>
</header>

<img class="logo" src="https://inversesa.com/logo.png" alt="INVERSE SA Logo">

<div class="about">
    Go Wild, Go INVERSE<br>
    Urban Streetwear | Black & White | Exclusive Collection
</div>

<div class="gallery" id="gallery"></div>

<div class="buttons">
    <button class="btn store-btn" onclick="window.open('https://msha.ke/inversesa','_blank')">Visit Store</button>
    <button class="btn tiktok-btn" onclick="window.open('https://www.tiktok.com/@inversesa','_blank')">TikTok</button>
    <button class="btn instagram-btn" onclick="window.open('https://www.instagram.com/sainverse','_blank')">Instagram</button>
    <button class="btn whatsapp-btn" onclick="window.open('https://wa.me/27712668330','_blank')">Chat on WhatsApp</button>
</div>

<footer>
    © 2026 INVERSE SA | All Rights Reserved
</footer>

<!-- Modal -->
<div id="productModal" class="modal">
    <div class="modal-content">
        <span class="close" onclick="closeModal()">&times;</span>
        <img id="modalImage" src="" alt="Product">
        <h2 id="modalTitle">Product Name</h2>
        <p id="modalPrice">$0.00</p>
        <p id="modalDesc">Description</p>
        <button class="buy-btn" id="modalBuyBtn" onclick="">Buy Now</button>
    </div>
</div>

<script>
    const products = [
        {name:"Urban Hoodie", price:"$299", desc:"Black & white hoodie with streetwear vibes.", img:"https://inversesa.com/images/item1.png", link:"https://msha.ke/inversesa"},
        {name:"Street Tee", price:"$149", desc:"Casual black t-shirt with INVERSE logo.", img:"https://inversesa.com/images/item2.png", link:"https://msha.ke/inversesa"},
        {name:"Graphic Cap", price:"$99", desc:"Black cap with bold street graphics.", img:"https://inversesa.com/images/item3.png", link:"https://msha.ke/inversesa"},
        {name:"Sneaker Socks", price:"$49", desc:"Comfortable socks for your urban style.", img:"https://inversesa.com/images/item4.png", link:"https://msha.ke/inversesa"}
    ];

    const galleryDiv = document.getElementById("gallery");
    products.forEach((product,index)=>{
        const img = document.createElement("img");
        img.src = product.img;
        img.alt = product.name;
        img.onclick = ()=> openModal(index);
        galleryDiv.appendChild(img);
    });

    const modal = document.getElementById("productModal");
    const modalImage = document.getElementById("modalImage");
    const modalTitle = document.getElementById("modalTitle");
    const modalPrice = document.getElementById("modalPrice");
    const modalDesc = document.getElementById("modalDesc");
    const modalBuyBtn = document.getElementById("modalBuyBtn");

    function openModal(index){
        const p = products[index];
        modalImage.src = p.img;
        modalTitle.innerText = p.name;
        modalPrice.innerText = p.price;
        modalDesc.innerText = p.desc;
        modalBuyBtn.onclick = ()=> window.open(p.link,'_blank');
        modal.style.display = "block";
    }

    function closeModal(){ modal.style.display="none"; }

    window.onclick = function(e){ if(e.target==modal) modal.style.display="none"; }
</script>

</body>
</html>
