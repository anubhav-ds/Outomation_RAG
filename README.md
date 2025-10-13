# Outamation RAG Pipeline

This repo contains milestone relevant projects I completed during externship at Outamation AI for RAG based Workflow Automation.

During the externship, main focus was to automate Mortgage loan application using advanced document intelligence techniques. For this we focused on Advanced RAG pipeline on Llama Index and used Gradio app interface to design end users application of RAG pipeline. 

Final project notebook is Outomation_RAG_pipeline.ipynb and slides are also for that specific notebook. Main features of this RAG Project:
1. Whole pipeline was made on a local LLM, Llama3.1 8B Instruct Q8, tested 7 other different local instruct LLMs as Outomation required us to use local LLM for security and cost benefits.
2. Ability to parse PDF based documents, both scanned and digital documents via PyMuPDF and Tesseract OCR, with further specialized extraction for tables via Camelot.
3. Used Local LLM to create Logical Documents and advanced Metadata.
4. Applied Recursive splitting and then Semantic chunking to the logical documents.
5. Used FAISS Vector Storage with L2 similarity.
6. Used query routing and metadata filtering to enrich retriever.
7. Used advanced retriever consisting of Dense and Boosted BM25 Retrievers powered by Query Expansion and crossnecoder Rerankers.
8. Used Local LLM for query engine with custom formatting
9. RAG Pipeline Evaluation
10. Optimized RAG Pipeline for latency and launched it on a Gradio APP allowing users to upload multiple documents, do Q&A on them, visualize top 3 nodes with scores, and PDF viewer with retriever top K slider.

On our testing with test dataset having documents from web and Outomation, containing distinct names, intents, and categories we obtained Recall@5 of 73.3% and Recall@8 of 86.7%. Accuracy was 66.67% on Local LLM, and 90%+ on Gemini API. We expect to see better result in both metrics in customer application processing as we can further enrich the metadata and by using a better LLM we could get better accuracy and improved latency as our local LLM was limited to local hardware.
