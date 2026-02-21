# Quickstart Guide: ROS 2 Middleware for Humanoid Robotics

## Prerequisites
- Node.js 18+ and npm/yarn
- Python 3.11+
- Access to OpenAI API key
- Qdrant Cloud account
- Neon Postgres account

## Setup Instructions

### 1. Clone and Initialize the Repository
```bash
git clone <repository-url>
cd hackathon_book_creation
```

### 2. Install Backend Dependencies
```bash
cd backend
pip install -r requirements.txt
```

### 3. Configure Environment Variables
Create a `.env` file in the root directory:
```env
OPENAI_API_KEY=your_openai_api_key
QDRANT_URL=your_qdrant_cloud_url
QDRANT_API_KEY=your_qdrant_api_key
DATABASE_URL=your_neon_postgres_connection_string
```

### 4. Install Docusaurus Dependencies
```bash
cd docusaurus
npm install
```

### 5. Run the Backend Service
```bash
cd backend
python -m uvicorn src.main:app --reload
```
Backend will start on http://localhost:8000

### 6. Run Docusaurus Locally
```bash
cd docusaurus
npm start
```
Documentation site will be available at http://localhost:3000

## Adding New Content

### 1. Create a New Chapter
Add your Markdown file to the appropriate module directory in `docusaurus/docs/`:
- `docusaurus/docs/ros2-middleware/new-chapter.md`
- `docusaurus/docs/gazebo-unity/new-chapter.md`
- `docusaurus/docs/nvidia-isaac/new-chapter.md`
- `docusaurus/docs/vla/new-chapter.md`

### 2. Index the Content for RAG
Run the indexing script to add new content to the vector store:
```bash
cd backend
python src/utils/document_loader.py
```

## Running the Application

### Development Mode
1. Start the backend: `cd backend && python -m uvicorn src.main:app --reload`
2. Start Docusaurus: `cd docusaurus && npm start`
3. Access the documentation at http://localhost:3000
4. RAG chat functionality will be embedded in the documentation pages

### Production Build
1. Build the backend: `cd backend && pip install -r requirements.txt`
2. Build Docusaurus: `cd docusaurus && npm run build`
3. Serve the Docusaurus build: `cd docusaurus && npm run serve`

## Testing the RAG Functionality
1. Navigate to any documentation page
2. Use the embedded chatbot to ask questions about the content
3. Verify that responses are grounded in the documentation content
4. Check that confidence scores are provided with responses

## Deployment to GitHub Pages
1. Build the Docusaurus site: `cd docusaurus && npm run build`
2. The output will be in the `build` directory
3. Configure GitHub Actions or manually deploy to your GitHub Pages branch
4. Ensure the backend service is deployed separately with public access