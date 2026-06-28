%========================================================================================
%   Concept-Based Architectures
%========================================================================================
\section{Beyond Black-Box: Predictions Through Clinical Concepts}
\boxtitle{Beyond Black-Box: Predictions Through Clinical Concepts}
\vspace{1cm}

%----------------------------------------------------------------------------------------
\subsection*{Concept Bottleneck Models (CBM)}
\boxsubtitle{Concept Bottleneck Models (CBM)}
\vspace{0.5cm}

The model predicts named clinical symptoms before classifying.
An LLM (Gemini-pro) annotates training data from unstructured
medical notes --- at test time, only the audio model runs.

\begin{center}
\includegraphics[width=\linewidth]{figures/cbm_framework.png}
\captionof{figure}{Audio mapped through a clinical concept layer
before prediction. LLM used at training only
(dashed)\cite{ghia2024}.}
\end{center}
\vspace{0.5cm}

\begin{center}
\renewcommand{\arraystretch}{1.5}
\begin{tabularx}{\linewidth}{|>{\raggedright\arraybackslash}p{0.28\linewidth}
                              |>{\raggedright\arraybackslash}X
                              |>{\raggedright\arraybackslash}X|}
\hline
 & \textbf{Ghia et al.} & \textbf{Leschly et al.} \\ \hline
\textbf{Role of text}
  & Training only (LLM labels)
  & Live test input (BERT) \\ \hline
\textbf{Inference input}
  & Audio only (HuBERT)
  & Audio + text \\ \hline
\textbf{Concept targets}
  & Vocal acoustics
  & Patient symptoms \\ \hline
\end{tabularx}
\captionof{table}{Text serves opposite roles across
studies\cite{ghia2024, leschly2025}.}
\end{center}
\vspace{1cm}

%----------------------------------------------------------------------------------------
\subsection*{From Binary Nodes to Embeddings: CEM}
\boxsubtitle{From Binary Nodes to Embeddings: CEM}
\vspace{0.5cm}

CBM assigns one binary node per concept. CEM replaces it with
an active/inactive embedding pair --- richer and equally
interpretable.

\begin{center}
\includegraphics[width=\linewidth]{figures/cbm_cem_architecture.png}
\captionof{figure}{CBM vs.\ CEM: binary nodes vs.\
embedding pairs per vocal concept\cite{ghia2024}.}
\end{center}
\vspace{1cm}

%----------------------------------------------------------------------------------------
\subsection*{Literature-Grounded Explanations (RAG)}
\boxsubtitle{Literature-Grounded Explanations (RAG)}
\vspace{0.5cm}

Predicted concepts retrieve peer-reviewed evidence and generate
a clinician-readable report --- no post-hoc step needed.

\begin{center}
\includegraphics[width=\linewidth]{figures/neuroxvocal_architecture.png}
\captionof{figure}{NeuroXVocal: concepts drive RAG retrieval
from medical literature, producing evidence-grounded
reports\cite{ntampakis2025}.}
\end{center}
\vspace{1cm}

%----------------------------------------------------------------------------------------
\subsection*{Results}
\boxsubtitle{Results}
\vspace{0.5cm}

\begin{center}
\renewcommand{\arraystretch}{1.5}
\begin{tabularx}{\linewidth}{|>{\raggedright\arraybackslash}p{0.24\linewidth}
                              |>{\raggedright\arraybackslash}X
                              |>{\centering\arraybackslash}p{0.20\linewidth}|}
\hline
\textbf{Task} & \textbf{Model} & \textbf{Score} \\ \hline
\multirow{2}{*}{Voice disorder}
  & HuBERT black-box    & 0.909 F1 \\
  & CEM                 & 0.860 F1 \\ \hline
\multirow{2}{*}{Dysarthria}
  & Black-box CNN       & 82.5\% Acc \\
  & + concept layer     & \textbf{83.9\%} Acc \\ \hline
\multirow{2}{*}{MCI}
  & Baseline            & 0.58 AUC \\
  & + concept layer     & \textbf{0.62 AUC} \\ \hline
Alzheimer's
  & NeuroXVocal         & \textbf{0.958 F1} \\ \hline
\end{tabularx}
\captionof{table}{Concept-based models match or exceed
black-box baselines across all four disorders.}
\end{center}

\vspace{0.5cm}
\colorbox{yellow!10}{%
  \parbox{\dimexpr\linewidth-2\fboxsep}{%
    \LARGE
    \textbf{\color{Black}Key Finding:} Concept-based models
    predict \textit{through} clinical symptoms ---
    accurate, transparent, no post-hoc approximation.
  }%
}
\vspace{1cm}

figures/cbm_framework.pngFig. 1 — Ghia et al.figures/cbm_cem_architecture.pngFig. 2 — Ghia et al.figures/neuroxvocal_architecture.pngFig. 1 — Ntampakis et al.