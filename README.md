# 🕷️ Apify Platform Integration

A dynamic web interface that connects to the Apify platform, fetches actors with their schemas, and executes real web scraping tasks.

## 📋 README Requirements (As Specified)

✅ **How to install and run your application**  
✅ **Which actor you chose for testing**  
✅ **Any assumptions or notable design choices you made**  
✅ **Screenshots or brief notes demonstrating the working flow**

## 🚀 Quick Setup & Run

### 1. Install and Run

Clone or download the project
git clone https://github.com/arnavgupta007/apify-platform-integration

cd apify-platform-integration

Setup backend
cd backend
npm install
npm run dev


**You should see:** `🎉 Proxy server running successfully!`

Open frontend
Simply open frontend/index.html in your browser


### 2. Get Running in 2 Minutes

1. **Get Apify API Key:** [console.apify.com/account/integrations](https://console.apify.com/account/integrations)
2. **Enter API key** in the web interface
3. **Click "Connect to Real Apify"**
4. **Select an actor** (Web Scraper recommended)
5. **Fill form and click "Run Real Actor"**

## 🎭 Actor Used for Testing

**Primary Test Actor:** `apify/web-scraper`
- **Why chosen:** Most popular, well-documented, handles dynamic content
- **Test URLs used:** 
  - `https://quotes.toscrape.com/`
  - `https://books.toscrape.com/`
- **Results:** Successfully scrapes and stores data in Apify datasets

**Alternative actors tested:**
- `apify/cheerio-scraper` (faster, server-side scraping)
- User's personal actors (if available)

## 🏗️ Design Choices & Assumptions

### Key Design Decisions:

1. **Node.js Proxy Server**
   - **Why:** Solves CORS issues when calling Apify API from browser
   - **Alternative considered:** Direct API calls (blocked by CORS)

2. **Dynamic Schema Forms**
   - **Assumption:** All actor schemas follow JSON Schema format
   - **Fallback:** Generic form when schema unavailable

3. **Real-time Polling**
   - **Choice:** 5-second intervals to check run status
   - **Assumption:** Most runs complete within 2-3 minutes

4. **Single HTML File Frontend**
   - **Why:** Simplicity, no build process needed
   - **Trade-off:** Larger file size vs. easy deployment

### Assumptions Made:

- User has valid Apify account and API key
- Node.js 18+ is available
- Modern browser with JavaScript enabled
- Port 3001 is available for proxy server

## 📸 Working Flow Demonstration

### Step 1: Authentication
<img width="1858" height="898" alt="image" src="https://github.com/user-attachments/assets/d7fb33f9-5512-4e53-bc81-f5b5809f7bba" />

- Enter API key → Connect to real Apify account
- 
### Step 2: Actor Selection
- Shows personal + public actors → Dynamic loading from your account

### Step 3: Configuration
- Auto-generated form from actor schema → Fill parameters

### Step 4: Execution & Results
- Real-time execution → Dataset stored in your Apify account

## ✅ Success Verification

**You'll know it's working when you see:**
{
"🎉 REAL Run Information": {

"Run ID": "actual_run_id_here",

"Status": "SUCCEEDED",

"Dataset ID": "actual_dataset_id",

"Items Found": 10

}
}

**Check your Apify Console:** [console.apify.com/datasets](https://console.apify.com/datasets)

## 🔧 Project Structure
apify-platform-integration/

├── backend/

│ ├── server.js # Express proxy server

│ ├── package.json # Dependencies

│ └── .env.example

└── frontend/

└── index.html # Complete web app

## 🐛 Quick Fixes


**Server won't start?**
Try different port
cd backend
PORT=3002 npm run dev

**No actors showing?**
- Normal for new accounts
- Public actors (Web Scraper, etc.) will still appear
- Create actors at [console.apify.com/actors](https://console.apify.com/actors)

**CORS errors?**
- Ensure backend server is running
- Refresh browser page

## 📊 Test Data Output Example

**Input:** `https://quotes.toscrape.com/`
**Output:** Real scraped data in your Apify account

*Total setup time: ~3 minutes | Real web scraping in action! 🚀**
