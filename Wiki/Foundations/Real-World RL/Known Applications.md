# Notable Real-World Examples

Recent work on using Reinforcement Learning for inventory control has been established \cite{boute:2022}. This includes an application used at Amazon \cite{madeka:2022}. Furthermore, \cite{Osborne:RL4RL-book} provides a detailed set of examples based on published articles and summarised as: 

\begin{itemize} 
    \item \textbf{Google Data Centre:} A Google DeepMind article \cite{Google:2016} describes the challenges faced when optimising energy consumption in their data centers and how Reinforcement Learning can help us become more energy efficient. 
    \item \textbf{Salesforce Text Summarizing:} A research team within Salesforce described their challenges and solutions to parse and summarize long pieces of text. This was published in an academic paper \cite{SalesforcePaper:2017} and a follow-up post online \cite{Salesforce:2017}.
    \item \textbf{IBM Stock Trading:} As described by \cite{IBM:2018}, IBM uses Reinforcement Learning for financial trading.
    \item \textbf{SCG Chemical Production:} \textit{The Siam Cement Group Public Company Limited (SCG)} is one of the largest integrated petrochemical companies in Thailand. A key objective of SCG is the reduction of waste and minimizing out of spec products for all chemical processing as described in \cite{SCG:2020}.
\end{itemize}



A recent article in the Harvard Business Review also provides a summary of notable examples of real-world RL \cite{Hume:2021} shown in Table \ref{tab:commercial_applications}.

\begin{table}[ht]
    \centering
    \begin{tabular}{p{1.5cm}|p{2.5cm}|p{1.5cm}|p{2.5cm}|p{2.5cm}|p{2.5cm}}
         \textbf{Company} & \textbf{Application} & \textbf{Sector} & \textbf{Inputs} & \textbf{Actions} & \textbf{Objective} \\
         \hline
         Royal Bank of Canada & Trade execution platform for multiple strategies & Financial services & 200-plus market-related data inputs & Sell, buy, hold stocks & To trade as close as possible to VWAP, a common price metric \\
         \hline
         Netflix & Test schedules for business partner devices & Technology & Historical test and device performance information & Which test to do next & Minimize device failure \\
         \hline
         Spotify & Recommendation engine & Entertainment & Previous songs liked/disliked/not played & Which songs to put in your playlist & Maximize user listening time \\
         \hline
         JPMorgan Chase & Financial derivatives risk and pricing calculations & Financial services & Historical market data & Price and sell a financial product & Maximize future cash flows of an investment portfolio \\
         \hline
         Google & Data center cooling & Technology & Temperature/air pressure & Turn on fan, add water to air unit & Control temperature and reduce energy usage \\
         \hline
         DiDi & Order dispatching & Ride hailing & Number of idle vehicles, number of orders, location, destination & Match drivers to passengers & Minimize pickup time and maximize revenue
         
\end{tabular}
\caption{Notable commercial applications of Reinforcement Learning \cite{Hume:2021}.}
\label{tab:commercial_applications}
\end{table}

