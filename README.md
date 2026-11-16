vhtml
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Vault | Urban Luxury Fun Zone</title>
    <style>
        :root {
            --bg-black: #050505;
            --neon-blue: #00f0ff;
            --neon-pink: #ff007f;
            --neon-purple: #9400d3;
            --gold-bling: #ffd700;
            --text-green: #b3b3b3;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Impact', 'Arial Black', 'Chancery';
        }

        body {
            background-color: var(--bg-black);
            color: #ffffff;
            overflow-x: hidden;
            background-image: radial-gradient(var(--neon-purple) 0.5px, transparent 0.5px), radial-gradient(var(--neon-blue) 0.5px, var(--bg-black) 0.5px);
            background-size: 40px 40px;
            background-position: 0 0, 20px 20px;
        }

        .neon-text-blue {
            text-shadow: 0 0 5px #00f0ff, 0 0 15px #00f0ff, 0 0 30px #00f0ff;
            color: var(--neon-blue);
        }

        .neon-text-pink {
            text-shadow: 0 0 5px #ff007f, 0 0 15px #ff007f, 0 0 30px #ff007f;
            color: var(--neon-pink);
        }

        .bling-text {
            color: var(--gold-bling);
            text-shadow: 2px 2px 0px #000, -1px -1px 0px #000, 1px -1px 0px #000, -1px 1px 0px #000;
            letter-spacing: 2px;
        }

        .floating-bolt {
            position: fixed;
            width: 60px;
            height: 60px;
            z-index: 100;
            pointer-events: none;
            animation: floatAround 12s infinite linear;
            opacity: 0.8;
        }

        @keyframes floatAround {
            0% { top: 10%; left: 5%; transform: rotate(0deg); }
            25% { top: 40%; left: 85%; transform: rotate(90deg); }
            50% { top: 85%; left: 50%; transform: rotate(180deg); }
            75% { top: 50%; left: 10%; transform: rotate(270deg); }
            100% { top: 10%; left: 5%; transform: rotate(360deg); }
        }

        header {
            background: rgba(5, 5, 5, 0.9);
            border-bottom: 3px solid var(--neon-pink);
            padding: 15px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .logo {
            font-size: 2.5rem;
            text-transform: uppercase;
            font-style: italic;
        }

        .nav-links a {
            color: #fff;
            text-decoration: none;
            margin-left: 20px;
            font-size: 1.2rem;
            transition: 0.3s;
        }

        .nav-links a:hover {
            color: var(--neon-blue);
        }

        .hero {
            padding: 60px 20px;
            text-align: center;
            position: relative;
        }

        .hero h1 {
            font-size: 5rem;
            margin-bottom: 10px;
            text-transform: uppercase;
        }

        .hero p {
            font-size: 1.5rem;
            color: var(--text-gray);
            margin-bottom: 30px;
        }

        .music-zone {
            background: linear-gradient(135deg, rgba(20,20,20,0.9), rgba(5,5,5,0.9));
            border: 3px solid var(--neon-blue);
            box-shadow: 0 0 20px var(--neon-blue);
            max-width: 600px;
            margin: 0 auto 50px auto;
            border-radius: 15px;
            padding: 25px;
        }

        .player-controls {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 20px;
            margin-top: 15px;
        }

        .player-btn {
            background: transparent;
            border: 2px solid var(--gold-bling);
            color: var(--gold-bling);
            padding: 10px 20px;
            font-size: 1.2rem;
            cursor: pointer;
            border-radius: 5px;
            transition: 0.3s;
        }

        .player-btn:hover {
            background: var(--gold-bling);
            color: #000;
            box-shadow: 0 0 10px var(--gold-bling);
        }

        .upload-box {
            margin-top: 15px;
            border: 2px dashed var(--text-gray);
            padding: 15px;
            cursor: pointer;
        }

        .store-section {
            padding: 40px 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            font-size: 3rem;
            text-align: center;
            margin-bottom: 40px;
            text-transform: uppercase;
        }

        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        .product-card {
            background: #111;
            border: 2px solid var(--neon-purple);
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            position: relative;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 0 20px var(--neon-purple);
        }

        .product-image-placeholder {
            width: 100%;
            height: 250px;
            background: #222;
            border-radius: 5px;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-bottom: 3px solid var(--neon-pink);
        }

        .price-tag {
            font-size: 1.5rem;
            margin: 10px 0;
        }

        .buy-btn {
            background: var(--neon-pink);
            color: white;
            border: none;
            padding: 12px 25px;
            font-size: 1.1rem;
            cursor: pointer;
            text-transform: uppercase;
            width: 100%;
            border-radius: 5px;
        }

        .quiz-zone {
            background: #0a0a0a;
            border: 3px solid var(--gold-bling);
            max-width: 700px;
            margin: 50px auto;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 0 25px rgba(255, 215, 0, 0.3);
        }

        .quiz-option {
            background: #1a1a1a;
            border: 2px solid var(--neon-blue);
            padding: 15px;
            margin: 10px 0;
            border-radius: 5px;
            cursor: pointer;
            transition: 0.2s;
            text-align: left;
        }

        .quiz-option:hover {
            background: var(--neon-blue);
            color: #000;
        }

        .rewards-dashboard {
            background: #111;
            border: 2px solid var(--neon-pink);
            max-width: 400px;
            margin: 40px auto;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
        }

        .points-display {
            font-size: 3.5rem;
            color: var(--neon-blue);
            margin: 10px 0;
        }

        .submission-portal {
            background: linear-gradient(180deg, #0a0a0a, #111);
            border: 3px dashed var(--neon-pink);
            box-shadow: 0 0 15px rgba(255, 0, 127, 0.2);
            max-width: 800px;
            margin: 40px auto;
            padding: 30px;
            border-radius: 15px;
            text-align: center;
        }

        .drop-zone {
            background: #050505;
            border: 2px dashed var(--neon-blue);
            border-radius: 10px;
            padding: 40px 20px;
            margin: 20px 0;
            cursor: pointer;
            transition: 0.3s;
        }

        .drop-zone:hover {
            background: rgba(0, 240, 255, 0.05);
            box-shadow: 0 0 15px rgba(0, 240, 255, 0.2);
        }

        .form-input {
            background: #222;
            border: 2px solid var(--neon-purple);
            color: #fff;
            padding: 12px;
            width: 100%;
            margin-bottom: 15


px;
            border-radius: 5px;
            font-size: 1.1rem;
        }

        .leaderboard-container {
            background: #0d0d0d;
            border: 3px solid var(--gold-bling);
            max-width: 500px;
            margin: 40px auto;
            padding: 25px;
            border-radius: 12px;
            box-shadow: 0 0 20px rgba(255, 215, 0, 0.2);
        }

        .leaderboard-table {
            width: 100%;
            margin-top: 15px;
            border-collapse: collapse;
        }

        .leaderboard-row {
            border-bottom: 1px solid #222;
            transition: 0.2s;
        }

        .leaderboard-row:hover {
            background: rgba(255, 215, 0, 0.1);
        }

        .leaderboard-cell {
            padding: 12px;
            font-size: 1.2rem;
            text-align: left;
        }

        .rank-num {
            color: var(--neon-pink);
            font-weight: bold;
        }

        .arcade-zone-wrapper {
            background: #000000;
            padding: 50px 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .arcade-grid-nav {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 35px;
            flex-wrap: wrap;
        }

        .game-tab-btn {
            background: #111;
            border: 2px solid #222;
            color: #fff;
            padding: 12px 28px;
            font-size: 1.1rem;
            cursor: pointer;
            border-radius: 30px;
            transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .game-tab-btn.active-game {
            border-color: var(--neon-blue);
            box-shadow: 0 0 15px rgba(0, 240, 255, 0.4);
            background: #00f0ff;
Use code with caution.

color: #000;
font-weight: bold;
}
.game-canvas-container {
background: linear-gradient(145deg, #0b0b0f, #050507);
border: 2px solid #1a1a24;
border-radius: 20px;
min-height: 550px;
position: relative;
padding: 30px;
display: none;
box-shadow: 0 20px 40px rgba(0,0,0,0.6);
}
.game-canvas-container.active-view {
display: block;
}
.mahjong-board-layer {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 15px;
max-width: 600px;
margin: 0 auto;
padding: 20px;
}
.bling-tile-asset {
background: linear-gradient(135deg, #1e1e24, #121215);
border: 2px solid var(--gold-bling);
border-radius: 8px;
aspect-ratio: 3/4;
cursor: pointer;
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
position: relative;
transition: transform 0.2s, box-shadow 0.2s;
box-shadow: 0 6px 0 #b89200, 0 8px 15px rgba(0,0,0,0.5);
}
.bling-tile-asset:hover {
transform: translateY(-4px);
box-shadow: 0 10px 0 #b89200, 0 12px 20px rgba(0, 240, 255, 0.3);
}
.tile-icon-svg {
width: 40px;
height: 40px;
margin-bottom: 6px;
}
.rhythm-fall-arena {
width: 100%;
max-width: 500px;
height: 400px;
background: #020203;
border-radius: 12px;
margin: 0 auto;
position: relative;
overflow: hidden;
border: 1px solid #222;
}
.rhythm-target-bar {
position: absolute;
bottom: 40px;
width: 100%;
height: 60px;
border-top: 2px dashed rgba(255, 0, 127, 0.4);
border-bottom: 2px dashed rgba(255, 0, 127, 0.4);
background: rgba(255, 0, 127, 0.05);
}
.vault-matrix-grid {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 15px;
max-width: 400px;
margin: 30px auto;
}
.matrix-node-btn {
background: #111;
border: 2px solid var(--neon-purple);
padding: 25px;
font-size: 1.5rem;
color: #fff;
cursor: pointer;
border-radius: 10px;
transition: 0.2s;
}
.matrix-node-btn:hover {
background: var(--neon-purple);
box-shadow: 0 0 15px var(--neon-purple);
}




THE VAULT

SHOP
BEATS
ARCADE
CUSTOM LAB


URBAN LUXURY FUN ZONE
Custom All-Over Print Apparel • Authentic Hype Beats • Street Culture Miniature Games
🎧 VAULT SOUNDSTAGE LIVE
Current Track: Street Symphony Remix

PLAY
PAUSE


⚡ DRAG & DROP CUSTOM SOUNDTRACKS HERE ⚡



THE DROPS



Custom Letterman Mockup

VIP Varsity Custom Fleece Jacket
$120 / 1200 PTS
Add to Cart
Embroidered Vest Mockup

Street Elite Waistcoat Vest
$65 / 650 PTS
Add to Cart
Jersey Dress Mockup

Neon Cascade Ruffle Jersey Dress
$45 / 450 PTS
Add to Cart



THE VAULT STYLE QUIZ
Answer to unlock exclusive drip items and earn bonus points!
What type of custom aesthetic defines your personal look?
A) Blacklight Neon Psychedelic Graphics
B) High-Bling Metallic & Dripping Gold Motifs
C) Minimalist Sharp Industrial Luxury Layout lines
D) Bold Vibrant Festival Oversized Casual Coordinates

⚡ THE VAULT PLAY ZONE
Play custom drops to rack up exclusive loyalty point payouts.
🀄 BLING MAHJONG
🎵 DRIP DROP RHYTHM
🔓 DECRYPT MULTIPLIER
HIP-HOP BLING MAHJONG DROPS



BOLT



CROWN



DIAMOND



BOLT



CROWN



DIAMOND


DRIP DROP RHYTHM SPEEDTAP




THE CORE CODE DECRYPTOR

7
3
9




⚡ THE VAULT CUSTOM DESIGN LAB ⚡
Upload your own graphics and fonts to lock down mockups on our custom apparel layers.



DRAG & DROP GRAPHICS / FONTS HERE



SUBMIT DROPS TO REVIEW LAB
👑 THE VAULT LEADERBOARD

#1
DripKing_916
14,250 PTS
#2
NeonVibe_958
11,800 PTS
#3
You
0000 PTS
YOUR VAULT BALANCE
0000
10 Points earned per $1 Spent • Instant Sweepstakes Tokens
let currentPoints = 0;
function addPoints(amount) {
currentPoints += amount;
document.getElementById('points').innerText = String(currentPoints).padStart(4, '0');
document.getElementById('leaderboardUserPoints').innerText = String(currentPoints).padStart(4, '0') + " PTS";
}
function selectOption(pointsReward) {
alert('Preference Locked! Styling customization tags updated.');
addPoints(pointsReward);
}
function switchGameMode(targetId, btnRef) {
document.querySelectorAll('.game-canvas-container').forEach(view => view.classList.remove('active-view'));
document.querySelectorAll('.game-tab-btn').forEach(btn => btn.classList.remove('active-game'));
document.getElementById(targetId).classList.add('active-view');
btnRef.classList.add('active-game');
}
let activeSelectedTile = null;
function triggerTileMatch(tileElement, assetType) {
tileElement.style.borderColor = "var(--neon-blue)";
if (!activeSelectedTile) {
activeSelectedTile = { element: tileElement, type: assetType };
} else {
if (activeSelectedTile.type === assetType && activeSelectedTile.element !== tileElement) {
alert(🎯 MATCH LOCKED! Cleared ${assetType.toUpperCase()} layer. +250 Vault Points!);
tileElement.style.visibility = "hidden";
activeSelectedTile.element.style.visibility = "hidden";
addPoints(250);
} else {
tileElement.style.borderColor = "var(--gold-bling)";
activeSelectedTile.element.style.borderColor = "var(--gold-bling)";
}
activeSelectedTile = null;
}
}
function handleRhythmTap() {
alert("⚡ BEAT LOCKED IN! Perfect rhythm match timing. +150 Points!");
addPoints(150);
}
let decryptStep = 0;
function handleMatrixCrack(nodeNum) {
decryptStep++;
if(decryptStep >= 2) {
alert("🔓 VAULT MATRIX BYPASSED! 2X Reward Multiplier Activated!");
addPoints(500);
decryptStep = 0;
} else {
alert(🔒 Node ${nodeNum} configured. Sequence track advancing...);
}
}
function handleFileSelect(input) {
const file = input.files[0];
if (file) {
document.getElementById('fileUploadPreview').innerText = 📄 STAGED FILE: ${file.name.toUpperCase()};
}
}
function submitCustomDesign() {
const creator = document.getElementById('creatorName').value;
const design = document.getElementById('designTitle').value;
if (!creator || !design) {
alert('❌ REJECTED: Complete track configurations before dropping data.');
return;
}
alert(🚀 SUCCESS! ${design.toUpperCase()} submitted. +500 Vault Reward Points!);
addPoints(500);
}


<!-- AUTOMATED AUDIO STATION WITH SELECTABLE TRACKLIST MENU -->
<div class="music-bar-dock" style="display: block; max-width: 750px; margin: 30px auto; border-radius: 16px; padding: 25px;">
    <div class="audio-info" style="margin-bottom: 20px;">
        <svg class="cannabis-glow-icon" viewBox="0 0 24 24" fill="none" xmlns="http://w3.org">
            <path d="M12 2C12 2 13 7 15 9C17 11 22 12 22 12C22 12 17 13 15 15C13 17 12 22 12 22C12 22 11 17 9 15C7 13 2 12 2 12C2 12 7 11 9 9C11 7 12 2 12 2Z" fill="#00ff66"/>
        </svg>
        <div>
            <p style="font-size: 0.9rem; font-family: 'Syncopate', sans-serif; font-weight: 700; letter-spacing: 0.5px;" id="trackNameDisplay">STREAMING AUDIO: INITIALIZING...</p>
            <p style="font-size: 0.75rem; color: #666;" id="audioStatusText">Autoplay pending activation • Select a track below</p>
        </div>
    </div>
    
    <!-- Audio Direct Control Deck -->
    <div class="audio-controls" style="justify-content: center; gap: 20px; margin-bottom: 20px;">
        <button class="audio-btn" id="playPauseBtn" onclick="togglePlayPause()">▶</button>
        <button class="audio-btn" id="skipBtn" onclick="skipTrack()">Skip</button>
        <button class="audio-btn" id="muteBtn" onclick="toggleMute()">🔊</button>
    </div>

    <!-- Clickable Interactive Track List Menu Box -->
    <div style="background: rgba(0,0,0,0.4); border-radius: 8px; padding: 10px; border: 1px solid rgba(255,255,255,0.05);">
        <p style="font-size: 0.75rem; color: var(--cannabis-green); font-family: 'Syncopate', sans-serif; margin-bottom: 8px; letter-spacing: 1px;">SELECT DECK CUT:</p>
        <div style="display: flex; flex-direction: column; gap: 5px;">
            <div style="padding: 10px; background: rgba(255,255,255,0.02); border-radius: 4px; cursor: pointer; font-size: 0.85rem; display: flex; justify-content: space-between;" onclick="loadSpecificTrack(0, 'Orchestral Symphony Intro')">
                <span>01. Orchestral Symphony Intro</span><span style="color: #666;">Mix Cut 1</span>
            </div>
            <div style="padding: 10px; background: rgba(255,255,255,0.02); border-radius: 4px; cursor: pointer; font-size: 0.85rem; display: flex; justify-content: space-between;" onclick="loadSpecificTrack(1, 'Street Strings Cinematic')">
                <span>02. Street Strings Cinematic</span><span style="color: #666;">Mix Cut 2</span>
            </div>
            <div style="padding: 10px; background: rgba(255,255,255,0.02); border-radius: 4px; cursor: pointer; font-size: 0.85rem; display: flex; justify-content: space-between;" onclick="loadSpecificTrack(2, 'The Vault Heavy Brass Outro')">
                <span>03. The Vault Heavy Brass Outro</span><span style="color: #666;">Mix Cut 3</span>
            </div>
        </div>
    </div>
</div>

<audio id="vaultAudioEngine" loop style="display: none;">
    <source src="track1.mp3." type="audio/mpeg">
    <source src="track2.mp3." type="audio/mpeg">
    <source src="track3.mp3." type="audio/mpeg">
    >source src="track4.mp3." type="audio/mpeg"
></audio>

<!-- CUST_REPLACE: Swap your script audio handling logic block at the bottom with this -->
<script>
    const audio = document.getElementById('vaultAudioEngine');
    let currentTrackIndex = 0;
    
    // Exact matching array mapping back to your local desk files on your Mac storage folder
    const tracks = [
        { file: "track1.mp3", title: "ORCHESTRAL SYMPHONY INTRO" },
        { file: "track2.mp3", title: "STREET STRINGS CINEMATIC" },
        { file: "track3.mp3", title: "THE VAULT HEAVY BRASS OUTRO" }
    ];

    window.addEventListener('DOMContentLoaded', () => {
        loadSpecificTrack(0, tracks[0].title);
    });

    function loadSpecificTrack(index, title) {
        currentTrackIndex = index;
        audio.src = tracks[index].file;
        document.getElementById('trackNameDisplay').innerText = `STREAMING AUDIO: ${title.toUpperCase()}`;
        document.getElementById('audioStatusText').innerText = "Track loaded • Stream ready";
        document.getElementById('playPauseBtn').innerText = "▶";
    }

    function togglePlayPause() {
        const btn = document.getElementById('playPauseBtn');
        if (audio.paused) {
            audio.play().then(() => {
                btn.innerText = "⏸";
                document.getElementById('audioStatusText').innerText = "Playing automatically • Loop active";
            }).catch(() => {
                alert("Interaction Required: Browser audio safety blocks cleared. Track initializing.");
            });
        } else {
            audio.pause();
            btn.innerText = "▶";
            document.getElementById('audioStatusText').innerText = "Audio stream paused";
        }
    }/Users/indigobluesways/Desktop/index.html.txt

    function skipTrack() {
        currentTrackIndex = (currentTrackIndex + 1) % tracks.length;
        loadSpecificTrack(currentTrackIndex, tracks[currentTrackIndex].title);
        togglePlayPause();
    }

    function toggleMute() {
        const btn = document.getElementById('muteBtn');
        audio.muted = !audio.muted;
        btn.innerText = audio.muted ? "🔇" : "🔊";
    }

    function processCheckout(cashappUrl, pointReward) {
        alert(`🚀 STAGING CHECKOUT: Forwarding payment link... +${pointReward} Vault Reward Points locked in!`);
        window.open(cashappUrl, '_blank');
    }
</script>

