# 🧪 XAScribe

AI-powered research assistant for X-ray Absorption Spectroscopy (XAS) analysis and manuscript generation using Google Gemini 2.5 Flash and RAG technology.

## Features

- **XAS Data Analysis**: Upload and analyze experimental data with machine learning models
- **Literature Processing**: Process research papers for context-aware manuscript generation with intelligent caching
- **AI Manuscript Generation**: Create academic content with proper citations using Gemini 2.5 Flash
- **Smart Caching**: Automatically reuses processed papers from previous sessions - no need to re-upload
- **Optional Uploads**: Add new papers to existing collections or work with cached data only
- **Interactive Workflow**: Streamlined interface with automatic detection of existing data

## Quick Start

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Get Google Gemini API Key
1. Visit [Google AI Studio](https://aistudio.google.com/)
2. Create an API key for Gemini
3. Keep it ready for the app interface

### 3. Run the Application
```bash
streamlit run app.py
```

### 4. Access the App
Open your browser to the URL shown in terminal (typically `http://localhost:8501`)

## Usage

1. **Enter API Key** in the sidebar
2. **Check Existing Data**: App automatically detects papers from previous sessions
3. **Upload Data** (optional): 
   - XAS data files (JSON, CSV, XLSX, TXT)
   - Additional research papers (individual TXT files or ZIP archive)
4. **Process Data**: Initialize with existing papers or add new ones to your collection
5. **Generate Manuscript**: Enter your research question and generate academic content

### Smart Caching System

- **First Run**: Upload research papers and XAS data - system creates cache files
- **Subsequent Runs**: Papers are automatically detected and loaded from cache
- **Adding Papers**: Upload additional papers to expand your existing collection
- **Cache Files**: `rag_cache.pkl` (metadata) and `embeddings_cache.pkl` (vector embeddings)

## Example Data

The project includes:
- `example_xas_data/nmc_exp_xas.json` - Sample XAS experimental data
- `example_papers/` - 24 research papers about XAS studies on battery cathodes
- `paper_metadata.csv` - Citation metadata for proper referencing

## File Structure

```
├── app.py                    # Main Streamlit application
├── rag.py                    # RAG system with FAISS vector search
├── Backend/Modeling.py       # XAS data analysis pipeline
├── requirements.txt          # Python dependencies
├── paper_metadata.csv        # Citation metadata
├── rag_cache.pkl             # Cached paper metadata (auto-generated)
├── embeddings_cache.pkl      # Cached vector embeddings (auto-generated)
├── converted_papers/         # Processed paper text files (auto-generated)
├── example_xas_data/         # Sample experimental data
└── example_papers/           # Sample research papers
```

## Configuration

Set your API key via:
- Streamlit sidebar interface (recommended)
- Environment variable: `export GOOGLE_API_KEY="your-key"`

## Technologies

- **Frontend**: Streamlit
- **AI**: Google Gemini 2.5 Flash
- **Vector Search**: FAISS (Facebook AI Similarity Search)
- **Embeddings**: BGE-large-en (sentence-transformers)
- **ML**: Scikit-learn, SHAP
- **Materials Science**: Pymatgen
- **Caching**: Python pickle for persistent storage

## Troubleshooting

- **API Key Error**: Verify your Gemini API key is valid and has access to Gemini 2.5 Flash
- **File Format**: Use supported formats (JSON, CSV, XLSX, TXT, ZIP)
- **Memory Issues**: Process smaller batches for large datasets
- **Cache Issues**: Delete `rag_cache.pkl` and `embeddings_cache.pkl` to force re-processing
- **Missing Papers**: Check `converted_papers/` folder for processed text files
- **Model Not Found**: Ensure your API key has access to the latest Gemini models

## Cache Management

- **Cache Location**: All cache files are stored in the project root directory
- **Force Refresh**: Delete cache files to re-process papers with updated parameters
- **Backup**: Cache files can be backed up to preserve processed literature databases
- **Sharing**: Share `rag_cache.pkl` and `embeddings_cache.pkl` to distribute processed datasets

---

**XAScribe v2.0** - Advanced AI Research Platform for Materials Science with Smart Caching
