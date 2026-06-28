Here are the instructions for Claude to modify the poster:

In the section Beyond Black-Box: Predictions Through Clinical Concepts, make these changes:

Remove Figure 4 (CBM framework with LLM dashed lines) entirely.
Remove Table 2 (the Ghia vs Leschly comparison table) entirely.
Keep Figure 5 (CBM vs CEM diagram) but make it smaller: \includegraphics[width=0.75\linewidth]
Add a brief caption under Figure 5 replacing Table 2, something like:

latex\captionof{figure}{CBM vs.\ CEM: binary nodes vs.\ embedding pairs.
Note: text serves opposite roles --- offline label generator (Ghia et al.)
vs.\ live multimodal input (Leschly et al.)\cite{ghia2024, leschly2025}.}

Make Figure 6 (RAG diagram) smaller: \includegraphics[width=0.75\linewidth]
Keep the CBM text but shorten to one sentence:

latexThe model predicts named clinical symptoms before classifying ---
at test time, only the audio model runs.

Keep the CEM text as is (already short).
Keep Table 3 (results) and the Key Finding box as is.

The goal is to fit everything on one page by removing Figure 4, Table 2, and shrinking Figures 5 and 6.