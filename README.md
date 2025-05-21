\documentclass[12pt]{article}
\usepackage{amsmath}
\usepackage{graphicx}
\usepackage{geometry}
\usepackage{hyperref}
\geometry{margin=1in}

\title{Are You Bored Yet? - Documentation}
\author{}

\begin{document}

\maketitle

\section*{1. Boredom Score Definition}

We define a \textbf{continuous disengagement score} (boredom) for each trial using two main behavioral indicators:

\begin{itemize}
  \item \textbf{Reaction Time (RT)}
  \item \textbf{Dropout Indicator}
  \item \textbf{Correct Choice}
\end{itemize}


The raw boredom score is computed as:

\[\text{Boredom\_Raw} = 0.8 \times \text{srt} + 0.3\times \text{dropout} \times \text{rt} + 0.4 \times \text{Leave Frequency} \times \text{rt} - 2 \times \text{Choice Average} \]
Where:
\begin{itemize}
  \item \texttt{srt} is a rolling mean of reaction times over a 30-trial window.
  \item \texttt{dropout} is a binary flag indicating trials with ITD( inter-trial delay) $>$ 5 seconds.
\end{itemize}

We then normalize the raw boredom score within each session to ensure comparability across sessions:
\[
\text{boredom\_norm} = \frac{\text{boredom\_raw} - \mu}{\sigma}
\]


\section*{2. Behavioral Proxies for Disengagement}

The following behavioral signals were selected as proxies for disengagement:

\begin{itemize}
  \item \textbf{Slow Responses}: Increasing reaction times typically reflect reduced attention or fatigue.
  \item \textbf{Dropouts}: Trials without any action show disinterest.
  \item \textbf{Rolling Accuracy Drop} (used during feature engineering): A decline in performance shows boreness in performing correct action.
\end{itemize}

\end{document}
