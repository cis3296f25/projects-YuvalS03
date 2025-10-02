# WearHouse POC

In this project, I propose developing WearHouse, a smart digital closet app designed to help users manage their wardrobe and plan outfits more efficiently. Many people struggle with decision-making and fatigue when choosing their daily outfits, especially when they try to account for different weather conditions, various social/professional events, and the desire to have variety in their outfits. WearHouse addresses this by allowing users to integrate calendar events and local weather forecasts into the app, ensuring that recommendations are not only stylish but context-appropriate. Users upload images of their clothing items, which are automatically processed with a background remover to create a clean visual of their clothes. Items can be tagged by category, color, and formality. This enables the user to utilize the system to combine pieces into practical outfits. The app will include an outfit generator that uses simple rules to avoid clashes, prevent repeats, and align clothing choices with formality and climate types. The intended users include anyone who cares or needs to care about what they wear on a regular basis. Specifically, those who want to save time doing so, while being stylish, experimental, and prepared. As a stretch goal, WearHouse would like to develop an avatar-based try-on feature that would allow users to preview their outfits on a personal photo overlay or maybe even a digital mannequin. Maybe also add a swiping on clothes feature based on what you have previously uploaded.


Proof of concept for a smart digital wardrobe. Demonstrates:  
- Uploading clothes with metadata.  
- Background removal via a Node/Express proxy to **remove.bg**.  
- Storage in **Supabase** (Postgres + Storage).  
- Simple rules-based outfit generator (mocked calendar + weather).  

---

## Tech Stack
- **Frontend:** React + Vite  
- **Backend Proxy:** Node.js + Express  
- **Database & Storage:** Supabase  
- **Image Processing:** remove.bg API  

---

## Setup
0. Version:
   Microsoft Windows 10, Version 22H2 (OS Build 19045.6332)
   npm Version 10.5.0
   node Version 20.13.1
1. Clone and install:  
   ```bash
   git clone https://github.com/YOUR-USERNAME/wearhouse-poc.git
   cd wearhouse-poc 
   npm install
   ```
2. Create Supabase project, bucket `items`, and `items` table.  
3. Add `.env` in root:  
   ```
   VITE_SUPABASE_URL=your-url
   VITE_SUPABASE_ANON=your-anon-key
   VITE_REMOVE_BG_PROXY=http://localhost:3001/remove-bg
   ```
4. Start proxy (in `/server`):  
   ```bash
   npm install
   echo "REMOVE_BG_KEY=your-removebg-key" > .env
   npm start
   ```
5. Run frontend:  
   ```bash
   npm run dev
   ```

---

## Usage
- Upload an image → proxy removes background → file stored in Supabase.  
- Metadata saved in DB.  
- Items display in grid.  
- “Suggest Outfit” picks a top + bottom using mock calendar/weather.  





Disclaimer: Some code in this repository was generated using AI.