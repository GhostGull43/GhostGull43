<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Studio Lumina Focus Tree</title>
<style>
    body {
        margin: 0;
        font-family: 'Segoe UI', sans-serif;
        background-color: #1b1b1b;
        color: #f0e6d2;
    }
    header {
        text-align: center;
        padding: 20px;
        font-size: 2em;
        background: #2a2a2a;
        border-bottom: 2px solid gold;
    }
    main {
        display: flex;
        justify-content: space-between;
        padding: 20px;
    }
    .focus-tree {
        display: grid;
        grid-template-columns: repeat(5, 1fr);
        gap: 30px;
        flex: 3;
    }
    .focus-node {
        background: #333;
        border: 2px solid gold;
        border-radius: 10px;
        text-align: center;
        padding: 15px;
        cursor: pointer;
        transition: transform 0.2s;
    }
    .focus-node:hover {
        transform: scale(1.05);
        background: #444;
    }
    .focus-node img {
        width: 50px;
        height: 50px;
    }
    aside {
        flex: 1;
        padding: 20px;
        background: #242424;
        border-left: 2px solid gold;
    }
    .modal {
        display: none;
        position: fixed;
        top: 0; left: 0;
        width: 100%; height: 100%;
        background: rgba(0, 0, 0, 0.8);
        justify-content: center;
        align-items: center;
        z-index: 1000;
    }
    .modal-content {
        background: #2c2c2c;
        padding: 20px;
        border: 2px solid gold;
        border-radius: 10px;
        width: 300px;
        color: #fff;
    }
    .close-btn {
        float: right;
        cursor: pointer;
        font-weight: bold;
        color: red;
    }
    footer {
        text-align: center;
        padding: 10px;
        background: #2a2a2a;
        border-top: 2px solid gold;
    }
    button.join-btn {
        background: gold;
        color: #000;
        padding: 10px 20px;
        border: none;
        font-size: 1.1em;
        border-radius: 5px;
        cursor: pointer;
    }
    button.join-btn:hover {
        background: #ffcc00;
    }
