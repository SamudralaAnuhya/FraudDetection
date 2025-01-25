"""
Fraud Detection Chatbot using Groq Language Models
------------------------------------------------
This chatbot implements real-time fraud detection for financial transactions using Groq's powerful 
language models (mixtral-8x7b-32768, llama2-70b-4096, gemma-7b-it). It utilizes multiple prompting 
techniques (zero-shot, few-shot, chain-of-thought) to analyze transaction patterns and detect potential 
fraud risks.

Key Features:
- Interactive input for transaction details (amount, location, time)
- Multiple prompting strategies for varied analysis approaches 
- Comparative model evaluation with detailed scoring
- Transaction history tracking and CSV export
- Real-time model performance comparison
- Auto-suggestions based on customer history

Setup & Usage:
1. Install: ipywidgets, pandas
2. Configure Groq API credentials
3. Run cells in sequence
4. Input transaction details and select model/prompt type
5. Use buttons:
  - Submit: Generate analysis
  - Export: Save to CSV
  - Evaluate: Compare model responses (needs 2+ transactions)

Note: For best results, maintain consistent Customer IDs and try different prompting techniques
"""

import ipywidgets as widgets
from IPython.display import Markdown, display
from us import states
import pandas as pd
import re
