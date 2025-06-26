# Volatility-Modeling-GARCH
Modeling and forecasting BTC volatility using GARCH model 

Il cuore del progetto è l'implementazione di un modello GARCH(1,1) per catturare il fenomeno del volatility clustering, confrontare le stime con i dati storici e prevedere l'andamento futuro della volatilità. Questo tipo di analisi è fondamentale per la gestione del rischio (risk management), il pricing di derivati e lo sviluppo di strategie di trading avanzate.

📜 Indice
Concetti Chiave

Tecnologie e Librerie

Struttura del Progetto

Risultati dell'Analisi

Limiti e Sviluppi Futuri

Autore

Licenza

🔑 Concetti Chiave
Volatility Clustering (Raggruppamento della Volatilità)
È il fenomeno, osservabile in quasi tutte le serie storiche finanziarie, per cui periodi di alta volatilità (grandi oscillazioni di prezzo) tendono a essere seguiti da altri periodi di alta volatilità, e periodi di calma tendono a essere seguiti da altri periodi di calma. Il nostro obiettivo è modellizzare matematicamente questo comportamento.

Modello GARCH
GARCH (Generalized Autoregressive Conditional Heteroskedasticity) è un modello econometrico creato appositamente per catturare il volatility clustering. Un modello GARCH(1,1) prevede la volatilità di domani basandosi su una combinazione di tre fattori:

Una volatilità media di lungo periodo (la costante omega).

La volatilità prevista ieri (il termine GARCH, beta). Questo modella la persistenza della volatilità.

La "sorpresa" (magnitudo) nel rendimento di ieri (il termine ARCH, alpha). Questo modella la reattività della volatilità a nuovi shock di mercato.

🛠️ Tecnologie e Librerie
Python 3.x

arch: Libreria specializzata per la stima di modelli GARCH e altre analisi econometriche.

yfinance: Per scaricare i dati storici di mercato da Yahoo Finance.

pandas & NumPy: Per la manipolazione dei dati e i calcoli numerici.

Matplotlib & Seaborn: Per la visualizzazione grafica dei risultati.

Jupyter Notebook / Google Colab: Come ambiente di sviluppo interattivo.

📁 Struttura del Progetto
Download dei Dati: Acquisizione dei dati storici per BTC-USD.

Calcolo dei Rendimenti: Trasformazione dei prezzi in rendimenti logaritmici.

Analisi della Volatilità Realizzata: Calcolo e visualizzazione della volatilità storica come benchmark.

Stima del Modello GARCH(1,1): Fitting del modello sui dati dei rendimenti.

Confronto e Validazione: Visualizzazione della volatilità prevista dal modello contro quella realizzata.

Forecast: Previsione della volatilità per i 30 giorni successivi.

📊 Risultati dell'Analisi
I risultati mostrano come il modello GARCH(1,1) sia in grado di catturare efficacemente le dinamiche della volatilità di Bitcoin.

Interpretazione dei Risultati del Modello
Dal sommario del modello GARCH(1,1) si evincono i seguenti punti chiave:

mu (0.1864): Stima del rendimento medio costante, risultato statisticamente significativo.

omega (0.7128): Rappresenta il livello di base (costante) della volatilità.

alpha[1] (0.1162): Il coefficiente ARCH. Indica che i grandi movimenti di prezzo di ieri (positivi o negativi) aumentano la volatilità di oggi. È statisticamente significativo.

beta[1] (0.8389): Il coefficiente GARCH. Indica che la volatilità di ieri tende a "persistere" anche oggi. Il suo valore elevato e la sua significatività statistica sono cruciali.

La somma di alpha + beta (0.9551) è molto vicina a 1, il che conferma una forte persistenza degli shock di volatilità, una caratteristica tipica delle serie finanziarie.

Volatilità Prevista vs. Realizzata e Forecast
Il grafico seguente confronta la volatilità storica (linea grigia) con quella stimata dal modello (linea rossa), mostrando un'ottima capacità di catturare i picchi e le valli del rischio.

<img width="637" alt="Screenshot 2025-06-26 alle 15 43 58" src="https://github.com/user-attachments/assets/b8958694-d68c-4464-ac83-ce327f5af78f" />

La previsione a 30 giorni (l'estensione della linea rossa) mostra il percorso atteso della volatilità. Basandosi sui dati più recenti, il modello ha prodotto le seguenti stime:

Volatilità prevista per domani: 48.77% (annualizzata).

Volatilità media prevista per i prossimi 30 giorni: 62.13% (annualizzata).

<img width="637" alt="Screenshot 2025-06-26 alle 15 44 24" src="https://github.com/user-attachments/assets/9d5a28b8-2832-4293-b156-5b5da9744a43" />

In sintesi, il modello ha appreso con successo i pattern di volatilità dai dati storici e li ha utilizzati per fornire una previsione quantitativa e statisticamente fondata del rischio futuro.

🧐 Limiti e Sviluppi Futuri
Effetto Leva (Leverage Effect): Si potrebbe testare un modello EGARCH o GJR-GARCH per catturare l'asimmetria per cui le notizie negative tendono a impattare la volatilità più di quelle positive.

Distribuzione dei Rendimenti: Il modello attuale assume una distribuzione Normale. Si potrebbe ottenere un fit migliore utilizzando una distribuzione t di Student per tenere conto delle "code grasse" (fat tails) tipiche dei rendimenti finanziari.

Cambio di Regime: Per asset come Bitcoin, si potrebbe utilizzare un modello Markov Switching GARCH per catturare cambiamenti strutturali nella dinamica della volatilità (es. pre e post-halving).

👨‍💻 Autore
Pietro Bonamin

Profilo LinkedIn: https://www.linkedin.com/in/pietro-bonamin-127666203/

Profilo GitHub: https://github.com/bonaminpietro

📄 Licenza
Questo progetto è rilasciato sotto la Licenza MIT.