</style>
</head>
<body>
<header>Studio Lumina – National Focus Tree</header>
<main>
    <section class="focus-tree" id="focusTree">
        <!-- Focus Nodes: Economy, Infrastructure, Military, Diplomacy, Culture -->
        <div class="focus-node" data-title="First Settlement" data-req="Start of Nation" data-reward="Claim 500x500 Land">
            <img src="https://minecraft.wiki/images/Oak_Planks.png" alt="First Settlement">
            <p>First Settlement</p>
        </div>
        <div class="focus-node" data-title="Agriculture" data-req="First Settlement" data-reward="Unlock Villager Trading, Food Surplus">
            <img src="https://minecraft.wiki/images/Wheat_JE2_BE2.png" alt="Agriculture">
            <p>Agriculture</p>
        </div>
        <div class="focus-node" data-title="Mining Boom" data-req="Agriculture" data-reward="Access Advanced Trade Deals">
            <img src="https://minecraft.wiki/images/Iron_Pickaxe_JE2_BE2.png" alt="Mining">
            <p>Mining Boom</p>
        </div>
        <div class="focus-node" data-title="Trade Dominance" data-req="Mining Boom" data-reward="Set Up Marketplace">
            <img src="https://minecraft.wiki/images/Emerald_JE2_BE2.png" alt="Trade">
            <p>Trade Dominance</p>
        </div>
        <div class="focus-node" data-title="Industrialization" data-req="Trade Dominance" data-reward="Unlock Automated Farms">
            <img src="https://minecraft.wiki/images/Furnace_JE3_BE2.png" alt="Industry">
            <p>Industrialization</p>
        </div>

        <div class="focus-node" data-title="Road Network" data-req="First Settlement" data-reward="Faster Travel Between Cities">
            <img src="https://minecraft.wiki/images/Cobblestone_JE2_BE2.png" alt="Roads">
            <p>Road Network</p>
        </div>
        <div class="focus-node" data-title="Capital City" data-req="Road Network" data-reward="Boost Cultural Prestige">
            <img src="https://minecraft.wiki/images/Stone_Brick_JE3_BE2.png" alt="Capital">
            <p>Capital City</p>
        </div>
        <div class="focus-node" data-title="Transport Hub" data-req="Capital City" data-reward="Rail/Boat Routes Unlocked">
            <img src="https://minecraft.wiki/images/Minecart_JE2_BE2.png" alt="Transport">
            <p>Transport Hub</p>
        </div>
        <div class="focus-node" data-title="Mega Projects" data-req="Transport Hub" data-reward="Access to Nation Projects">
            <img src="https://minecraft.wiki/images/Beacon_JE3_BE2.png" alt="Mega Projects">
            <p>Mega Projects</p>
        </div>

        <div class="focus-node" data-title="Militia Organization" data-req="First Settlement" data-reward="Recruit Army (50 troops)">
            <img src="https://minecraft.wiki/images/Iron_Sword_JE2_BE2.png" alt="Militia">
            <p>Militia Organization</p>
        </div>
        <div class="focus-node" data-title="Fortification Plans" data-req="Militia Organization" data-reward="+Defensive Buff">
            <img src="https://minecraft.wiki/images/Cobblestone_Wall_JE3_BE2.png" alt="Fortifications">
            <p>Fortification Plans</p>
        </div>
        <div class="focus-node" data-title="Professional Army" data-req="Fortification Plans" data-reward="Diamond Gear Access">
            <img src="https://minecraft.wiki/images/Diamond_Chestplate_JE3_BE2.png" alt="Army">
            <p>Professional Army</p>
        </div>
        <div class="focus-node" data-title="Siege Warfare" data-req="Professional Army" data-reward="Unlock TNT Cannons">
            <img src="https://minecraft.wiki/images/TNT_JE2_BE2.png" alt="Siege">
            <p>Siege Warfare</p>
        </div>

        <div class="focus-node" data-title="First Treaty" data-req="First Settlement" data-reward="Non-Aggression Pact">
            <img src="https://minecraft.wiki/images/Book_JE2_BE2.png" alt="Treaty">
            <p>First Treaty</p>
        </div>
        <div class="focus-node" data-title="Alliance Pact" data-req="First Treaty" data-reward="Defensive Pact">
            <img src="https://minecraft.wiki/images/Shield_JE2_BE2.png" alt="Alliance">
            <p>Alliance Pact</p>
        </div>
        <div class="focus-node" data-title="Join a League" data-req="Alliance Pact" data-reward="Shared Defense Network">
            <img src="https://minecraft.wiki/images/Banner_JE2_BE2.png" alt="League">
            <p>Join a League</p>
        </div>

        <div class="focus-node" data-title="National Banner" data-req="First Settlement" data-reward="Cultural Prestige">
            <img src="https://minecraft.wiki/images/White_Banner_JE2_BE2.png" alt="Banner">
            <p>National Banner</p>
        </div>
        <div class="focus-node" data-title="Great Monument" data-req="National Banner" data-reward="Diplomacy Bonus">
            <img src="https://minecraft.wiki/images/Quartz_Block_JE2_BE2.png" alt="Monument">
            <p>Great Monument</p>
        </div>
        <div class="focus-node" data-title="Festivals" data-req="Great Monument" data-reward="+Happiness, Trade Boost">
            <img src="https://minecraft.wiki/images/Cake_JE2_BE2.png" alt="Festival">
            <p>Festivals</p>
        </div>
    </section>

    <aside>
        <h2>Civilization Levels</h2>
        <p><strong>Village:</strong> 1–5 Builds | 50 Troops | Claim Size: 500x500</p>
        <p><strong>Town:</strong> 6–10 Builds | 100 Troops | Unlock Trade Routes</p>
        <p><strong>Kingdom:</strong> 10+ Builds | 150 Troops | Access Mega-Projects</p>
    </aside>
</main>
<footer>
    <button class="join-btn">Join Our Server</button>
</footer>

<div class="modal" id="focusModal">
    <div class="modal-content">
        <span class="close-btn" id="closeModal">×</span>
        <h2 id="modalTitle"></h2>
        <p><strong>Requirement:</strong> <span id="modalReq"></span></p>
        <p><strong>Reward:</strong> <span id="modalReward"></span></p>
    </div>
</div>

<script>
    const modal = document.getElementById('focusModal');
    const closeModal = document.getElementById('closeModal');
    const modalTitle = document.getElementById('modalTitle');
    const modalReq = document.getElementById('modalReq');
    const modalReward = document.getElementById('modalReward');

    document.querySelectorAll('.focus-node').forEach(node => {
        node.addEventListener('click', () => {
            modalTitle.textContent = node.dataset.title;
            modalReq.textContent = node.dataset.req;
            modalReward.textContent = node.dataset.reward;
            modal.style.display = 'flex';
        });
    });

    closeModal.addEventListener('click', () => {
        modal.style.display = 'none';
    });

    window.addEventListener('click', (e) => {
        if (e.target === modal) modal.style.display = 'none';
    });
</script>
</body>
</html>
