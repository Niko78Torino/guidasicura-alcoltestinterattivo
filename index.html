<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Guida Sicura: Alcoltest Interattivo</title>
    <meta name="google-adsense-account" content="ca-pub-8268426852108056">
    <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-8268426852108056"
     crossorigin="anonymous"></script>
    <!-- ads.txt content: google.com, pub-8268426852108056, DIRECT, f08c4Tfec0942fa0 -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <!-- Chosen Palette: Warm Red -->
    <!-- Application Structure Plan: Ho progettato l'applicazione con una navigazione a schede (Simulatore, Informazioni, Fattori) per separare logicamente le diverse funzioni. L'utente atterra sul "Simulatore" per un'azione immediata. Le altre schede forniscono un contesto educativo approfondito. L'informativa sulla privacy è stata spostata nel footer per un accesso diretto e costante. -->
    <!-- Visualization & Content Choices: 
        - Dati Utente (Sesso, Pasto): Goal: Informare/Input. Metodo: Pulsanti stilizzati (radio button) per un'interazione chiara e tattile. Giustificazione: Migliore UX rispetto ai dropdown.
        - Bevande: Goal: Organizzare/Input. Metodo: Lista dinamica di card HTML/CSS. Interazione: Aggiungi/Rimuovi. Giustificazione: Gestisce input complessi in modo pulito.
        - Risultato BAC: Goal: Informare. Metodo: Testo dinamico di grandi dimensioni e colorato. Giustificazione: Massima chiarezza e impatto visivo immediato.
        - Andamento BAC: Goal: Mostrare il cambiamento. Metodo: Grafico a linee (Chart.js Canvas). Interazione: Tooltip al passaggio del mouse. Giustificazione: Visualizzazione standard ed efficace per dati temporali.
        - Tempo per Guidare: Goal: Informare. Metodo: Card di testo dinamica. Giustificazione: Fornisce una risposta chiara a una domanda chiave dell'utente.
        - Effetti BAC: Goal: Organizzare/Informare. Metodo: Tabella HTML stilizzata. Giustificazione: Presentazione chiara e strutturata di dati comparativi.
        - Fattori Chiave: Goal: Informare. Metodo: Card informative HTML/CSS con icone Unicode. Giustificazione: Suddivide il testo in blocchi digeribili e visivamente accattivanti.
        - Privacy: Goal: Informare/Rassicurare. Metodo: Sezione a comparsa nel footer. Giustificazione: Rende l'informativa accessibile senza appesantire la navigazione principale.
        - Librerie: Solo Chart.js per i grafici.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');
        body { font-family: 'Inter', sans-serif; background-color: #fef2f2; color: #334155; }
        .tab-btn.active { color: #991b1b; border-bottom-color: #991b1b; background-color: #fee2e2; }
        .tab-btn { transition: all 0.2s ease-in-out; }
        .tab-content { display: none; }
        .tab-content.active { display: block; }
        .form-radio:checked + label { background-color: #fee2e2; border-color: #f87171; color: #991b1b; }
        .bevanda-item { transition: all 0.3s ease-in-out; }
        .chart-container { position: relative; width: 100%; max-width: 800px; margin-left: auto; margin-right: auto; height: 300px; max-height: 40vh; }
        @media (min-width: 768px) { .chart-container { height: 350px; } }
        details > summary { list-style: none; }
        details > summary::-webkit-details-marker { display: none; }
        details summary .arrow { transition: transform 0.2s; }
        details[open] summary .arrow { transform: rotate(90deg); }
    </style>
</head>
<body class="antialiased">

    <div class="container mx-auto p-4 sm:p-6 lg:p-8 max-w-7xl">
        
        <header class="text-center mb-8">
            <h1 class="text-4xl md:text-5xl font-bold text-slate-800">Guida Sicura: Alcoltest Interattivo</h1>
            <p class="mt-2 text-lg text-slate-600">Simula il tuo tasso alcolemico per una guida più consapevole.</p>
        </header>

        <main>
            <div class="w-full max-w-4xl mx-auto bg-white rounded-2xl shadow-lg border border-gray-200">
                <nav class="flex border-b border-gray-200">
                    <button data-tab="simulatore" class="tab-btn flex-1 p-4 font-semibold text-gray-600 border-b-2 border-transparent hover:bg-red-50 active">Simulatore</button>
                    <button data-tab="informazioni" class="tab-btn flex-1 p-4 font-semibold text-gray-600 border-b-2 border-transparent hover:bg-red-50">Informazioni</button>
                    <button data-tab="fattori" class="tab-btn flex-1 p-4 font-semibold text-gray-600 border-b-2 border-transparent hover:bg-red-50">Fattori Chiave</button>
                </nav>

                <div class="p-6 sm:p-8">
                    <!-- Simulatore Tab -->
                    <div id="simulatore" class="tab-content active">
                        <div class="text-center mb-8">
                            <h2 class="text-2xl font-bold text-slate-800">Crea la tua Simulazione</h2>
                            <p class="mt-2 text-slate-600">Inserisci i tuoi dati e le bevande consumate per ottenere una stima del tuo tasso alcolemico (BAC) e del suo andamento nel tempo.</p>
                        </div>

                        <div class="space-y-8">
                            <!-- Step 1: Dati Personali -->
                            <div>
                                <h3 class="text-lg font-semibold mb-4 border-b pb-2 text-slate-700">1. Dati Personali</h3>
                                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                                    <div>
                                        <label class="block text-sm font-medium mb-2">Sesso Biologico</label>
                                        <div class="flex space-x-2">
                                            <input type="radio" id="sesso_m" name="sesso" value="M" class="form-radio hidden" checked>
                                            <label for="sesso_m" class="flex-1 text-center p-3 border border-gray-300 rounded-lg cursor-pointer hover:bg-red-50">Uomo</label>
                                            <input type="radio" id="sesso_f" name="sesso" value="F" class="form-radio hidden">
                                            <label for="sesso_f" class="flex-1 text-center p-3 border border-gray-300 rounded-lg cursor-pointer hover:bg-red-50">Donna</label>
                                        </div>
                                    </div>
                                    <div>
                                        <label for="peso" class="block text-sm font-medium mb-2">Peso (kg)</label>
                                        <input type="number" id="peso" placeholder="Es. 75" min="30" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-red-500 focus:border-red-500">
                                    </div>
                                    <div class="md:col-span-2">
                                        <label class="block text-sm font-medium mb-2">Consumazione</label>
                                        <div class="flex space-x-2">
                                            <input type="radio" id="pasto_pieno" name="pasto" value="pieno" class="form-radio hidden" checked>
                                            <label for="pasto_pieno" class="flex-1 text-center p-3 border border-gray-300 rounded-lg cursor-pointer hover:bg-red-50">A stomaco pieno</label>
                                            <input type="radio" id="pasto_vuoto" name="pasto" value="vuoto" class="form-radio hidden">
                                            <label for="pasto_vuoto" class="flex-1 text-center p-3 border border-gray-300 rounded-lg cursor-pointer hover:bg-red-50">A stomaco vuoto</label>
                                        </div>
                                    </div>
                                </div>
                            </div>

                            <!-- Step 2: Bevande -->
                            <div>
                                <h3 class="text-lg font-semibold mb-4 border-b pb-2 text-slate-700">2. Bevande Consumate</h3>
                                <div id="bevande-container" class="space-y-3 mb-4 min-h-[80px] flex items-center justify-center">
                                    <p id="bevande-placeholder" class="text-slate-500">Aggiungi una bevanda per iniziare.</p>
                                </div>
                                <button id="btn-aggiungi" class="w-full p-3 bg-red-100 text-red-800 font-semibold rounded-lg hover:bg-red-200 transition-colors">Aggiungi Bevanda</button>
                            </div>

                            <!-- Step 3: Tempo -->
                            <div>
                                <h3 class="text-lg font-semibold mb-4 border-b pb-2 text-slate-700">3. Tempo Trascorso</h3>
                                <label for="ore" class="block text-sm font-medium">Ore dalla fine della consumazione: <span id="ore-valore" class="font-bold text-red-600">1</span></label>
                                <input type="range" id="ore" min="0" max="24" value="1" class="w-full h-2 bg-gray-200 rounded-lg appearance-none cursor-pointer mt-2 accent-red-500">
                            </div>
                        </div>

                        <div class="mt-8 grid grid-cols-2 gap-4">
                            <button id="btn-reset" class="w-full p-4 bg-slate-200 text-slate-800 font-bold text-lg rounded-lg hover:bg-slate-300 transition-colors">Reset</button>
                            <button id="btn-calcola" class="w-full p-4 bg-red-600 text-white font-bold text-lg rounded-lg hover:bg-red-700 transition-colors">Calcola</button>
                        </div>
                        
                        <div id="error-message" class="hidden mt-4 p-4 bg-red-100 text-red-800 rounded-lg text-center font-semibold"></div>

                        <!-- Risultati -->
                        <div id="risultato-container" class="hidden mt-12">
                            <div class="text-center mb-8">
                                <h2 class="text-3xl font-bold text-slate-800">Il Tuo Risultato Stimato</h2>
                            </div>
                            <div class="bg-slate-50 p-6 rounded-xl border">
                                <div class="text-center mb-6">
                                    <p class="text-lg text-slate-600">Tasso Alcolemico Attuale (BAC)</p>
                                    <p id="bac-valore" class="text-7xl font-bold my-2">0.00</p>
                                    <p class="text-lg text-slate-600">g/L</p>
                                    <p id="interpretazione" class="mt-4 p-3 rounded-lg font-semibold text-lg"></p>
                                </div>
                                
                                <div id="tempo-guida-container" class="hidden mt-4 pt-4 border-t border-slate-200 text-center">
                                    <p id="tempo-guida-label" class="text-lg text-slate-600">Tempo per tornare alla guida:</p>
                                    <p id="tempo-guida" class="text-3xl font-bold text-slate-800"></p>
                                </div>

                                <div class="chart-container mt-6">
                                    <canvas id="bac-chart"></canvas>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Informazioni Tab -->
                    <div id="informazioni" class="tab-content space-y-6">
                        <div class="text-center mb-8">
                            <h2 class="text-2xl font-bold text-slate-800">Come Funziona e Cosa Significa</h2>
                            <p class="mt-2 text-slate-600">Questa simulazione si basa sulla formula di Widmark, un metodo scientifico per stimare la concentrazione di alcol nel sangue. Scopri di più sugli effetti del BAC e i limiti legali.</p>
                        </div>
                        <div class="p-6 bg-slate-50 rounded-lg border">
                            <h3 class="text-xl font-semibold mb-2 text-slate-700">La Formula di Widmark</h3>
                            <p class="text-slate-700">Il calcolo stima il BAC massimo dividendo i grammi di alcol ingeriti per la massa corporea moltiplicata per un coefficiente di diffusione specifico per sesso e condizione di pasto. Successivamente, sottrae l'alcol smaltito dal corpo nel tempo (circa 0.15 g/L all'ora).</p>
                        </div>
                        <div class="p-6 bg-slate-50 rounded-lg border">
                            <h3 class="text-xl font-semibold mb-2 text-slate-700">Effetti del Tasso Alcolemico (BAC)</h3>
                            <table class="w-full mt-4 text-left">
                                <thead class="bg-slate-200">
                                    <tr>
                                        <th class="p-3 font-semibold text-slate-700">BAC (g/L)</th>
                                        <th class="p-3 font-semibold text-slate-700">Effetti Comuni</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr class="border-b"><td class="p-3 font-mono">0.1 - 0.2</td><td class="p-3">Leggera euforia, sensazione di calore.</td></tr>
                                    <tr class="border-b bg-slate-50"><td class="p-3 font-mono">0.3 - 0.4</td><td class="p-3">Riflessi diminuiti, minore percezione del rischio.</td></tr>
                                    <tr class="border-b"><td class="p-3 font-mono text-amber-600 font-bold">0.5</td><td class="p-3 text-amber-600 font-bold">Limite legale per la guida. Alterazione della coordinazione.</td></tr>
                                    <tr class="border-b bg-slate-50"><td class="p-3 font-mono text-red-600 font-bold">0.8</td><td class="p-3 text-red-600 font-bold">Stato di ebbrezza. Visione offuscata, reazioni lente.</td></tr>
                                    <tr class="border-b"><td class="p-3 font-mono text-red-700 font-bold">1.5+</td><td class="p-3 text-red-700 font-bold">Grave intossicazione, rischio di perdita di coscienza.</td></tr>
                                </tbody>
                            </table>
                        </div>
                    </div>

                    <!-- Fattori Chiave Tab -->
                    <div id="fattori" class="tab-content space-y-6">
                         <div class="text-center mb-8">
                            <h2 class="text-2xl font-bold text-slate-800">Cosa Influenza il Tuo BAC</h2>
                            <p class="mt-2 text-slate-600">Il tasso alcolemico non dipende solo da quanto bevi. Diversi fattori personali giocano un ruolo cruciale nell'assorbimento e nello smaltimento dell'alcol.</p>
                        </div>
                        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                            <div class="p-6 bg-slate-50 rounded-lg border">
                                <h3 class="text-xl font-semibold mb-2 text-slate-700">Sesso Biologico</h3>
                                <p class="text-slate-700">Le donne hanno generalmente una minore percentuale di acqua corporea e diversi livelli enzimatici rispetto agli uomini, portando a un BAC più elevato a parità di alcol consumato.</p>
                            </div>
                            <div class="p-6 bg-slate-50 rounded-lg border">
                                <h3 class="text-xl font-semibold mb-2 text-slate-700">Peso Corporeo</h3>
                                <p class="text-slate-700">L'alcol si distribuisce nell'acqua corporea. Una persona con un peso maggiore ha una massa più grande in cui diluire l'alcol, risultando in un BAC inferiore.</p>
                            </div>
                            <div class="p-6 bg-slate-50 rounded-lg border">
                                <h3 class="text-xl font-semibold mb-2 text-slate-700">Cibo nello Stomaco</h3>
                                <p class="text-slate-700">Consumare alcol a stomaco pieno rallenta il suo assorbimento nel flusso sanguigno, portando a un picco di BAC più basso e ritardato rispetto al consumo a stomaco vuoto.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <footer class="text-center mt-12 space-y-4">
                <div class="max-w-4xl mx-auto p-4 bg-amber-100 border-l-4 border-amber-500 rounded-r-lg">
                    <p class="text-amber-800 text-base">⚠️ <strong>DISCLAIMER:</strong> Questo strumento fornisce solo una stima a scopo educativo. Non sostituisce un etilometro professionale. Il BAC reale può variare. Non guidare se hai bevuto.</p>
                </div>
                
                <div class="max-w-4xl mx-auto text-left">
                    <details class="bg-slate-50 p-4 rounded-lg border">
                        <summary class="font-semibold text-slate-700 cursor-pointer flex justify-between items-center">
                            <span>Leggi l'informativa sulla privacy</span>
                            <span class="arrow text-red-600">▶</span>
                        </summary>
                        <div class="mt-4 pt-4 border-t space-y-4 text-slate-700">
                             <div>
                                <h3 class="text-lg font-semibold mb-2 text-slate-700">Nessuna Raccolta Dati</h3>
                                <p>Questo strumento è progettato per garantire il completo anonimato. <strong>Non raccogliamo, salviamo, né trasmettiamo alcun dato personale</strong> inserito nel simulatore (sesso, peso, consumazioni, ecc.).</p>
                            </div>
                            <div>
                                <h3 class="text-lg font-semibold mb-2 text-slate-700">Elaborazione Esclusivamente Locale</h3>
                                <p>Tutti i calcoli necessari per stimare il tasso alcolemico avvengono <strong>esclusivamente all'interno del tuo browser</strong> (client-side). Le informazioni che inserisci non lasciano mai il tuo dispositivo e non raggiungono mai i nostri server.</p>
                            </div>
                            <div>
                                <h3 class="text-lg font-semibold mb-2 text-slate-700">Nessun Tracciamento delle Abitudini</h3>
                                <p>Non utilizziamo cookie di profilazione o altre tecnologie di tracciamento per analizzare le tue abitudini o il tuo comportamento. L'uso dello strumento è volatile: una volta chiusa la pagina, ogni informazione inserita viene eliminata definitivamente.</p>
                            </div>
                             <div>
                                <h3 class="text-lg font-semibold mb-2 text-slate-700">Scopo Educativo</h3>
                                <p>Lo scopo di questo strumento è puramente educativo e informativo. È stato creato per aumentare la consapevolezza sui fattori che influenzano il tasso alcolemico e sui rischi della guida in stato di ebbrezza, nel pieno rispetto della privacy dell'utente.</p>
                            </div>
                            <div>
                                <h3 class="text-lg font-semibold mb-2 text-slate-700">Contatti</h3>
                                <p>Per qualsiasi informazione o comunicazione riguardo la privacy, puoi scrivere a: <a href="mailto:luminaessenza1@gmail.com" class="text-red-600 hover:underline">luminaessenza1@gmail.com</a></p>
                            </div>
                        </div>
                    </details>
                </div>

                <div class="text-sm text-gray-500">
                    <p>Copyright © 2025 Nicola Nicolaci. Tutti i diritti riservati.</p>
                </div>
            </footer>
        </main>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const app = {
                bevandaCounter: 0,
                bacChart: null,
                
                bevandeStandard: {
                    'birra_chiara': { nome: 'Birra Chiara (330ml)', gradazione: 0.05, volume: 330 },
                    'birra_doppio_malto': { nome: 'Birra Doppio Malto (330ml)', gradazione: 0.08, volume: 330 },
                    'vino_rosso': { nome: 'Bicchiere Vino Rosso (150ml)', gradazione: 0.13, volume: 150 },
                    'vino_bianco': { nome: 'Bicchiere Vino Bianco (150ml)', gradazione: 0.12, volume: 150 },
                    'aperitivo': { nome: 'Aperitivo (es. Spritz, 180ml)', gradazione: 0.11, volume: 180 },
                    'superalcolico_standard': { nome: 'Shot Superalcolico (40ml)', gradazione: 0.40, volume: 40 },
                    'cocktail': { nome: 'Cocktail (es. Negroni, 100ml)', gradazione: 0.28, volume: 100 },
                    'personalizzata': { nome: 'Bevanda Personalizzata', isCustom: true }
                },

                init() {
                    this.cacheDOM();
                    this.bindEvents();
                    this.setupTabs();
                    this.updateBevandePlaceholder();
                },

                cacheDOM() {
                    this.tabs.buttons = document.querySelectorAll('.tab-btn');
                    this.tabs.contents = document.querySelectorAll('.tab-content');
                    this.ui.bevandeContainer = document.getElementById('bevande-container');
                    this.ui.bevandePlaceholder = document.getElementById('bevande-placeholder');
                    this.ui.btnAggiungi = document.getElementById('btn-aggiungi');
                    this.ui.btnCalcola = document.getElementById('btn-calcola');
                    this.ui.btnReset = document.getElementById('btn-reset');
                    this.ui.risultatoContainer = document.getElementById('risultato-container');
                    this.ui.errorMessage = document.getElementById('error-message');
                    this.ui.oreSlider = document.getElementById('ore');
                    this.ui.oreValore = document.getElementById('ore-valore');
                    this.ui.bacValore = document.getElementById('bac-valore');
                    this.ui.interpretazione = document.getElementById('interpretazione');
                    this.ui.tempoGuidaContainer = document.getElementById('tempo-guida-container');
                    this.ui.tempoGuidaLabel = document.getElementById('tempo-guida-label');
                    this.ui.tempoGuida = document.getElementById('tempo-guida');
                },
                
                ui: {},
                tabs: {},

                bindEvents() {
                    this.ui.btnAggiungi.addEventListener('click', () => this.aggiungiBevanda());
                    this.ui.btnCalcola.addEventListener('click', () => this.calcolaBAC());
                    this.ui.btnReset.addEventListener('click', () => this.resetSimulatore());
                    this.ui.oreSlider.addEventListener('input', (e) => {
                        this.ui.oreValore.textContent = e.target.value;
                    });
                },

                setupTabs() {
                    this.tabs.buttons.forEach(button => {
                        button.addEventListener('click', () => {
                            const targetTab = button.dataset.tab;
                            
                            this.tabs.buttons.forEach(btn => btn.classList.remove('active'));
                            button.classList.add('active');

                            this.tabs.contents.forEach(content => {
                                content.classList.remove('active');
                                if (content.id === targetTab) {
                                    content.classList.add('active');
                                }
                            });
                        });
                    });
                },

                updateBevandePlaceholder() {
                    const hasItems = this.ui.bevandeContainer.querySelector('.bevanda-item');
                    if (hasItems) {
                        this.ui.bevandePlaceholder.classList.add('hidden');
                    } else {
                        this.ui.bevandePlaceholder.classList.remove('hidden');
                    }
                },

                aggiungiBevanda() {
                    this.bevandaCounter++;
                    const bevandaId = `bevanda-${this.bevandaCounter}`;
                    const itemDiv = document.createElement('div');
                    itemDiv.className = 'bevanda-item bg-slate-50 p-4 rounded-lg border grid grid-cols-6 gap-4 items-center';
                    itemDiv.id = bevandaId;

                    let selectHTML = '<select class="bevanda-tipo col-span-6 md:col-span-3 w-full p-2 border border-gray-300 rounded-lg focus:ring-1 focus:ring-red-500 focus:border-red-500">';
                    for (const key in this.bevandeStandard) {
                        selectHTML += `<option value="${key}">${this.bevandeStandard[key].nome}</option>`;
                    }
                    selectHTML += '</select>';

                    itemDiv.innerHTML = `
                        ${selectHTML}
                        <div class="bevanda-details col-span-6 md:col-span-2 grid grid-cols-2 gap-2">
                            <input type="number" class="bevanda-quantita w-full p-2 border border-gray-300 rounded-lg" value="1" min="1" placeholder="Q.tà">
                            <div class="bevanda-custom-fields hidden grid grid-cols-2 gap-2">
                                <input type="number" class="custom-volume w-full p-2 border border-gray-300 rounded-lg" placeholder="ml">
                                <input type="number" class="custom-gradazione w-full p-2 border border-gray-300 rounded-lg" placeholder="%">
                            </div>
                        </div>
                        <button class="remove-btn col-span-6 md:col-span-1 bg-red-100 text-red-700 font-bold p-2 rounded-lg hover:bg-red-200">X</button>
                    `;

                    this.ui.bevandeContainer.appendChild(itemDiv);
                    this.updateBevandePlaceholder();

                    const select = itemDiv.querySelector('.bevanda-tipo');
                    const customFields = itemDiv.querySelector('.bevanda-custom-fields');
                    const quantitaInput = itemDiv.querySelector('.bevanda-quantita');

                    select.addEventListener('change', () => {
                        if (select.value === 'personalizzata') {
                            customFields.classList.remove('hidden');
                            quantitaInput.classList.add('hidden');
                        } else {
                            customFields.classList.add('hidden');
                            quantitaInput.classList.remove('hidden');
                        }
                    });

                    itemDiv.querySelector('.remove-btn').addEventListener('click', () => {
                        itemDiv.remove();
                        this.updateBevandePlaceholder();
                    });
                },
                
                resetSimulatore() {
                    document.getElementById('peso').value = '';
                    document.getElementById('sesso_m').checked = true;
                    document.getElementById('pasto_pieno').checked = true;
                    this.ui.oreSlider.value = 1;
                    this.ui.oreValore.textContent = 1;
                    this.ui.bevandeContainer.innerHTML = '';
                    this.updateBevandePlaceholder();
                    this.hideError();
                    this.ui.risultatoContainer.classList.add('hidden');
                    if (this.bacChart) {
                        this.bacChart.destroy();
                    }
                },

                showError(message) {
                    this.ui.errorMessage.textContent = message;
                    this.ui.errorMessage.classList.remove('hidden');
                    this.ui.risultatoContainer.classList.add('hidden');
                },

                hideError() {
                    this.ui.errorMessage.classList.add('hidden');
                },

                calcolaBAC() {
                    this.hideError();
                    const peso = parseFloat(document.getElementById('peso').value);
                    const ore = parseInt(this.ui.oreSlider.value);
                    if (isNaN(peso) || peso <= 20) { this.showError('Per favore, inserisci un peso valido (> 20 kg).'); return; }
                    
                    const sesso = document.querySelector('input[name="sesso"]:checked').value;
                    const pasto = document.querySelector('input[name="pasto"]:checked').value;
                    const items = this.ui.bevandeContainer.querySelectorAll('.bevanda-item');
                    if (items.length === 0) { this.showError('Aggiungi almeno una bevanda.'); return; }

                    let grammiAlcolTotali = 0;
                    const DENSITA_ALCOL = 0.789;
                    
                    for (const item of items) {
                        const tipo = item.querySelector('.bevanda-tipo').value;
                        const bevandaInfo = this.bevandeStandard[tipo];
                        
                        if (bevandaInfo.isCustom) {
                            const volume = parseFloat(item.querySelector('.custom-volume').value);
                            const gradazionePerc = parseFloat(item.querySelector('.custom-gradazione').value);
                            if (isNaN(volume) || isNaN(gradazionePerc) || volume <= 0 || gradazionePerc <= 0) {
                                this.showError('Per le bevande personalizzate, inserisci volume e gradazione validi.'); return;
                            }
                            grammiAlcolTotali += volume * (gradazionePerc / 100) * DENSITA_ALCOL;
                        } else {
                            const quantita = parseFloat(item.querySelector('.bevanda-quantita').value);
                            if (isNaN(quantita) || quantita <= 0) {
                                this.showError('Inserisci una quantità valida per le bevande.'); return;
                            }
                            grammiAlcolTotali += bevandaInfo.volume * bevandaInfo.gradazione * DENSITA_ALCOL * quantita;
                        }
                    }

                    if (grammiAlcolTotali <= 0) { this.showError('Nessun alcol consumato.'); return; }

                    const coeffDiffusione = (sesso === 'M') ? (pasto === 'pieno' ? 0.7 : 0.6) : (pasto === 'pieno' ? 0.6 : 0.5);
                    const SMALTIMENTO_ORARIO = 0.15;
                    const LIMITE_LEGALE = 0.5;
                    const bacMassimo = grammiAlcolTotali / (peso * coeffDiffusione);
                    let bacAttuale = bacMassimo - (SMALTIMENTO_ORARIO * ore);
                    if (bacAttuale < 0) bacAttuale = 0;

                    let orePerTornareSottoLimite = 0;
                    if (bacMassimo > LIMITE_LEGALE) {
                        orePerTornareSottoLimite = (bacMassimo - (LIMITE_LEGALE - 0.01)) / SMALTIMENTO_ORARIO;
                    }

                    const chartData = { labels: [], bacValues: [], currentIndex: ore };
                    let tempBac = bacMassimo;
                    let oraCorrente = 0;
                    while (tempBac > 0 && oraCorrente <= 24) {
                        chartData.labels.push(`${oraCorrente}h`);
                        chartData.bacValues.push(Math.max(0, tempBac));
                        tempBac -= SMALTIMENTO_ORARIO;
                        oraCorrente++;
                    }
                    if (chartData.labels.length === 0) {
                        chartData.labels.push('0h');
                        chartData.bacValues.push(0);
                    } else if (chartData.bacValues[chartData.bacValues.length -1] > 0) {
                         chartData.labels.push(`${oraCorrente}h`);
                         chartData.bacValues.push(0);
                    }

                    this.mostraRisultato(bacAttuale, chartData, orePerTornareSottoLimite);
                },

                mostraRisultato(bac, chartData, orePerTornareSottoLimite) {
                    this.ui.bacValore.textContent = bac.toFixed(2);
                    this.ui.interpretazione.classList.remove('bg-green-100', 'text-green-800', 'bg-yellow-100', 'text-yellow-800', 'bg-red-100', 'text-red-800');

                    if (bac < 0.5) {
                        this.ui.interpretazione.classList.add('bg-green-100', 'text-green-800');
                        this.ui.interpretazione.textContent = "Sotto il limite legale. La prudenza è sempre d'obbligo.";
                        this.ui.bacValore.style.color = '#15803d';
                    } else if (bac < 0.8) {
                        this.ui.interpretazione.classList.add('bg-yellow-100', 'text-yellow-800');
                        this.ui.interpretazione.textContent = "SOPRA IL LIMITE LEGALE. NON GUIDARE.";
                        this.ui.bacValore.style.color = '#a16207';
                    } else {
                        this.ui.interpretazione.classList.add('bg-red-100', 'text-red-800');
                        this.ui.interpretazione.textContent = "STATO DI EBBREZZA. Rischio elevato. NON GUIDARE.";
                        this.ui.bacValore.style.color = '#b91c1c';
                    }

                    const oreAttuali = parseInt(this.ui.oreSlider.value);
                    if (bac >= 0.5) {
                        const tempoRimanente = orePerTornareSottoLimite - oreAttuali;
                        if (tempoRimanente > 0) {
                            const ore = Math.floor(tempoRimanente);
                            const minuti = Math.round((tempoRimanente - ore) * 60);
                            this.ui.tempoGuida.textContent = `Circa ${ore} ore e ${minuti} minuti`;
                            this.ui.tempoGuidaLabel.textContent = 'Tempo stimato per tornare sotto il limite:';
                            this.ui.tempoGuida.style.color = '#b91c1c';
                        } else {
                            this.ui.tempoGuida.textContent = 'A breve sotto il limite';
                            this.ui.tempoGuidaLabel.textContent = 'Tempo stimato per tornare sotto il limite:';
                            this.ui.tempoGuida.style.color = '#a16207';
                        }
                    } else {
                        this.ui.tempoGuida.textContent = 'Puoi guidare in sicurezza';
                        this.ui.tempoGuidaLabel.textContent = 'Stato attuale:';
                        this.ui.tempoGuida.style.color = '#15803d';
                    }
                    this.ui.tempoGuidaContainer.classList.remove('hidden');

                    this.ui.risultatoContainer.classList.remove('hidden');
                    this.renderChart(chartData);
                    
                    setTimeout(() => {
                        this.ui.risultatoContainer.scrollIntoView({ behavior: 'smooth' });
                    }, 100);
                },
                
                renderChart(chartData) {
                    if (this.bacChart) {
                        this.bacChart.destroy();
                    }
                    const chartCtx = document.getElementById('bac-chart').getContext('2d');
                    this.bacChart = new Chart(chartCtx, {
                        type: 'line',
                        data: {
                            labels: chartData.labels,
                            datasets: [
                                {
                                    label: 'Tasso Alcolemico (g/L)',
                                    data: chartData.bacValues,
                                    borderColor: '#b91c1c',
                                    backgroundColor: 'rgba(185, 28, 28, 0.1)',
                                    fill: true,
                                    tension: 0.4,
                                    pointRadius: (ctx) => (ctx.dataIndex === chartData.currentIndex ? 6 : 3),
                                    pointBackgroundColor: (ctx) => (ctx.dataIndex === chartData.currentIndex ? '#881337' : '#b91c1c'),
                                    pointHoverRadius: 5,
                                },
                                {
                                    label: 'Limite Legale (0.5 g/L)',
                                    data: Array(chartData.labels.length).fill(0.5),
                                    borderColor: '#f59e0b',
                                    borderDash: [5, 5],
                                    borderWidth: 2,
                                    pointRadius: 0,
                                    fill: false,
                                }
                            ]
                        },
                        options: {
                            responsive: true,
                            maintainAspectRatio: false,
                            plugins: {
                                title: { display: true, text: 'Andamento Stimato del BAC nel Tempo', font: { size: 16 }, color: '#334155', padding: { bottom: 20 } },
                                legend: { position: 'bottom', labels: { color: '#334155' } },
                                tooltip: {
                                    callbacks: {
                                        footer: (tooltipItems) => {
                                            if (tooltipItems[0].datasetIndex === 0 && tooltipItems[0].dataIndex === chartData.currentIndex) {
                                                return 'Stima attuale.';
                                            }
                                            return '';
                                        }
                                    }
                                }
                            },
                            scales: {
                                x: { title: { display: true, text: 'Ore dalla fine della consumazione', color: '#475569' }, ticks: { color: '#475569' }, grid: { display: false } },
                                y: { title: { display: true, text: 'BAC (g/L)', color: '#475569' }, beginAtZero: true, ticks: { color: '#475569' } }
                            }
                        }
                    });
                }
            };

            app.init();
        });
    </script>
</body>
</html>
