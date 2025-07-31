<!DOCTYPE html>
<html lang="it" dir="ltr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title data-lang-key="pageTitle">Guida Sicura: Alcoltest Interattivo</title>
    <meta name="google-adsense-account" content="ca-pub-8268426852108056">
    <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-8268426852108056"
     crossorigin="anonymous"></script>
    <!-- ads.txt content: google.com, pub-8268426852108056, DIRECT, f08c4Tfec0942fa0 -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');
        @import url('https://fonts.googleapis.com/css2?family=Cairo:wght@400;500;600;700&display=swap'); /* For Arabic */

        body { font-family: 'Inter', sans-serif; background-color: #fef2f2; color: #334155; }
        [dir="rtl"] body { font-family: 'Cairo', sans-serif; text-align: right; }

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
        details summary .arrow { transition: transform 0.2s; display: inline-block; }
        details[open] summary .arrow { transform: rotate(90deg); }

        /* RTL Specific Styles */
        [dir="rtl"] details[open] summary .arrow { transform: rotate(-90deg); }
        [dir="rtl"] .arrow { transform: scaleX(-1); }
        [dir="rtl"] .space-x-2 { --tw-space-x-reverse: 1; }
        [dir="rtl"] .border-l-4 {
            border-left-width: 0px;
            border-right-width: 4px;
        }
        [dir="rtl"] .rounded-r-lg {
            border-top-right-radius: 0;
            border-bottom-right-radius: 0;
            border-top-left-radius: 0.5rem;
            border-bottom-left-radius: 0.5rem;
        }
    </style>
</head>
<body class="antialiased">

    <div class="container mx-auto p-4 sm:p-6 lg:p-8 max-w-7xl">
        
        <header class="text-center mb-8">
            <div class="flex justify-center items-center mb-4">
                 <select id="language-selector" class="bg-white border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-red-500 focus:border-red-500 block p-2.5">
                    <option value="it">Italiano</option>
                    <option value="en">English</option>
                    <option value="fr">Français</option>
                    <option value="de">Deutsch</option>
                    <option value="es">Español</option>
                    <option value="ro">Română</option>
                    <option value="sq">Shqip</option>
                    <option value="ru">Русский</option>
                    <option value="ar">العربية</option>
                </select>
            </div>
            <h1 class="text-4xl md:text-5xl font-bold text-slate-800" data-lang-key="mainTitle">Guida Sicura: Alcoltest Interattivo</h1>
            <p class="mt-2 text-lg text-slate-600" data-lang-key="tagline">Simula il tuo tasso alcolemico per una guida più consapevole.</p>
        </header>

        <main>
            <div class="w-full max-w-4xl mx-auto bg-white rounded-2xl shadow-lg border border-gray-200">
                <nav class="flex border-b border-gray-200">
                    <button data-tab="simulatore" class="tab-btn flex-1 p-4 font-semibold text-gray-600 border-b-2 border-transparent hover:bg-red-50 active" data-lang-key="tabSimulator">Simulatore</button>
                    <button data-tab="informazioni" class="tab-btn flex-1 p-4 font-semibold text-gray-600 border-b-2 border-transparent hover:bg-red-50" data-lang-key="tabInformation">Informazioni</button>
                    <button data-tab="fattori" class="tab-btn flex-1 p-4 font-semibold text-gray-600 border-b-2 border-transparent hover:bg-red-50" data-lang-key="tabFactors">Fattori Chiave</button>
                </nav>

                <div class="p-6 sm:p-8">
                    <!-- Simulatore Tab -->
                    <div id="simulatore" class="tab-content active">
                        <div class="text-center mb-8">
                            <h2 class="text-2xl font-bold text-slate-800" data-lang-key="createSimulationTitle">Crea la tua Simulazione</h2>
                            <p class="mt-2 text-slate-600" data-lang-key="createSimulationDescription">Inserisci i tuoi dati e le bevande consumate per ottenere una stima del tuo tasso alcolemico (BAC) e del suo andamento nel tempo.</p>
                        </div>

                        <div class="space-y-8">
                            <!-- Step 1: Dati Personali -->
                            <div>
                                <h3 class="text-lg font-semibold mb-4 border-b pb-2 text-slate-700" data-lang-key="step1Title">1. Dati Personali</h3>
                                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                                    <div>
                                        <label class="block text-sm font-medium mb-2" data-lang-key="labelSex">Sesso Biologico</label>
                                        <div class="flex space-x-2">
                                            <input type="radio" id="sesso_m" name="sesso" value="M" class="form-radio hidden" checked>
                                            <label for="sesso_m" class="flex-1 text-center p-3 border border-gray-300 rounded-lg cursor-pointer hover:bg-red-50" data-lang-key="sexMale">Uomo</label>
                                            <input type="radio" id="sesso_f" name="sesso" value="F" class="form-radio hidden">
                                            <label for="sesso_f" class="flex-1 text-center p-3 border border-gray-300 rounded-lg cursor-pointer hover:bg-red-50" data-lang-key="sexFemale">Donna</label>
                                        </div>
                                    </div>
                                    <div>
                                        <label for="peso" class="block text-sm font-medium mb-2" data-lang-key="labelWeight">Peso (kg)</label>
                                        <input type="number" id="peso" min="30" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-red-500 focus:border-red-500" data-lang-key-placeholder="placeholderWeight">
                                    </div>
                                    <div class="md:col-span-2">
                                        <label class="block text-sm font-medium mb-2" data-lang-key="labelConsumption">Consumazione</label>
                                        <div class="flex space-x-2">
                                            <input type="radio" id="pasto_pieno" name="pasto" value="pieno" class="form-radio hidden" checked>
                                            <label for="pasto_pieno" class="flex-1 text-center p-3 border border-gray-300 rounded-lg cursor-pointer hover:bg-red-50" data-lang-key="stomachFull">A stomaco pieno</label>
                                            <input type="radio" id="pasto_vuoto" name="pasto" value="vuoto" class="form-radio hidden">
                                            <label for="pasto_vuoto" class="flex-1 text-center p-3 border border-gray-300 rounded-lg cursor-pointer hover:bg-red-50" data-lang-key="stomachEmpty">A stomaco vuoto</label>
                                        </div>
                                    </div>
                                </div>
                            </div>

                            <!-- Step 2: Bevande -->
                            <div>
                                <h3 class="text-lg font-semibold mb-4 border-b pb-2 text-slate-700" data-lang-key="step2Title">2. Bevande Consumate</h3>
                                <div id="bevande-container" class="space-y-3 mb-4 min-h-[80px] flex items-center justify-center">
                                    <p id="bevande-placeholder" class="text-slate-500" data-lang-key="drinksPlaceholder">Aggiungi una bevanda per iniziare.</p>
                                </div>
                                <button id="btn-aggiungi" class="w-full p-3 bg-red-100 text-red-800 font-semibold rounded-lg hover:bg-red-200 transition-colors" data-lang-key="btnAddDrink">Aggiungi Bevanda</button>
                            </div>

                            <!-- Step 3: Tempo -->
                            <div>
                                <h3 class="text-lg font-semibold mb-4 border-b pb-2 text-slate-700" data-lang-key="step3Title">3. Tempo Trascorso</h3>
                                <label for="ore" class="block text-sm font-medium"><span data-lang-key="timeElapsedLabel">Ore dalla fine della consumazione:</span> <span id="ore-valore" class="font-bold text-red-600">1</span></label>
                                <input type="range" id="ore" min="0" max="24" value="1" class="w-full h-2 bg-gray-200 rounded-lg appearance-none cursor-pointer mt-2 accent-red-500">
                            </div>
                        </div>

                        <div class="mt-8 grid grid-cols-2 gap-4">
                            <button id="btn-reset" class="w-full p-4 bg-slate-200 text-slate-800 font-bold text-lg rounded-lg hover:bg-slate-300 transition-colors" data-lang-key="btnReset">Reset</button>
                            <button id="btn-calcola" class="w-full p-4 bg-red-600 text-white font-bold text-lg rounded-lg hover:bg-red-700 transition-colors" data-lang-key="btnCalculate">Calcola</button>
                        </div>
                        
                        <div id="error-message" class="hidden mt-4 p-4 bg-red-100 text-red-800 rounded-lg text-center font-semibold"></div>

                        <!-- Risultati -->
                        <div id="risultato-container" class="hidden mt-12">
                            <div class="text-center mb-8">
                                <h2 class="text-3xl font-bold text-slate-800" data-lang-key="resultsTitle">Il Tuo Risultato Stimato</h2>
                            </div>
                            <div class="bg-slate-50 p-6 rounded-xl border">
                                <div class="text-center mb-6">
                                    <p class="text-lg text-slate-600" data-lang-key="resultsCurrentBac">Tasso Alcolemico Attuale (BAC)</p>
                                    <p id="bac-valore" class="text-7xl font-bold my-2">0.00</p>
                                    <p class="text-lg text-slate-600">g/L</p>
                                    <p id="interpretazione" class="mt-4 p-3 rounded-lg font-semibold text-lg"></p>
                                </div>
                                
                                <div id="tempo-guida-container" class="hidden mt-4 pt-4 border-t border-slate-200 text-center">
                                    <p id="tempo-guida-label" class="text-lg text-slate-600"></p>
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
                            <h2 class="text-2xl font-bold text-slate-800" data-lang-key="infoTitle">Come Funziona e Cosa Significa</h2>
                            <p class="mt-2 text-slate-600" data-lang-key="infoDescription">Questa simulazione si basa sulla formula di Widmark, un metodo scientifico per stimare la concentrazione di alcol nel sangue. Scopri di più sugli effetti del BAC e i limiti legali.</p>
                        </div>
                        <div class="p-6 bg-slate-50 rounded-lg border">
                            <h3 class="text-xl font-semibold mb-2 text-slate-700" data-lang-key="widmarkTitle">La Formula di Widmark</h3>
                            <p class="text-slate-700" data-lang-key="widmarkDescription">Il calcolo stima il BAC massimo dividendo i grammi di alcol ingeriti per la massa corporea moltiplicata per un coefficiente di diffusione specifico per sesso e condizione di pasto. Successivamente, sottrae l'alcol smaltito dal corpo nel tempo (circa 0.15 g/L all'ora).</p>
                        </div>
                        <div class="p-6 bg-slate-50 rounded-lg border">
                            <h3 class="text-xl font-semibold mb-2 text-slate-700" data-lang-key="effectsTitle">Effetti del Tasso Alcolemico (BAC)</h3>
                            <table class="w-full mt-4 text-left">
                                <thead class="bg-slate-200">
                                    <tr>
                                        <th class="p-3 font-semibold text-slate-700" data-lang-key="tableHeaderBac">BAC (g/L)</th>
                                        <th class="p-3 font-semibold text-slate-700" data-lang-key="tableHeaderEffects">Effetti Comuni</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr class="border-b"><td class="p-3 font-mono">0.1 - 0.2</td><td class="p-3" data-lang-key="effect1">Leggera euforia, sensazione di calore.</td></tr>
                                    <tr class="border-b bg-slate-50"><td class="p-3 font-mono">0.3 - 0.4</td><td class="p-3" data-lang-key="effect2">Riflessi diminuiti, minore percezione del rischio.</td></tr>
                                    <tr class="border-b"><td class="p-3 font-mono text-amber-600 font-bold">0.5</td><td class="p-3 text-amber-600 font-bold" data-lang-key="effect3">Limite legale per la guida. Alterazione della coordinazione.</td></tr>
                                    <tr class="border-b bg-slate-50"><td class="p-3 font-mono text-red-600 font-bold">0.8</td><td class="p-3 text-red-600 font-bold" data-lang-key="effect4">Stato di ebbrezza. Visione offuscata, reazioni lente.</td></tr>
                                    <tr class="border-b"><td class="p-3 font-mono text-red-700 font-bold">1.5+</td><td class="p-3 text-red-700 font-bold" data-lang-key="effect5">Grave intossicazione, rischio di perdita di coscienza.</td></tr>
                                </tbody>
                            </table>
                        </div>
                    </div>

                    <!-- Fattori Chiave Tab -->
                    <div id="fattori" class="tab-content space-y-6">
                         <div class="text-center mb-8">
                            <h2 class="text-2xl font-bold text-slate-800" data-lang-key="factorsTitle">Cosa Influenza il Tuo BAC</h2>
                            <p class="mt-2 text-slate-600" data-lang-key="factorsDescription">Il tasso alcolemico non dipende solo da quanto bevi. Diversi fattori personali giocano un ruolo cruciale nell'assorbimento e nello smaltimento dell'alcol.</p>
                        </div>
                        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                            <div class="p-6 bg-slate-50 rounded-lg border">
                                <h3 class="text-xl font-semibold mb-2 text-slate-700" data-lang-key="factorSexTitle">Sesso Biologico</h3>
                                <p class="text-slate-700" data-lang-key="factorSexDescription">Le donne hanno generalmente una minore percentuale di acqua corporea e diversi livelli enzimatici rispetto agli uomini, portando a un BAC più elevato a parità di alcol consumato.</p>
                            </div>
                            <div class="p-6 bg-slate-50 rounded-lg border">
                                <h3 class="text-xl font-semibold mb-2 text-slate-700" data-lang-key="factorWeightTitle">Peso Corporeo</h3>
                                <p class="text-slate-700" data-lang-key="factorWeightDescription">L'alcol si distribuisce nell'acqua corporea. Una persona con un peso maggiore ha una massa più grande in cui diluire l'alcol, risultando in un BAC inferiore.</p>
                            </div>
                            <div class="p-6 bg-slate-50 rounded-lg border">
                                <h3 class="text-xl font-semibold mb-2 text-slate-700" data-lang-key="factorFoodTitle">Cibo nello Stomaco</h3>
                                <p class="text-slate-700" data-lang-key="factorFoodDescription">Consumare alcol a stomaco pieno rallenta il suo assorbimento nel flusso sanguigno, portando a un picco di BAC più basso e ritardato rispetto al consumo a stomaco vuoto.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <footer class="text-center mt-12 space-y-4">
                <div class="max-w-4xl mx-auto p-4 bg-amber-100 border-l-4 border-amber-500 rounded-r-lg">
                    <p class="text-amber-800 text-base"><strong data-lang-key="disclaimerTitle">⚠️ DISCLAIMER:</strong> <span data-lang-key="disclaimerText">Questo strumento fornisce solo una stima a scopo educativo. Non sostituisce un etilometro professionale. Il BAC reale può variare. Non guidare se hai bevuto.</span></p>
                </div>
                
                <div class="max-w-4xl mx-auto text-left">
                    <details class="bg-slate-50 p-4 rounded-lg border">
                        <summary class="font-semibold text-slate-700 cursor-pointer flex justify-between items-center">
                            <span data-lang-key="privacyTitle">Leggi l'informativa sulla privacy</span>
                            <span class="arrow text-red-600">▶</span>
                        </summary>
                        <div class="mt-4 pt-4 border-t space-y-4 text-slate-700">
                             <div>
                                <h3 class="text-lg font-semibold mb-2 text-slate-700" data-lang-key="privacy1Title">Nessuna Raccolta Dati</h3>
                                <p data-lang-key="privacy1Text">Questo strumento è progettato per garantire il completo anonimato. <strong>Non raccogliamo, salviamo, né trasmettiamo alcun dato personale</strong> inserito nel simulatore (sesso, peso, consumazioni, ecc.).</p>
                            </div>
                            <div>
                                <h3 class="text-lg font-semibold mb-2 text-slate-700" data-lang-key="privacy2Title">Elaborazione Esclusivamente Locale</h3>
                                <p data-lang-key="privacy2Text">Tutti i calcoli necessari per stimare il tasso alcolemico avvengono <strong>esclusivamente all'interno del tuo browser</strong> (client-side). Le informazioni che inserisci non lasciano mai il tuo dispositivo e non raggiungono mai i nostri server.</p>
                            </div>
                             <div>
                                <h3 class="text-lg font-semibold mb-2 text-slate-700" data-lang-key="privacy3Title">Nessun Tracciamento delle Abitudini</h3>
                                <p data-lang-key="privacy3Text">Non utilizziamo cookie di profilazione o altre tecnologie di tracciamento per analizzare le tue abitudini o il tuo comportamento. L'uso dello strumento è volatile: una volta chiusa la pagina, ogni informazione inserita viene eliminata definitivamente.</p>
                            </div>
                             <div>
                                <h3 class="text-lg font-semibold mb-2 text-slate-700" data-lang-key="privacy4Title">Scopo Educativo</h3>
                                <p data-lang-key="privacy4Text">Lo scopo di questo strumento è puramente educativo e informativo. È stato creato per aumentare la consapevolezza sui fattori che influenzano il tasso alcolemico e sui rischi della guida in stato di ebbrezza, nel pieno rispetto della privacy dell'utente.</p>
                            </div>
                             <div>
                                <h3 class="text-lg font-semibold mb-2 text-slate-700" data-lang-key="privacy5Title">Contatti</h3>
                                <p><span data-lang-key="privacy5Text">Per qualsiasi informazione o comunicazione riguardo la privacy, puoi scrivere a:</span> <a href="mailto:luminaessenza1@gmail.com" class="text-red-600 hover:underline">luminaessenza1@gmail.com</a></p>
                            </div>
                        </div>
                    </details>
                </div>

                <div class="text-sm text-gray-500">
                    <p data-lang-key="copyright">Copyright © 2025 Nicola Nicolaci. Tutti i diritti riservati.</p>
                </div>
            </footer>
        </main>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const app = {
                bevandaCounter: 0,
                bacChart: null,
                currentLanguage: 'it',
                lastResultData: null,
                
                // All translations are stored here
                translations: {
                    // Italian
                    it: {
                        pageTitle: "Guida Sicura: Alcoltest Interattivo", mainTitle: "Guida Sicura: Alcoltest Interattivo", tagline: "Simula il tuo tasso alcolemico per una guida più consapevole.", tabSimulator: "Simulatore", tabInformation: "Informazioni", tabFactors: "Fattori Chiave", createSimulationTitle: "Crea la tua Simulazione", createSimulationDescription: "Inserisci i tuoi dati e le bevande consumate per ottenere una stima del tuo tasso alcolemico (BAC) e del suo andamento nel tempo.", step1Title: "1. Dati Personali", labelSex: "Sesso Biologico", sexMale: "Uomo", sexFemale: "Donna", labelWeight: "Peso (kg)", placeholderWeight: "Es. 75", labelConsumption: "Consumazione", stomachFull: "A stomaco pieno", stomachEmpty: "A stomaco vuoto", step2Title: "2. Bevande Consumate", drinksPlaceholder: "Aggiungi una bevanda per iniziare.", btnAddDrink: "Aggiungi Bevanda", step3Title: "3. Tempo Trascorso", timeElapsedLabel: "Ore dalla fine della consumazione:", btnReset: "Reset", btnCalculate: "Calcola", errorWeight: "Per favore, inserisci un peso valido (> 30 kg).", errorNoDrinks: "Aggiungi almeno una bevanda.", errorCustomDrink: "Per le bevande personalizzate, inserisci volume e gradazione validi.", errorQuantity: "Inserisci una quantità valida per le bevande.", errorNoAlcohol: "Nessun alcol consumato.", resultsTitle: "Il Tuo Risultato Stimato", resultsCurrentBac: "Tasso Alcolemico Attuale (BAC)", interpretationSafe: "Sotto il limite legale. La prudenza è sempre d'obbligo.", interpretationWarning: "SOPRA IL LIMITE LEGALE. NON GUIDARE.", interpretationDanger: "STATO DI EBBREZZA. Rischio elevato. NON GUIDARE.", timeToDriveLabel: "Tempo stimato per tornare sotto il limite:", timeToDriveSoon: "A breve sotto il limite", timeToDriveFormat: "Circa {hours} ore e {minutes} minuti", timeToDriveSafe: "Puoi guidare in sicurezza", timeToDriveStatus: "Stato attuale:", chartTitle: "Andamento Stimato del BAC nel Tempo", chartLabelBac: "Tasso Alcolemico (g/L)", chartLabelHours: "Ore dalla fine della consumazione", chartLabelLegalLimit: "Limite Legale (0.5 g/L)", chartTooltipCurrent: "Stima attuale.", infoTitle: "Come Funziona e Cosa Significa", infoDescription: "Questa simulazione si basa sulla formula di Widmark, un metodo scientifico per stimare la concentrazione di alcol nel sangue. Scopri di più sugli effetti del BAC e i limiti legali.", widmarkTitle: "La Formula di Widmark", widmarkDescription: "Il calcolo stima il BAC massimo dividendo i grammi di alcol ingeriti per la massa corporea moltiplicata per un coefficiente di diffusione specifico per sesso e condizione di pasto. Successivamente, sottrae l'alcol smaltito dal corpo nel tempo (circa 0.15 g/L all'ora).", effectsTitle: "Effetti del Tasso Alcolemico (BAC)", tableHeaderBac: "BAC (g/L)", tableHeaderEffects: "Effetti Comuni", effect1: "Leggera euforia, sensazione di calore.", effect2: "Riflessi diminuiti, minore percezione del rischio.", effect3: "Limite legale per la guida. Alterazione della coordinazione.", effect4: "Stato di ebbrezza. Visione offuscata, reazioni lente.", effect5: "Grave intossicazione, rischio di perdita di coscienza.", factorsTitle: "Cosa Influenza il Tuo BAC", factorsDescription: "Il tasso alcolemico non dipende solo da quanto bevi. Diversi fattori personali giocano un ruolo cruciale nell'assorbimento e nello smaltimento dell'alcol.", factorSexTitle: "Sesso Biologico", factorSexDescription: "Le donne hanno generalmente una minore percentuale di acqua corporea e diversi livelli enzimatici rispetto agli uomini, portando a un BAC più elevato a parità di alcol consumato.", factorWeightTitle: "Peso Corporeo", factorWeightDescription: "L'alcol si distribuisce nell'acqua corporea. Una persona con un peso maggiore ha una massa più grande in cui diluire l'alcol, risultando in un BAC inferiore.", factorFoodTitle: "Cibo nello Stomaco", factorFoodDescription: "Consumare alcol a stomaco pieno rallenta il suo assorbimento nel flusso sanguigno, portando a un picco di BAC più basso e ritardato rispetto al consumo a stomaco vuoto.", disclaimerTitle: "⚠️ DISCLAIMER:", disclaimerText: "Questo strumento fornisce solo una stima a scopo educativo. Non sostituisce un etilometro professionale. Il BAC reale può variare. Non guidare se hai bevuto.", privacyTitle: "Leggi l'informativa sulla privacy", privacy1Title: "Nessuna Raccolta Dati", privacy1Text: "Questo strumento è progettato per garantire il completo anonimato. <strong>Non raccogliamo, salviamo, né trasmettiamo alcun dato personale</strong> inserito nel simulatore (sesso, peso, consumazioni, ecc.).", privacy2Title: "Elaborazione Esclusivamente Locale", privacy2Text: "Tutti i calcoli necessari per stimare il tasso alcolemico avvengono <strong>esclusivamente all'interno del tuo browser</strong> (client-side). Le informazioni che inserisci non lasciano mai il tuo dispositivo e non raggiungono mai i nostri server.", privacy3Title: "Nessun Tracciamento delle Abitudini", privacy3Text: "Non utilizziamo cookie di profilazione o altre tecnologie di tracciamento per analizzare le tue abitudini o il tuo comportamento. L'uso dello strumento è volatile: una volta chiusa la pagina, ogni informazione inserita viene eliminata definitivamente.", privacy4Title: "Scopo Educativo", privacy4Text: "Lo scopo di questo strumento è puramente educativo e informativo. È stato creato per aumentare la consapevolezza sui fattori che influenzano il tasso alcolemico e sui rischi della guida in stato di ebbrezza, nel pieno rispetto della privacy dell'utente.", privacy5Title: "Contatti", privacy5Text: "Per qualsiasi informazione o comunicazione riguardo la privacy, puoi scrivere a:", copyright: "Copyright © 2025 Nicola Nicolaci. Tutti i diritti riservati."
                    },
                    // English
                    en: {
                        pageTitle: "Safe Driving: Interactive BAC Test", mainTitle: "Safe Driving: Interactive BAC Test", tagline: "Simulate your blood alcohol content for more conscious driving.", tabSimulator: "Simulator", tabInformation: "Information", tabFactors: "Key Factors", createSimulationTitle: "Create Your Simulation", createSimulationDescription: "Enter your data and the drinks consumed to get an estimate of your blood alcohol content (BAC) and its trend over time.", step1Title: "1. Personal Data", labelSex: "Biological Sex", sexMale: "Male", sexFemale: "Female", labelWeight: "Weight (kg)", placeholderWeight: "E.g. 75", labelConsumption: "Consumption", stomachFull: "On a full stomach", stomachEmpty: "On an empty stomach", step2Title: "2. Drinks Consumed", drinksPlaceholder: "Add a drink to get started.", btnAddDrink: "Add Drink", step3Title: "3. Time Elapsed", timeElapsedLabel: "Hours since last drink:", btnReset: "Reset", btnCalculate: "Calculate", errorWeight: "Please enter a valid weight (> 30 kg).", errorNoDrinks: "Add at least one drink.", errorCustomDrink: "For custom drinks, please enter valid volume and ABV.", errorQuantity: "Please enter a valid quantity for the drinks.", errorNoAlcohol: "No alcohol consumed.", resultsTitle: "Your Estimated Result", resultsCurrentBac: "Current Blood Alcohol Content (BAC)", interpretationSafe: "Below the legal limit. Caution is always advised.", interpretationWarning: "ABOVE THE LEGAL LIMIT. DO NOT DRIVE.", interpretationDanger: "STATE OF INTOXICATION. High risk. DO NOT DRIVE.", timeToDriveLabel: "Estimated time to get back under the limit:", timeToDriveSoon: "Soon under the limit", timeToDriveFormat: "About {hours} hours and {minutes} minutes", timeToDriveSafe: "You can drive safely", timeToDriveStatus: "Current status:", chartTitle: "Estimated BAC Trend Over Time", chartLabelBac: "Blood Alcohol Content (g/L)", chartLabelHours: "Hours since last drink", chartLabelLegalLimit: "Legal Limit (0.5 g/L)", chartTooltipCurrent: "Current estimate.", infoTitle: "How It Works and What It Means", infoDescription: "This simulation is based on the Widmark formula, a scientific method for estimating blood alcohol concentration. Learn more about the effects of BAC and legal limits.", widmarkTitle: "The Widmark Formula", widmarkDescription: "The calculation estimates the peak BAC by dividing the grams of alcohol consumed by body mass multiplied by a diffusion coefficient specific to sex and meal status. It then subtracts the alcohol metabolized by the body over time (about 0.15 g/L per hour).", effectsTitle: "Effects of Blood Alcohol Content (BAC)", tableHeaderBac: "BAC (g/L)", tableHeaderEffects: "Common Effects", effect1: "Slight euphoria, feeling of warmth.", effect2: "Decreased reflexes, lower risk perception.", effect3: "Legal limit for driving. Impaired coordination.", effect4: "State of intoxication. Blurred vision, slow reactions.", effect5: "Severe intoxication, risk of unconsciousness.", factorsTitle: "What Influences Your BAC", factorsDescription: "Blood alcohol content doesn't just depend on how much you drink. Several personal factors play a crucial role in alcohol absorption and metabolism.", factorSexTitle: "Biological Sex", factorSexDescription: "Women generally have a lower percentage of body water and different enzyme levels than men, leading to a higher BAC for the same amount of alcohol consumed.", factorWeightTitle: "Body Weight", factorWeightDescription: "Alcohol is distributed in body water. A person with a higher weight has more mass to dilute the alcohol, resulting in a lower BAC.", factorFoodTitle: "Food in Stomach", factorFoodDescription: "Consuming alcohol on a full stomach slows its absorption into the bloodstream, leading to a lower and delayed BAC peak compared to drinking on an empty stomach.", disclaimerTitle: "⚠️ DISCLAIMER:", disclaimerText: "This tool provides an estimate for educational purposes only. It does not replace a professional breathalyzer. Actual BAC may vary. Do not drive if you have been drinking.", privacyTitle: "Read the privacy policy", privacy1Title: "No Data Collection", privacy1Text: "This tool is designed to ensure complete anonymity. <strong>We do not collect, save, or transmit any personal data</strong> entered in the simulator (sex, weight, drinks, etc.).", privacy2Title: "Exclusively Local Processing", privacy2Text: "All calculations needed to estimate blood alcohol content occur <strong>exclusively within your browser</strong> (client-side). The information you enter never leaves your device and never reaches our servers.", privacy3Title: "No Habit Tracking", privacy3Text: "We do not use profiling cookies or other tracking technologies to analyze your habits or behavior. The use of the tool is volatile: once you close the page, all entered information is permanently deleted.", privacy4Title: "Educational Purpose", privacy4Text: "The purpose of this tool is purely educational and informational. It was created to raise awareness about the factors influencing blood alcohol content and the risks of drunk driving, while fully respecting user privacy.", privacy5Title: "Contact", privacy5Text: "For any information or communication regarding privacy, you can write to:", copyright: "Copyright © 2025 Nicola Nicolaci. All rights reserved."
                    },
                    // French
                    fr: {
                        pageTitle: "Conduite Sûre : Alcootest Interactif", mainTitle: "Conduite Sûre : Alcootest Interactif", tagline: "Simulez votre taux d'alcoolémie pour une conduite plus consciente.", tabSimulator: "Simulateur", tabInformation: "Informations", tabFactors: "Facteurs Clés", createSimulationTitle: "Créez votre simulation", createSimulationDescription: "Entrez vos données et les boissons consommées pour obtenir une estimation de votre taux d'alcoolémie (TAS) et de son évolution dans le temps.", step1Title: "1. Données Personnelles", labelSex: "Sexe Biologique", sexMale: "Homme", sexFemale: "Femme", labelWeight: "Poids (kg)", placeholderWeight: "Ex. 75", labelConsumption: "Consommation", stomachFull: "Estomac plein", stomachEmpty: "Estomac vide", step2Title: "2. Boissons Consommées", drinksPlaceholder: "Ajoutez une boisson pour commencer.", btnAddDrink: "Ajouter une boisson", step3Title: "3. Temps Écoulé", timeElapsedLabel: "Heures depuis la dernière consommation :", btnReset: "Réinitialiser", btnCalculate: "Calculer", errorWeight: "Veuillez entrer un poids valide (> 30 kg).", errorNoDrinks: "Ajoutez au moins une boisson.", errorCustomDrink: "Pour les boissons personnalisées, veuillez entrer un volume et un degré d'alcool valides.", errorQuantity: "Veuillez entrer une quantité valide pour les boissons.", errorNoAlcohol: "Pas d'alcool consommé.", resultsTitle: "Votre Résultat Estimé", resultsCurrentBac: "Taux d'Alcoolémie Actuel (TAS)", interpretationSafe: "En dessous de la limite légale. La prudence est toujours de mise.", interpretationWarning: "AU-DESSUS DE LA LIMITE LÉGALE. NE CONDUISEZ PAS.", interpretationDanger: "ÉTAT D'IVRESSE. Risque élevé. NE CONDUISEZ PAS.", timeToDriveLabel: "Temps estimé pour repasser sous la limite :", timeToDriveSoon: "Bientôt sous la limite", timeToDriveFormat: "Environ {hours} heures et {minutes} minutes", timeToDriveSafe: "Vous pouvez conduire en toute sécurité", timeToDriveStatus: "État actuel :", chartTitle: "Évolution Estimée du TAS dans le Temps", chartLabelBac: "Taux d'Alcoolémie (g/L)", chartLabelHours: "Heures depuis la dernière consommation", chartLabelLegalLimit: "Limite Légale (0.5 g/L)", chartTooltipCurrent: "Estimation actuelle.", infoTitle: "Comment ça marche et ce que ça signifie", infoDescription: "Cette simulation est basée sur la formule de Widmark, une méthode scientifique pour estimer la concentration d'alcool dans le sang. Apprenez-en plus sur les effets du TAS et les limites légales.", widmarkTitle: "La Formule de Widmark", widmarkDescription: "Le calcul estime le pic de TAS en divisant les grammes d'alcool ingérés par la masse corporelle multipliée par un coefficient de diffusion spécifique au sexe et à l'état du repas. Il soustrait ensuite l'alcool métabolisé par le corps au fil du temps (environ 0,15 g/L par heure).", effectsTitle: "Effets du Taux d'Alcoolémie (TAS)", tableHeaderBac: "TAS (g/L)", tableHeaderEffects: "Effets Courants", effect1: "Légère euphorie, sensation de chaleur.", effect2: "Réflexes diminués, perception du risque plus faible.", effect3: "Limite légale pour la conduite. Coordination altérée.", effect4: "État d'ivresse. Vision floue, réactions lentes.", effect5: "Intoxication sévère, risque de perte de conscience.", factorsTitle: "Ce qui influence votre TAS", factorsDescription: "Le taux d'alcoolémie ne dépend pas seulement de la quantité que vous buvez. Plusieurs facteurs personnels jouent un rôle crucial dans l'absorption et l'élimination de l'alcool.", factorSexTitle: "Sexe Biologique", factorSexDescription: "Les femmes ont généralement un pourcentage d'eau corporelle plus faible et des niveaux d'enzymes différents de ceux des hommes, ce qui entraîne un TAS plus élevé pour la même quantité d'alcool consommée.", factorWeightTitle: "Poids Corporel", factorWeightDescription: "L'alcool est distribué dans l'eau corporelle. Une personne plus lourde a une plus grande masse pour diluer l'alcool, ce qui se traduit par un TAS plus faible.", factorFoodTitle: "Nourriture dans l'Estomac", factorFoodDescription: "Consommer de l'alcool l'estomac plein ralentit son absorption dans la circulation sanguine, entraînant un pic de TAS plus bas et retardé par rapport à la consommation à jeun.", disclaimerTitle: "⚠️ AVERTISSEMENT :", disclaimerText: "Cet outil ne fournit qu'une estimation à des fins éducatives. Il ne remplace pas un alcootest professionnel. Le TAS réel peut varier. Ne conduisez pas si vous avez bu.", privacyTitle: "Lire la politique de confidentialité", privacy1Title: "Aucune Collecte de Données", privacy1Text: "Cet outil est conçu pour garantir un anonymat complet. <strong>Nous ne collectons, ne sauvegardons ni ne transmettons aucune donnée personnelle</strong> saisie dans le simulateur (sexe, poids, boissons, etc.).", privacy2Title: "Traitement Exclusivement Local", privacy2Text: "Tous les calculs nécessaires pour estimer le taux d'alcoolémie ont lieu <strong>exclusivement dans votre navigateur</strong> (côté client). Les informations que vous saisissez ne quittent jamais votre appareil et n'atteignent jamais nos serveurs.", privacy3Title: "Aucun Suivi des Habitudes", privacy3Text: "Nous n'utilisons pas de cookies de profilage ou d'autres technologies de suivi pour analyser vos habitudes ou votre comportement. L'utilisation de l'outil est volatile : une fois la page fermée, toutes les informations saisies sont définitivement supprimées.", privacy4Title: "But Éducatif", privacy4Text: "Le but de cet outil est purement éducatif et informatif. Il a été créé pour sensibiliser aux facteurs qui influencent le taux d'alcoolémie et aux risques de la conduite en état d'ivresse, dans le respect total de la vie privée de l'utilisateur.", privacy5Title: "Contact", privacy5Text: "Pour toute information ou communication concernant la confidentialité, vous pouvez écrire à :", copyright: "Copyright © 2025 Nicola Nicolaci. Tous droits réservés."
                    },
                    // German
                    de: {
                        pageTitle: "Sicheres Fahren: Interaktiver BAK-Test", mainTitle: "Sicheres Fahren: Interaktiver BAK-Test", tagline: "Simulieren Sie Ihre Blutalkoholkonzentration für ein bewussteres Fahren.", tabSimulator: "Simulator", tabInformation: "Informationen", tabFactors: "Schlüsselfaktoren", createSimulationTitle: "Erstellen Sie Ihre Simulation", createSimulationDescription: "Geben Sie Ihre Daten und die konsumierten Getränke ein, um eine Schätzung Ihrer Blutalkoholkonzentration (BAK) und deren Verlauf zu erhalten.", step1Title: "1. Persönliche Daten", labelSex: "Biologisches Geschlecht", sexMale: "Männlich", sexFemale: "Weiblich", labelWeight: "Gewicht (kg)", placeholderWeight: "Z.B. 75", labelConsumption: "Konsum", stomachFull: "Auf vollen Magen", stomachEmpty: "Auf leeren Magen", step2Title: "2. Konsumierte Getränke", drinksPlaceholder: "Fügen Sie ein Getränk hinzu, um zu beginnen.", btnAddDrink: "Getränk hinzufügen", step3Title: "3. Verstrichene Zeit", timeElapsedLabel: "Stunden seit dem letzten Getränk:", btnReset: "Zurücksetzen", btnCalculate: "Berechnen", errorWeight: "Bitte geben Sie ein gültiges Gewicht ein (> 30 kg).", errorNoDrinks: "Fügen Sie mindestens ein Getränk hinzu.", errorCustomDrink: "Für benutzerdefinierte Getränke geben Sie bitte gültiges Volumen und Alkoholgehalt ein.", errorQuantity: "Bitte geben Sie eine gültige Menge für die Getränke ein.", errorNoAlcohol: "Kein Alkohol konsumiert.", resultsTitle: "Ihr geschätztes Ergebnis", resultsCurrentBac: "Aktuelle Blutalkoholkonzentration (BAK)", interpretationSafe: "Unter der gesetzlichen Grenze. Vorsicht ist immer geboten.", interpretationWarning: "ÜBER DER GESETZLICHEN GRENZE. NICHT FAHREN.", interpretationDanger: "RAUSCHZUSTAND. Hohes Risiko. NICHT FAHREN.", timeToDriveLabel: "Geschätzte Zeit, um wieder unter die Grenze zu kommen:", timeToDriveSoon: "Bald unter der Grenze", timeToDriveFormat: "Ungefähr {hours} Stunden und {minutes} Minuten", timeToDriveSafe: "Sie können sicher fahren", timeToDriveStatus: "Aktueller Status:", chartTitle: "Geschätzter BAK-Verlauf über die Zeit", chartLabelBac: "Blutalkoholkonzentration (g/L)", chartLabelHours: "Stunden seit dem letzten Getränk", chartLabelLegalLimit: "Gesetzliche Grenze (0.5 g/L)", chartTooltipCurrent: "Aktuelle Schätzung.", infoTitle: "Wie es funktioniert und was es bedeutet", infoDescription: "Diese Simulation basiert auf der Widmark-Formel, einer wissenschaftlichen Methode zur Schätzung der Blutalkoholkonzentration. Erfahren Sie mehr über die Auswirkungen von BAK und gesetzliche Grenzen.", widmarkTitle: "Die Widmark-Formel", widmarkDescription: "Die Berechnung schätzt den Spitzen-BAK, indem die Gramm des konsumierten Alkohols durch die Körpermasse geteilt werden, multipliziert mit einem Diffusionskoeffizienten, der für Geschlecht und Mahlzeitenstatus spezifisch ist. Anschließend wird der vom Körper im Laufe der Zeit metabolisierte Alkohol abgezogen (ca. 0,15 g/L pro Stunde).", effectsTitle: "Auswirkungen der Blutalkoholkonzentration (BAK)", tableHeaderBac: "BAK (g/L)", tableHeaderEffects: "Häufige Auswirkungen", effect1: "Leichte Euphorie, Wärmegefühl.", effect2: "Verringerte Reflexe, geringere Risikowahrnehmung.", effect3: "Gesetzliche Grenze für das Fahren. Beeinträchtigte Koordination.", effect4: "Rauschzustand. Verschwommenes Sehen, langsame Reaktionen.", effect5: "Schwere Vergiftung, Bewusstlosigkeitsrisiko.", factorsTitle: "Was Ihre BAK beeinflusst", factorsDescription: "Die Blutalkoholkonzentration hängt nicht nur davon ab, wie viel Sie trinken. Mehrere persönliche Faktoren spielen eine entscheidende Rolle bei der Alkoholaufnahme und -verstoffwechselung.", factorSexTitle: "Biologisches Geschlecht", factorSexDescription: "Frauen haben im Allgemeinen einen geringeren Körperwasseranteil und andere Enzymspiegel als Männer, was bei gleicher Alkoholmenge zu einer höheren BAK führt.", factorWeightTitle: "Körpergewicht", factorWeightDescription: "Alkohol verteilt sich im Körperwasser. Eine Person mit höherem Gewicht hat mehr Masse, um den Alkohol zu verdünnen, was zu einer niedrigeren BAK führt.", factorFoodTitle: "Nahrung im Magen", factorFoodDescription: "Der Konsum von Alkohol auf vollen Magen verlangsamt seine Aufnahme in den Blutkreislauf, was zu einem niedrigeren und verzögerten BAK-Peak im Vergleich zum Trinken auf leeren Magen führt.", disclaimerTitle: "⚠️ HAFTUNGSAUSSCHLUSS:", disclaimerText: "Dieses Tool dient nur zu Bildungszwecken. Es ersetzt keinen professionellen Alkoholtester. Die tatsächliche BAK kann variieren. Fahren Sie nicht, wenn Sie getrunken haben.", privacyTitle: "Lesen Sie die Datenschutzrichtlinie", privacy1Title: "Keine Datenerfassung", privacy1Text: "Dieses Tool wurde entwickelt, um vollständige Anonymität zu gewährleisten. <strong>Wir sammeln, speichern oder übertragen keine persönlichen Daten</strong>, die im Simulator eingegeben werden (Geschlecht, Gewicht, Getränke usw.).", privacy2Title: "Ausschließlich lokale Verarbeitung", privacy2Text: "Alle Berechnungen zur Schätzung der Blutalkoholkonzentration erfolgen <strong>ausschließlich in Ihrem Browser</strong> (clientseitig). Die von Ihnen eingegebenen Informationen verlassen niemals Ihr Gerät und erreichen niemals unsere Server.", privacy3Title: "Kein Verhaltens-Tracking", privacy3Text: "Wir verwenden keine Profiling-Cookies oder andere Tracking-Technologien, um Ihre Gewohnheiten oder Ihr Verhalten zu analysieren. Die Nutzung des Tools ist flüchtig: Sobald Sie die Seite schließen, werden alle eingegebenen Informationen endgültig gelöscht.", privacy4Title: "Bildungszweck", privacy4Text: "Der Zweck dieses Tools ist rein bildend und informativ. Es wurde geschaffen, um das Bewusstsein für die Faktoren zu schärfen, die die Blutalkoholkonzentration beeinflussen, und für die Risiken des Fahrens unter Alkoholeinfluss, unter voller Achtung der Privatsphäre der Benutzer.", privacy5Title: "Kontakt", privacy5Text: "Für Informationen oder Mitteilungen zum Datenschutz können Sie schreiben an:", copyright: "Copyright © 2025 Nicola Nicolaci. Alle Rechte vorbehalten."
                    },
                    // Spanish
                    es: {
                        pageTitle: "Conducción Segura: Test de Alcoholemia Interactivo", mainTitle: "Conducción Segura: Test de Alcoholemia Interactivo", tagline: "Simula tu tasa de alcoholemia para una conducción más consciente.", tabSimulator: "Simulador", tabInformation: "Información", tabFactors: "Factores Clave", createSimulationTitle: "Crea tu Simulación", createSimulationDescription: "Introduce tus datos y las bebidas consumidas para obtener una estimación de tu tasa de alcoholemia (BAC) y su evolución en el tiempo.", step1Title: "1. Datos Personales", labelSex: "Sexo Biológico", sexMale: "Hombre", sexFemale: "Mujer", labelWeight: "Peso (kg)", placeholderWeight: "Ej. 75", labelConsumption: "Consumo", stomachFull: "Con el estómago lleno", stomachEmpty: "Con el estómago vacío", step2Title: "2. Bebidas Consumidas", drinksPlaceholder: "Añade una bebida para empezar.", btnAddDrink: "Añadir Bebida", step3Title: "3. Tiempo Transcurrido", timeElapsedLabel: "Horas desde la última consumición:", btnReset: "Reiniciar", btnCalculate: "Calcular", errorWeight: "Por favor, introduce un peso válido (> 30 kg).", errorNoDrinks: "Añade al menos una bebida.", errorCustomDrink: "Para bebidas personalizadas, introduce un volumen y graduación válidos.", errorQuantity: "Introduce una cantidad válida para las bebidas.", errorNoAlcohol: "No se ha consumido alcohol.", resultsTitle: "Tu Resultado Estimado", resultsCurrentBac: "Tasa de Alcoholemia Actual (BAC)", interpretationSafe: "Por debajo del límite legal. Se recomienda siempre prudencia.", interpretationWarning: "POR ENCIMA DEL LÍMITE LEGAL. NO CONDUZCAS.", interpretationDanger: "ESTADO DE EMBRIAGUEZ. Riesgo elevado. NO CONDUZCAS.", timeToDriveLabel: "Tiempo estimado para volver a estar por debajo del límite:", timeToDriveSoon: "Pronto por debajo del límite", timeToDriveFormat: "Aproximadamente {hours} horas y {minutes} minutos", timeToDriveSafe: "Puedes conducir de forma segura", timeToDriveStatus: "Estado actual:", chartTitle: "Evolución Estimada del BAC en el Tiempo", chartLabelBac: "Tasa de Alcoholemia (g/L)", chartLabelHours: "Horas desde la última consumición", chartLabelLegalLimit: "Límite Legal (0.5 g/L)", chartTooltipCurrent: "Estimación actual.", infoTitle: "Cómo Funciona y Qué Significa", infoDescription: "Esta simulación se basa en la fórmula de Widmark, un método científico para estimar la concentración de alcohol en sangre. Aprende más sobre los efectos del BAC y los límites legales.", widmarkTitle: "La Fórmula de Widmark", widmarkDescription: "El cálculo estima el BAC máximo dividiendo los gramos de alcohol ingeridos por la masa corporal multiplicada por un coeficiente de difusión específico para el sexo y la condición de la comida. Posteriormente, resta el alcohol metabolizado por el cuerpo con el tiempo (aproximadamente 0.15 g/L por hora).", effectsTitle: "Efectos de la Tasa de Alcoholemia (BAC)", tableHeaderBac: "BAC (g/L)", tableHeaderEffects: "Efectos Comunes", effect1: "Ligera euforia, sensación de calor.", effect2: "Reflejos disminuidos, menor percepción del riesgo.", effect3: "Límite legal para conducir. Alteración de la coordinación.", effect4: "Estado de embriaguez. Visión borrosa, reacciones lentas.", effect5: "Intoxicación grave, riesgo de pérdida de conciencia.", factorsTitle: "Qué Influye en tu BAC", factorsDescription: "La tasa de alcoholemia no solo depende de cuánto bebas. Varios factores personales juegan un papel crucial en la absorción y eliminación del alcohol.", factorSexTitle: "Sexo Biológico", factorSexDescription: "Las mujeres generalmente tienen un menor porcentaje de agua corporal y diferentes niveles de enzimas que los hombres, lo que lleva a un BAC más alto con la misma cantidad de alcohol consumido.", factorWeightTitle: "Peso Corporal", factorWeightDescription: "El alcohol se distribuye en el agua corporal. Una persona con un peso mayor tiene una masa más grande en la que diluir el alcohol, lo que resulta en un BAC más bajo.", factorFoodTitle: "Comida en el Estómago", factorFoodDescription: "Consumir alcohol con el estómago lleno ralentiza su absorción en el torrente sanguíneo, lo que lleva a un pico de BAC más bajo y retardado en comparación con beber con el estómago vacío.", disclaimerTitle: "⚠️ AVISO:", disclaimerText: "Esta herramienta proporciona solo una estimación con fines educativos. No reemplaza a un alcoholímetro profesional. El BAC real puede variar. No conduzcas si has bebido.", privacyTitle: "Leer la política de privacidad", privacy1Title: "Sin Recopilación de Datos", privacy1Text: "Esta herramienta está diseñada para garantizar el anonimato total. <strong>No recopilamos, guardamos ni transmitimos ningún dato personal</strong> introducido en el simulador (sexo, peso, consumiciones, etc.).", privacy2Title: "Procesamiento Exclusivamente Local", privacy2Text: "Todos los cálculos necesarios para estimar la tasa de alcoholemia se realizan <strong>exclusivamente en tu navegador</strong> (lado del cliente). La información que introduces nunca abandona tu dispositivo y nunca llega a nuestros servidores.", privacy3Title: "Sin Seguimiento de Hábitos", privacy3Text: "No utilizamos cookies de perfilado ni otras tecnologías de seguimiento para analizar tus hábitos o tu comportamiento. El uso de la herramienta es volátil: una vez que cierras la página, toda la información introducida se elimina de forma permanente.", privacy4Title: "Propósito Educativo", privacy4Text: "El propósito de esta herramienta es puramente educativo e informativo. Fue creada para aumentar la conciencia sobre los factores que influyen en la tasa de alcoholemia y los riesgos de conducir ebrio, respetando plenamente la privacidad del usuario.", privacy5Title: "Contacto", privacy5Text: "Para cualquier información o comunicación sobre privacidad, puedes escribir a:", copyright: "Copyright © 2025 Nicola Nicolaci. Todos los derechos reservados."
                    },
                    // Romanian
                    ro: {
                        pageTitle: "Conducere Sigură: Test de Alcoolemie Interactiv", mainTitle: "Conducere Sigură: Test de Alcoolemie Interactiv", tagline: "Simulează-ți alcoolemia pentru o conducere mai conștientă.", tabSimulator: "Simulator", tabInformation: "Informații", tabFactors: "Factori Cheie", createSimulationTitle: "Creează-ți Simulare", createSimulationDescription: "Introdu datele tale și băuturile consumate pentru a obține o estimare a alcoolemiei (BAC) și evoluția acesteia în timp.", step1Title: "1. Date Personale", labelSex: "Sex Biologic", sexMale: "Bărbat", sexFemale: "Femeie", labelWeight: "Greutate (kg)", placeholderWeight: "Ex. 75", labelConsumption: "Consum", stomachFull: "Pe stomacul plin", stomachEmpty: "Pe stomacul gol", step2Title: "2. Băuturi Consumate", drinksPlaceholder: "Adaugă o băutură pentru a începe.", btnAddDrink: "Adaugă Băutură", step3Title: "3. Timp Trecut", timeElapsedLabel: "Ore de la ultimul consum:", btnReset: "Resetare", btnCalculate: "Calculează", errorWeight: "Te rugăm să introduci o greutate validă (> 30 kg).", errorNoDrinks: "Adaugă cel puțin o băutură.", errorCustomDrink: "Pentru băuturi personalizate, introdu un volum și o tărie valide.", errorQuantity: "Te rugăm să introduci o cantitate validă pentru băuturi.", errorNoAlcohol: "Niciun alcool consumat.", resultsTitle: "Rezultatul Tău Estimat", resultsCurrentBac: "Alcoolemia Curentă (BAC)", interpretationSafe: "Sub limita legală. Prudența este întotdeauna recomandată.", interpretationWarning: "PESTE LIMITA LEGALĂ. NU CONDUCE.", interpretationDanger: "STARE DE EBRIETATE. Risc ridicat. NU CONDUCE.", timeToDriveLabel: "Timp estimat pentru a reveni sub limită:", timeToDriveSoon: "În curând sub limită", timeToDriveFormat: "Aproximativ {hours} ore și {minutes} minute", timeToDriveSafe: "Poți conduce în siguranță", timeToDriveStatus: "Starea actuală:", chartTitle: "Evoluția Estimată a BAC în Timp", chartLabelBac: "Alcoolemie (g/L)", chartLabelHours: "Ore de la ultimul consum", chartLabelLegalLimit: "Limită Legală (0.5 g/L)", chartTooltipCurrent: "Estimare curentă.", infoTitle: "Cum Funcționează și Ce Înseamnă", infoDescription: "Această simulare se bazează pe formula Widmark, o metodă științifică pentru estimarea concentrației de alcool în sânge. Află mai multe despre efectele BAC și limitele legale.", widmarkTitle: "Formula Widmark", widmarkDescription: "Calculul estimează alcoolemia maximă împărțind gramele de alcool ingerate la masa corporală înmulțită cu un coeficient de difuzie specific sexului și stării de masă. Ulterior, scade alcoolul metabolizat de corp în timp (aproximativ 0.15 g/L pe oră).", effectsTitle: "Efectele Alcoolemiei (BAC)", tableHeaderBac: "BAC (g/L)", tableHeaderEffects: "Efecte Comune", effect1: "Ușoară euforie, senzație de căldură.", effect2: "Reflexe diminuate, percepție redusă a riscului.", effect3: "Limită legală pentru condus. Coordonare afectată.", effect4: "Stare de ebrietate. Vedere încețoșată, reacții lente.", effect5: "Intoxicație severă, risc de pierdere a cunoștinței.", factorsTitle: "Ce Îți Influentează Alcoolemia", factorsDescription: "Alcoolemia nu depinde doar de cât bei. Mai mulți factori personali joacă un rol crucial în absorbția și metabolizarea alcoolului.", factorSexTitle: "Sex Biologic", factorSexDescription: "Femeile au în general un procent mai mic de apă corporală și niveluri diferite de enzime decât bărbații, ceea ce duce la o alcoolemie mai mare pentru aceeași cantitate de alcool consumată.", factorWeightTitle: "Greutate Corporală", factorWeightDescription: "Alcoolul se distribuie în apa corporală. O persoană cu o greutate mai mare are o masă mai mare pentru a dilua alcoolul, rezultând o alcoolemie mai mică.", factorFoodTitle: "Mâncare în Stomac", factorFoodDescription: "Consumul de alcool pe stomacul plin încetinește absorbția acestuia în sânge, ducând la un vârf de alcoolemie mai scăzut și întârziat în comparație cu consumul pe stomacul gol.", disclaimerTitle: "⚠️ DISCLAIMER:", disclaimerText: "Acest instrument oferă doar o estimare în scopuri educaționale. Nu înlocuiește un etilotest profesional. Alcoolemia reală poate varia. Nu conduce dacă ai băut.", privacyTitle: "Citește politica de confidențialitate", privacy1Title: "Fără Colectare de Date", privacy1Text: "Acest instrument este conceput pentru a garanta anonimatul complet. <strong>Nu colectăm, salvăm sau transmitem nicio dată personală</strong> introdusă în simulator (sex, greutate, băuturi etc.).", privacy2Title: "Procesare Exclusiv Locală", privacy2Text: "Toate calculele necesare pentru estimarea alcoolemiei au loc <strong>exclusiv în browserul tău</strong> (client-side). Informațiile pe care le introduci nu părăsesc niciodată dispozitivul tău și nu ajung niciodată pe serverele noastre.", privacy3Title: "Fără Urmărirea Obiceiurilor", privacy3Text: "Nu folosim cookie-uri de profilare sau alte tehnologii de urmărire pentru a analiza obiceiurile sau comportamentul tău. Utilizarea instrumentului este volatilă: odată ce închizi pagina, toate informațiile introduse sunt șterse definitiv.", privacy4Title: "Scop Educațional", privacy4Text: "Scopul acestui instrument este pur educațional și informativ. A fost creat pentru a crește gradul de conștientizare cu privire la factorii care influențează alcoolemia și riscurile conducerii în stare de ebrietate, respectând pe deplin confidențialitatea utilizatorului.", privacy5Title: "Contact", privacy5Text: "Pentru orice informație sau comunicare privind confidențialitatea, poți scrie la:", copyright: "Copyright © 2025 Nicola Nicolaci. Toate drepturile rezervate."
                    },
                    // Albanian
                    sq: {
                        pageTitle: "Drejtim i Sigurt: Test Interaktiv i Alkoolemisë", mainTitle: "Drejtim i Sigurt: Test Interaktiv i Alkoolemisë", tagline: "Simulo nivelin e alkoolit në gjak për një drejtim më të ndërgjegjshëm.", tabSimulator: "Simulator", tabInformation: "Informacion", tabFactors: "Faktorët Kryesorë", createSimulationTitle: "Krijo Simulimin Tënd", createSimulationDescription: "Fut të dhënat e tua dhe pijet e konsumuara për të marrë një vlerësim të nivelit të alkoolit në gjak (BAC) dhe ecurinë e tij në kohë.", step1Title: "1. Të Dhëna Personale", labelSex: "Gjinia Biologjike", sexMale: "Mashkull", sexFemale: "Femër", labelWeight: "Pesha (kg)", placeholderWeight: "P.sh. 75", labelConsumption: "Konsumi", stomachFull: "Me stomak plot", stomachEmpty: "Me stomak bosh", step2Title: "2. Pijet e Konsumuara", drinksPlaceholder: "Shto një pije për të filluar.", btnAddDrink: "Shto Pije", step3Title: "3. Koha e Kalimit", timeElapsedLabel: "Orë nga pija e fundit:", btnReset: "Rivendos", btnCalculate: "Llogarit", errorWeight: "Ju lutemi vendosni një peshë të vlefshme (> 30 kg).", errorNoDrinks: "Shto të paktën një pije.", errorCustomDrink: "Për pije të personalizuara, ju lutemi vendosni vëllim dhe përqindje të vlefshme.", errorQuantity: "Ju lutemi vendosni një sasi të vlefshme për pijet.", errorNoAlcohol: "Nuk është konsumuar alkool.", resultsTitle: "Rezultati Juaj i Vlerësuar", resultsCurrentBac: "Niveli Aktual i Alkoolit në Gjak (BAC)", interpretationSafe: "Nën limitin ligjor. Kujdesi këshillohet gjithmonë.", interpretationWarning: "MBI LIMITIN LIGJOR. MOS NGASNI MAKINËN.", interpretationDanger: "GJENDJE DEHJEJE. Rrezik i lartë. MOS NGASNI MAKINËN.", timeToDriveLabel: "Koha e vlerësuar për t'u kthyer nën limit:", timeToDriveSoon: "Së shpejti nën limit", timeToDriveFormat: "Rreth {hours} orë dhe {minutes} minuta", timeToDriveSafe: "Mund të ngasësh makinën në mënyrë të sigurt", timeToDriveStatus: "Gjendja aktuale:", chartTitle: "Ecuria e Vlerësuar e BAC në Kohë", chartLabelBac: "Niveli i Alkoolit në Gjak (g/L)", chartLabelHours: "Orë nga pija e fundit", chartLabelLegalLimit: "Limiti Ligjor (0.5 g/L)", chartTooltipCurrent: "Vlerësimi aktual.", infoTitle: "Si Funksionon dhe Çfarë Do të Thotë", infoDescription: "Ky simulim bazohet në formulën Widmark, një metodë shkencore për vlerësimin e përqendrimit të alkoolit në gjak. Mësoni më shumë për efektet e BAC dhe limitet ligjore.", widmarkTitle: "Formula Widmark", widmarkDescription: "Llogaritja vlerëson BAC-in maksimal duke pjesëtuar gramët e alkoolit të konsumuar me masën trupore të shumëzuar me një koeficient difuzioni specifik për gjininë dhe statusin e vaktit. Më pas, zbret alkoolin e metabolizuar nga trupi me kalimin e kohës (rreth 0.15 g/L në orë).", effectsTitle: "Efektet e Nivelit të Alkoolit në Gjak (BAC)", tableHeaderBac: "BAC (g/L)", tableHeaderEffects: "Efektet e Zakonshme", effect1: "Eufori e lehtë, ndjenjë ngrohtësie.", effect2: "Reflekse të zvogëluara, perceptim më i ulët i rrezikut.", effect3: "Limiti ligjor për drejtimin e mjetit. Koordinim i dëmtuar.", effect4: "Gjendje dehjeje. Shikim i turbullt, reagime të ngadalta.", effect5: "Intoksikim i rëndë, rrezik i humbjes së vetëdijes.", factorsTitle: "Çfarë Ndikon në BAC-in Tuaj", factorsDescription: "Niveli i alkoolit në gjak nuk varet vetëm nga sasia që pini. Disa faktorë personalë luajnë një rol vendimtar në përthithjen dhe metabolizmin e alkoolit.", factorSexTitle: "Gjinia Biologjike", factorSexDescription: "Gratë në përgjithësi kanë një përqindje më të ulët të ujit në trup dhe nivele të ndryshme enzimash sesa burrat, gjë që çon në një BAC më të lartë për të njëjtën sasi alkooli të konsumuar.", factorWeightTitle: "Pesha Trupore", factorWeightDescription: "Alkooli shpërndahet në ujin e trupit. Një person me peshë më të madhe ka më shumë masë për të holluar alkoolin, duke rezultuar në një BAC më të ulët.", factorFoodTitle: "Ushqim në Stomak", factorFoodDescription: "Konsumimi i alkoolit me stomak plot ngadalëson përthithjen e tij në qarkullimin e gjakut, duke çuar në një kulm më të ulët dhe të vonuar të BAC-it në krahasim me pirjen me stomak bosh.", disclaimerTitle: "⚠️ KUJDES:", disclaimerText: "Ky mjet ofron vetëm një vlerësim për qëllime edukative. Nuk zëvendëson një alkooltest profesional. BAC-i aktual mund të ndryshojë. Mos ngisni makinën nëse keni pirë.", privacyTitle: "Lexo politikën e privatësisë", privacy1Title: "Asnjë Mbledhje të Dhënash", privacy1Text: "Ky mjet është projektuar për të garantuar anonimitet të plotë. <strong>Ne nuk mbledhim, ruajmë apo transmetojmë asnjë të dhënë personale</strong> të futur në simulator (gjinia, pesha, pijet, etj.).", privacy2Title: "Përpunim Ekskluzivisht Lokal", privacy2Text: "Të gjitha llogaritjet e nevojshme për të vlerësuar nivelin e alkoolit në gjak ndodhin <strong>ekskluzivisht brenda shfletuesit tuaj</strong> (client-side). Informacioni që ju futni nuk largohet kurrë nga pajisja juaj dhe nuk arrin kurrë në serverët tanë.", privacy3Title: "Asnjë Ndjekje e Zakoneve", privacy3Text: "Ne nuk përdorim cookie profilizimi ose teknologji të tjera gjurmimi për të analizuar zakonet ose sjelljen tuaj. Përdorimi i mjetit është i paqëndrueshëm: sapo të mbyllni faqen, të gjitha informacionet e futura fshihen përgjithmonë.", privacy4Title: "Qëllim Edukativ", privacy4Text: "Qëllimi i këtij mjeti është thjesht edukativ dhe informues. Ai u krijua për të rritur ndërgjegjësimin për faktorët që ndikojnë në nivelin e alkoolit në gjak dhe rreziqet e drejtimit të mjetit në gjendje të dehur, duke respektuar plotësisht privatësinë e përdoruesit.", privacy5Title: "Kontakt", privacy5Text: "Për çdo informacion ose komunikim në lidhje me privatësinë, mund të shkruani në:", copyright: "E drejta e autorit © 2025 Nicola Nicolaci. Të gjitha të drejtat e rezervuara."
                    },
                    // Russian
                    ru: {
                        pageTitle: "Безопасное Вождение: Интерактивный Алкотестер", mainTitle: "Безопасное Вождение: Интерактивный Алкотестер", tagline: "Смоделируйте уровень алкоголя в крови для более осознанного вождения.", tabSimulator: "Симулятор", tabInformation: "Информация", tabFactors: "Ключевые факторы", createSimulationTitle: "Создайте свою симуляцию", createSimulationDescription: "Введите свои данные и выпитые напитки, чтобы получить оценку уровня алкоголя в крови (BAC) и его динамику во времени.", step1Title: "1. Личные данные", labelSex: "Биологический пол", sexMale: "Мужчина", sexFemale: "Женщина", labelWeight: "Вес (кг)", placeholderWeight: "Напр. 75", labelConsumption: "Прием пищи", stomachFull: "На полный желудок", stomachEmpty: "На пустой желудок", step2Title: "2. Выпитые напитки", drinksPlaceholder: "Добавьте напиток, чтобы начать.", btnAddDrink: "Добавить напиток", step3Title: "3. Прошедшее время", timeElapsedLabel: "Часов с момента последнего употребления:", btnReset: "Сброс", btnCalculate: "Рассчитать", errorWeight: "Пожалуйста, введите действительный вес (> 30 кг).", errorNoDrinks: "Добавьте хотя бы один напиток.", errorCustomDrink: "Для пользовательских напитков введите действительный объем и крепость.", errorQuantity: "Пожалуйста, введите действительное количество для напитков.", errorNoAlcohol: "Алкоголь не употреблялся.", resultsTitle: "Ваш предполагаемый результат", resultsCurrentBac: "Текущий уровень алкоголя в крови (BAC)", interpretationSafe: "Ниже установленного законом предела. Всегда рекомендуется соблюдать осторожность.", interpretationWarning: "ВЫШЕ УСТАНОВЛЕННОГО ЗАКОНОМ ПРЕДЕЛА. НЕ САДИТЕСЬ ЗА РУЛЬ.", interpretationDanger: "СОСТОЯНИЕ ОПЬЯНЕНИЯ. Высокий риск. НЕ САДИТЕСЬ ЗА РУЛЬ.", timeToDriveLabel: "Примерное время, чтобы вернуться в пределы нормы:", timeToDriveSoon: "Скоро в пределах нормы", timeToDriveFormat: "Примерно {hours} ч. и {minutes} мин.", timeToDriveSafe: "Вы можете безопасно водить", timeToDriveStatus: "Текущий статус:", chartTitle: "Предполагаемая динамика BAC во времени", chartLabelBac: "Уровень алкоголя в крови (г/л)", chartLabelHours: "Часы с момента последнего употребления", chartLabelLegalLimit: "Законный предел (0.5 г/л)", chartTooltipCurrent: "Текущая оценка.", infoTitle: "Как это работает и что это значит", infoDescription: "Эта симуляция основана на формуле Видмарка, научном методе оценки концентрации алкоголя в крови. Узнайте больше о влиянии BAC и законодательных ограничениях.", widmarkTitle: "Формула Видмарка", widmarkDescription: "Расчет оценивает пиковый BAC путем деления граммов потребленного алкоголя на массу тела, умноженную на коэффициент распределения, специфичный для пола и приема пищи. Затем вычитается алкоголь, метаболизированный организмом с течением времени (около 0,15 г/л в час).", effectsTitle: "Влияние уровня алкоголя в крови (BAC)", tableHeaderBac: "BAC (г/л)", tableHeaderEffects: "Общие эффекты", effect1: "Легкая эйфория, ощущение тепла.", effect2: "Снижение рефлексов, пониженное восприятие риска.", effect3: "Законный предел для вождения. Нарушение координации.", effect4: "Состояние опьянения. Затуманенное зрение, замедленные реакции.", effect5: "Тяжелое отравление, риск потери сознания.", factorsTitle: "Что влияет на ваш BAC", factorsDescription: "Уровень алкоголя в крови зависит не только от того, сколько вы пьете. Несколько личных факторов играют решающую роль в усвоении и выведении алкоголя.", factorSexTitle: "Биологический пол", factorSexDescription: "У женщин, как правило, меньший процент воды в организме и другие уровни ферментов, чем у мужчин, что приводит к более высокому BAC при одинаковом количестве потребленного алкоголя.", factorWeightTitle: "Вес тела", factorWeightDescription: "Алкоголь распределяется в воде организма. У человека с большим весом больше массы для разбавления алкоголя, что приводит к более низкому BAC.", factorFoodTitle: "Пища в желудке", factorFoodDescription: "Употребление алкоголя на полный желудок замедляет его всасывание в кровь, что приводит к более низкому и отсроченному пику BAC по сравнению с употреблением натощак.", disclaimerTitle: "⚠️ ОТКАЗ ОТ ОТВЕТСТВЕННОСТИ:", disclaimerText: "Этот инструмент предоставляет оценку только в образовательных целях. Он не заменяет профессиональный алкотестер. Фактический BAC может отличаться. Не садитесь за руль, если вы пили.", privacyTitle: "Прочитайте политику конфиденциальности", privacy1Title: "Нет сбора данных", privacy1Text: "Этот инструмент разработан для обеспечения полной анонимности. <strong>Мы не собираем, не сохраняем и не передаем никакие личные данные</strong>, введенные в симулятор (пол, вес, напитки и т. д.).", privacy2Title: "Исключительно локальная обработка", privacy2Text: "Все расчеты, необходимые для оценки уровня алкоголя в крови, происходят <strong>исключительно в вашем браузере</strong> (на стороне клиента). Введенная вами информация никогда не покидает ваше устройство и никогда не попадает на наши серверы.", privacy3Title: "Нет отслеживания привычек", privacy3Text: "Мы не используем профилирующие файлы cookie или другие технологии отслеживания для анализа ваших привычек или поведения. Использование инструмента является временным: как только вы закроете страницу, вся введенная информация будет безвозвратно удалена.", privacy4Title: "Образовательная цель", privacy4Text: "Цель этого инструмента — исключительно образовательная и информационная. Он был создан для повышения осведомленности о факторах, влияющих на уровень алкоголя в крови, и о рисках вождения в нетрезвом виде, при полном уважении конфиденциальности пользователя.", privacy5Title: "Контакты", privacy5Text: "Для любой информации или сообщений относительно конфиденциальности вы можете написать по адресу:", copyright: "Авторское право © 2025 Никола Николачи. Все права защищены."
                    },
                    // Arabic
                    ar: {
                        pageTitle: "القيادة الآمنة: اختبار تفاعلي لنسبة الكحول في الدم", mainTitle: "القيادة الآمنة: اختبار تفاعلي لنسبة الكحول في الدم", tagline: "قم بمحاكاة مستوى الكحول في دمك لقيادة أكثر وعياً.", tabSimulator: "المحاكي", tabInformation: "معلومات", tabFactors: "العوامل الرئيسية", createSimulationTitle: "أنشئ محاكاتك", createSimulationDescription: "أدخل بياناتك والمشروبات التي تناولتها للحصول على تقدير لمستوى الكحول في الدم (BAC) واتجاهه بمرور الوقت.", step1Title: "١. البيانات الشخصية", labelSex: "الجنس البيولوجي", sexMale: "ذكر", sexFemale: "أنثى", labelWeight: "الوزن (كجم)", placeholderWeight: "مثال: 75", labelConsumption: "الاستهلاك", stomachFull: "على معدة ممتلئة", stomachEmpty: "على معدة فارغة", step2Title: "٢. المشروبات المستهلكة", drinksPlaceholder: "أضف مشروبًا للبدء.", btnAddDrink: "إضافة مشروب", step3Title: "٣. الوقت المنقضي", timeElapsedLabel: "ساعات منذ آخر مشروب:", btnReset: "إعادة تعيين", btnCalculate: "احسب", errorWeight: "الرجاء إدخال وزن صالح (> 30 كجم).", errorNoDrinks: "أضف مشروبًا واحدًا على الأقل.", errorCustomDrink: "للمشروبات المخصصة ، يرجى إدخال حجم و نسبة كحول صالحين.", errorQuantity: "الرجاء إدخال كمية صالحة للمشروبات.", errorNoAlcohol: "لم يتم استهلاك الكحول.", resultsTitle: "نتيجتك التقديرية", resultsCurrentBac: "المستوى الحالي للكحول في الدم (BAC)", interpretationSafe: "أقل من الحد القانوني. ينصح بالحذر دائمًا.", interpretationWarning: "أعلى من الحد القانوني. لا تقد السيارة.", interpretationDanger: "حالة سكر. خطر كبير. لا تقد السيارة.", timeToDriveLabel: "الوقت المقدر للعودة إلى ما دون الحد:", timeToDriveSoon: "قريباً تحت الحد", timeToDriveFormat: "حوالي {hours} ساعات و {minutes} دقيقة", timeToDriveSafe: "يمكنك القيادة بأمان", timeToDriveStatus: "الحالة الحالية:", chartTitle: "الاتجاه التقديري لنسبة الكحول في الدم بمرور الوقت", chartLabelBac: "مستوى الكحول في الدم (جم/لتر)", chartLabelHours: "ساعات منذ آخر مشروب", chartLabelLegalLimit: "الحد القانوني (0.5 جم/لتر)", chartTooltipCurrent: "التقدير الحالي.", infoTitle: "كيف يعمل وماذا يعني", infoDescription: "تعتمد هذه المحاكاة على صيغة ويدمارك ، وهي طريقة علمية لتقدير تركيز الكحول في الدم. تعرف على المزيد حول تأثيرات BAC والحدود القانونية.", widmarkTitle: "صيغة ويدمارك", widmarkDescription: "يحسب الحساب ذروة BAC بقسمة جرامات الكحول المستهلكة على كتلة الجسم مضروبة في معامل انتشار خاص بالجنس وحالة الوجبة. ثم يطرح الكحول الذي يستقلبه الجسم بمرور الوقت (حوالي 0.15 جم/لتر في الساعة).", effectsTitle: "تأثيرات مستوى الكحول في الدم (BAC)", tableHeaderBac: "BAC (جم/لتر)", tableHeaderEffects: "التأثيرات الشائعة", effect1: "نشوة خفيفة ، شعور بالدفء.", effect2: "انخفاض ردود الفعل ، انخفاض إدراك المخاطر.", effect3: "الحد القانوني للقيادة. ضعف التنسيق.", effect4: "حالة سكر. رؤية ضبابية ، ردود فعل بطيئة.", effect5: "تسمم حاد ، خطر فقدان الوعي.", factorsTitle: "ما الذي يؤثر على نسبة الكحول في دمك", factorsDescription: "لا يعتمد مستوى الكحول في الدم فقط على الكمية التي تشربها. تلعب العديد من العوامل الشخصية دورًا حاسمًا في امتصاص الكحول والتمثيل الغذائي.", factorSexTitle: "الجنس البيولوجي", factorSexDescription: "تمتلك النساء عمومًا نسبة أقل من ماء الجسم ومستويات إنزيم مختلفة عن الرجال ، مما يؤدي إلى ارتفاع نسبة BAC لنفس الكمية من الكحول المستهلكة.", factorWeightTitle: "وزن الجسم", factorWeightDescription: "يتم توزيع الكحول في ماء الجسم. الشخص الذي لديه وزن أعلى لديه كتلة أكبر لتخفيف الكحول ، مما يؤدي إلى انخفاض نسبة BAC.", factorFoodTitle: "الطعام في المعدة", factorFoodDescription: "يؤدي تناول الكحول على معدة ممتلئة إلى إبطاء امتصاصه في مجرى الدم ، مما يؤدي إلى ذروة BAC أقل وتأخر مقارنة بالشرب على معدة فارغة.", disclaimerTitle: "⚠️ إخلاء مسؤولية:", disclaimerText: "توفر هذه الأداة تقديرًا للأغراض التعليمية فقط. لا تحل محل جهاز تحليل الكحول الاحترافي. قد تختلف نسبة BAC الفعلية. لا تقد السيارة إذا كنت قد شربت.", privacyTitle: "اقرأ سياسة الخصوصية", privacy1Title: "لا يوجد جمع للبيانات", privacy1Text: "تم تصميم هذه الأداة لضمان عدم الكشف عن الهوية تمامًا. <strong>نحن لا نجمع أو نحفظ أو ننقل أي بيانات شخصية</strong> تم إدخالها في المحاكي (الجنس ، الوزن ، المشروبات ، إلخ).", privacy2Title: "معالجة محلية حصرية", privacy2Text: "تتم جميع الحسابات اللازمة لتقدير مستوى الكحول في الدم <strong>حصريًا داخل متصفحك</strong> (من جانب العميل). المعلومات التي تدخلها لا تغادر جهازك أبدًا ولا تصل إلى خوادمنا أبدًا.", privacy3Title: "لا يوجد تتبع للعادات", privacy3Text: "نحن لا نستخدم ملفات تعريف الارتباط أو تقنيات التتبع الأخرى لتحليل عاداتك أو سلوكك. استخدام الأداة متقلب: بمجرد إغلاق الصفحة ، يتم حذف جميع المعلومات المدخلة نهائيًا.", privacy4Title: "غرض تعليمي", privacy4Text: "الغرض من هذه الأداة تعليمي وإعلامي بحت. تم إنشاؤه لزيادة الوعي بالعوامل التي تؤثر على مستوى الكحول في الدم ومخاطر القيادة تحت تأثير الكحول ، مع الاحترام الكامل لخصوصية المستخدم.", privacy5Title: "اتصل", privacy5Text: "لأية معلومات أو اتصالات بخصوص الخصوصية ، يمكنك الكتابة إلى:", copyright: "حقوق النشر © 2025 نيكولا نيكولاتشي. جميع الحقوق محفوظة."
                    }
                },

                bevandeStandard: {
                    'birra_chiara': { names: { it: 'Birra Chiara (330ml)', en: 'Lager Beer (330ml)', fr: 'Bière Blonde (330ml)', de: 'Helles Bier (330ml)', es: 'Cerveza Rubia (330ml)', ro: 'Bere Blondă (330ml)', sq: 'Birrë Bjonde (330ml)', ru: 'Светлое пиво (330мл)', ar: 'بيرة خفيفة (330 مل)' }, gradazione: 0.05, volume: 330 },
                    'birra_doppio_malto': { names: { it: 'Birra Doppio Malto (330ml)', en: 'Double Malt Beer (330ml)', fr: 'Bière Double Malt (330ml)', de: 'Doppelmalzbier (330ml)', es: 'Cerveza Doble Malta (330ml)', ro: 'Bere Dublu Malt (330ml)', sq: 'Birrë Malto e Dyfishtë (330ml)', ru: 'Двойное солодовое пиво (330мл)', ar: 'بيرة شعير مزدوج (330 مل)' }, gradazione: 0.08, volume: 330 },
                    'vino_rosso': { names: { it: 'Bicchiere Vino Rosso (150ml)', en: 'Glass of Red Wine (150ml)', fr: 'Verre de Vin Rouge (150ml)', de: 'Glas Rotwein (150ml)', es: 'Copa de Vino Tinto (150ml)', ro: 'Pahar Vin Roșu (150ml)', sq: 'Gotë Verë e Kuqe (150ml)', ru: 'Бокал красного вина (150мл)', ar: 'كأس نبيذ أحمر (150 مل)' }, gradazione: 0.13, volume: 150 },
                    'vino_bianco': { names: { it: 'Bicchiere Vino Bianco (150ml)', en: 'Glass of White Wine (150ml)', fr: 'Verre de Vin Blanc (150ml)', de: 'Glas Weißwein (150ml)', es: 'Copa de Vino Blanco (150ml)', ro: 'Pahar Vin Alb (150ml)', sq: 'Gotë Verë e Bardhë (150ml)', ru: 'Бокал белого вина (150мл)', ar: 'كأس نبيذ أبيض (150 مل)' }, gradazione: 0.12, volume: 150 },
                    'aperitivo': { names: { it: 'Aperitivo (es. Spritz, 180ml)', en: 'Aperitif (e.g. Spritz, 180ml)', fr: 'Apéritif (ex. Spritz, 180ml)', de: 'Aperitif (z.B. Spritz, 180ml)', es: 'Aperitivo (ej. Spritz, 180ml)', ro: 'Aperitiv (ex. Spritz, 180ml)', sq: 'Aperitiv (p.sh. Spritz, 180ml)', ru: 'Аперитив (напр. Спритц, 180мл)', ar: 'فاتح للشهية (مثل سبيريتز، 180 مل)' }, gradazione: 0.11, volume: 180 },
                    'superalcolico_standard': { names: { it: 'Shot Superalcolico (40ml)', en: 'Shot of Spirits (40ml)', fr: 'Shot de Spiritueux (40ml)', de: 'Schnaps (40ml)', es: 'Chupito de Licor (40ml)', ro: 'Shot Tărie (40ml)', sq: 'Gotë Pije e Fortë (40ml)', ru: 'Шот крепкого алкоголя (40мл)', ar: 'جرعة كحول (40 مل)' }, gradazione: 0.40, volume: 40 },
                    'cocktail': { names: { it: 'Cocktail (es. Negroni, 100ml)', en: 'Cocktail (e.g. Negroni, 100ml)', fr: 'Cocktail (ex. Negroni, 100ml)', de: 'Cocktail (z.B. Negroni, 100ml)', es: 'Cóctel (ej. Negroni, 100ml)', ro: 'Cocktail (ex. Negroni, 100ml)', sq: 'Koktej (p.sh. Negroni, 100ml)', ru: 'Коктейль (напр. Негрони, 100мл)', ar: 'كوكتيل (مثل نيغروني، 100 مل)' }, gradazione: 0.28, volume: 100 },
                    'personalizzata': { names: { it: 'Bevanda Personalizzata', en: 'Custom Drink', fr: 'Boisson Personnalisée', de: 'Benutzerdefiniertes Getränk', es: 'Bebida Personalizada', ro: 'Băutură Personalizată', sq: 'Pije e Personalizuar', ru: 'Пользовательский напиток', ar: 'مشروب مخصص' }, isCustom: true }
                },

                init() {
                    this.cacheDOM();
                    this.bindEvents();
                    this.setupTabs();
                    this.setLanguage(this.currentLanguage);
                },

                cacheDOM() {
                    this.ui = {
                        languageSelector: document.getElementById('language-selector'),
                        tabs: {
                            buttons: document.querySelectorAll('.tab-btn'),
                            contents: document.querySelectorAll('.tab-content')
                        },
                        bevandeContainer: document.getElementById('bevande-container'),
                        bevandePlaceholder: document.getElementById('bevande-placeholder'),
                        btnAggiungi: document.getElementById('btn-aggiungi'),
                        btnCalcola: document.getElementById('btn-calcola'),
                        btnReset: document.getElementById('btn-reset'),
                        risultatoContainer: document.getElementById('risultato-container'),
                        errorMessage: document.getElementById('error-message'),
                        oreSlider: document.getElementById('ore'),
                        oreValore: document.getElementById('ore-valore'),
                        bacValore: document.getElementById('bac-valore'),
                        interpretazione: document.getElementById('interpretazione'),
                        tempoGuidaContainer: document.getElementById('tempo-guida-container'),
                        tempoGuidaLabel: document.getElementById('tempo-guida-label'),
                        tempoGuida: document.getElementById('tempo-guida'),
                        pesoInput: document.getElementById('peso')
                    };
                },
                
                bindEvents() {
                    this.ui.languageSelector.addEventListener('change', (e) => this.setLanguage(e.target.value));
                    this.ui.btnAggiungi.addEventListener('click', () => this.aggiungiBevanda());
                    this.ui.btnCalcola.addEventListener('click', () => this.calcolaBAC());
                    this.ui.btnReset.addEventListener('click', () => this.resetSimulatore());
                    this.ui.oreSlider.addEventListener('input', (e) => {
                        this.ui.oreValore.textContent = e.target.value;
                    });
                },

                setLanguage(lang) {
                    this.currentLanguage = lang;
                    document.documentElement.lang = lang;
                    document.documentElement.dir = lang === 'ar' ? 'rtl' : 'ltr';

                    const elements = document.querySelectorAll('[data-lang-key]');
                    elements.forEach(el => {
                        const key = el.getAttribute('data-lang-key');
                        if (this.translations[lang][key]) {
                            el.innerHTML = this.translations[lang][key];
                        }
                    });
                    
                    const placeholderElements = document.querySelectorAll('[data-lang-key-placeholder]');
                    placeholderElements.forEach(el => {
                        const key = el.getAttribute('data-lang-key-placeholder');
                         if (this.translations[lang][key]) {
                            el.placeholder = this.translations[lang][key];
                        }
                    });

                    this.updateBevandePlaceholder();
                    this.updateExistingBevandaSelects();
                    
                    // If results are already displayed, re-render them with the new language
                    if (this.lastResultData) {
                        this.mostraRisultato(this.lastResultData.bac, this.lastResultData.chartData, this.lastResultData.orePerTornareSottoLimite);
                    }
                },

                setupTabs() {
                    this.ui.tabs.buttons.forEach(button => {
                        button.addEventListener('click', () => {
                            const targetTab = button.dataset.tab;
                            
                            this.ui.tabs.buttons.forEach(btn => btn.classList.remove('active'));
                            button.classList.add('active');

                            this.ui.tabs.contents.forEach(content => {
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
                        this.ui.bevandePlaceholder.textContent = this.translations[this.currentLanguage].drinksPlaceholder;
                    }
                },
                
                updateExistingBevandaSelects() {
                    const selects = this.ui.bevandeContainer.querySelectorAll('.bevanda-tipo');
                    selects.forEach(select => {
                        const selectedValue = select.value;
                        let optionsHTML = '';
                        for (const key in this.bevandeStandard) {
                            optionsHTML += `<option value="${key}">${this.bevandeStandard[key].names[this.currentLanguage]}</option>`;
                        }
                        select.innerHTML = optionsHTML;
                        select.value = selectedValue; // Restore selection
                    });
                },

                aggiungiBevanda() {
                    this.bevandaCounter++;
                    const bevandaId = `bevanda-${this.bevandaCounter}`;
                    const itemDiv = document.createElement('div');
                    itemDiv.className = 'bevanda-item bg-slate-50 p-4 rounded-lg border grid grid-cols-6 gap-4 items-center';
                    itemDiv.id = bevandaId;

                    let selectHTML = '<select class="bevanda-tipo col-span-6 md:col-span-3 w-full p-2 border border-gray-300 rounded-lg focus:ring-1 focus:ring-red-500 focus:border-red-500">';
                    for (const key in this.bevandeStandard) {
                        selectHTML += `<option value="${key}">${this.bevandeStandard[key].names[this.currentLanguage]}</option>`;
                    }
                    selectHTML += '</select>';

                    itemDiv.innerHTML = `
                        ${selectHTML}
                        <div class="bevanda-details col-span-6 md:col-span-2 grid grid-cols-2 gap-2">
                            <input type="number" class="bevanda-quantita w-full p-2 border border-gray-300 rounded-lg" value="1" min="1" placeholder="Qty">
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
                    this.ui.pesoInput.value = '';
                    document.getElementById('sesso_m').checked = true;
                    document.getElementById('pasto_pieno').checked = true;
                    this.ui.oreSlider.value = 1;
                    this.ui.oreValore.textContent = 1;
                    this.ui.bevandeContainer.innerHTML = '';
                    this.updateBevandePlaceholder();
                    this.hideError();
                    this.ui.risultatoContainer.classList.add('hidden');
                    this.lastResultData = null;
                    if (this.bacChart) {
                        this.bacChart.destroy();
                    }
                },

                showError(messageKey) {
                    this.ui.errorMessage.textContent = this.translations[this.currentLanguage][messageKey];
                    this.ui.errorMessage.classList.remove('hidden');
                    this.ui.risultatoContainer.classList.add('hidden');
                },

                hideError() {
                    this.ui.errorMessage.classList.add('hidden');
                },

                calcolaBAC() {
                    this.hideError();
                    const peso = parseFloat(this.ui.pesoInput.value);
                    const ore = parseInt(this.ui.oreSlider.value);
                    if (isNaN(peso) || peso <= 30) { this.showError('errorWeight'); return; }
                    
                    const sesso = document.querySelector('input[name="sesso"]:checked').value;
                    const pasto = document.querySelector('input[name="pasto"]:checked').value;
                    const items = this.ui.bevandeContainer.querySelectorAll('.bevanda-item');
                    if (items.length === 0) { this.showError('errorNoDrinks'); return; }

                    let grammiAlcolTotali = 0;
                    const DENSITA_ALCOL = 0.789;
                    
                    for (const item of items) {
                        const tipo = item.querySelector('.bevanda-tipo').value;
                        const bevandaInfo = this.bevandeStandard[tipo];
                        
                        if (bevandaInfo.isCustom) {
                            const volume = parseFloat(item.querySelector('.custom-volume').value);
                            const gradazionePerc = parseFloat(item.querySelector('.custom-gradazione').value);
                            if (isNaN(volume) || isNaN(gradazionePerc) || volume <= 0 || gradazionePerc <= 0) {
                                this.showError('errorCustomDrink'); return;
                            }
                            grammiAlcolTotali += volume * (gradazionePerc / 100) * DENSITA_ALCOL;
                        } else {
                            const quantita = parseFloat(item.querySelector('.bevanda-quantita').value);
                            if (isNaN(quantita) || quantita <= 0) {
                                this.showError('errorQuantity'); return;
                            }
                            grammiAlcolTotali += bevandaInfo.volume * bevandaInfo.gradazione * DENSITA_ALCOL * quantita;
                        }
                    }

                    if (grammiAlcolTotali <= 0) { this.showError('errorNoAlcohol'); return; }

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
                    
                    this.lastResultData = { bac: bacAttuale, chartData, orePerTornareSottoLimite };
                    this.mostraRisultato(bacAttuale, chartData, orePerTornareSottoLimite);
                },

                mostraRisultato(bac, chartData, orePerTornareSottoLimite) {
                    this.ui.bacValore.textContent = bac.toFixed(2);
                    this.ui.interpretazione.classList.remove('bg-green-100', 'text-green-800', 'bg-yellow-100', 'text-yellow-800', 'bg-red-100', 'text-red-800');

                    if (bac < 0.5) {
                        this.ui.interpretazione.classList.add('bg-green-100', 'text-green-800');
                        this.ui.interpretazione.textContent = this.translations[this.currentLanguage].interpretationSafe;
                        this.ui.bacValore.style.color = '#15803d';
                    } else if (bac < 0.8) {
                        this.ui.interpretazione.classList.add('bg-yellow-100', 'text-yellow-800');
                        this.ui.interpretazione.textContent = this.translations[this.currentLanguage].interpretationWarning;
                        this.ui.bacValore.style.color = '#a16207';
                    } else {
                        this.ui.interpretazione.classList.add('bg-red-100', 'text-red-800');
                        this.ui.interpretazione.textContent = this.translations[this.currentLanguage].interpretationDanger;
                        this.ui.bacValore.style.color = '#b91c1c';
                    }

                    const oreAttuali = parseInt(this.ui.oreSlider.value);
                    if (bac >= 0.5) {
                        const tempoRimanente = orePerTornareSottoLimite - oreAttuali;
                        if (tempoRimanente > 0) {
                            const ore = Math.floor(tempoRimanente);
                            const minuti = Math.round((tempoRimanente - ore) * 60);
                            this.ui.tempoGuida.textContent = this.translations[this.currentLanguage].timeToDriveFormat
                                .replace('{hours}', ore)
                                .replace('{minutes}', minuti);
                            this.ui.tempoGuidaLabel.textContent = this.translations[this.currentLanguage].timeToDriveLabel;
                            this.ui.tempoGuida.style.color = '#b91c1c';
                        } else {
                            this.ui.tempoGuida.textContent = this.translations[this.currentLanguage].timeToDriveSoon;
                            this.ui.tempoGuidaLabel.textContent = this.translations[this.currentLanguage].timeToDriveLabel;
                            this.ui.tempoGuida.style.color = '#a16207';
                        }
                    } else {
                        this.ui.tempoGuida.textContent = this.translations[this.currentLanguage].timeToDriveSafe;
                        this.ui.tempoGuidaLabel.textContent = this.translations[this.currentLanguage].timeToDriveStatus;
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
                    const lang = this.currentLanguage;
                    
                    this.bacChart = new Chart(chartCtx, {
                        type: 'line',
                        data: {
                            labels: chartData.labels,
                            datasets: [
                                {
                                    label: this.translations[lang].chartLabelBac,
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
                                    label: this.translations[lang].chartLabelLegalLimit,
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
                                title: { display: true, text: this.translations[lang].chartTitle, font: { size: 16 }, color: '#334155', padding: { bottom: 20 } },
                                legend: { position: 'bottom', labels: { color: '#334155' } },
                                tooltip: {
                                    callbacks: {
                                        footer: (tooltipItems) => {
                                            if (tooltipItems[0].datasetIndex === 0 && tooltipItems[0].dataIndex === chartData.currentIndex) {
                                                return this.translations[lang].chartTooltipCurrent;
                                            }
                                            return '';
                                        }
                                    }
                                }
                            },
                            scales: {
                                x: { title: { display: true, text: this.translations[lang].chartLabelHours, color: '#475569' }, ticks: { color: '#475569' }, grid: { display: false } },
                                y: { title: { display: true, text: this.translations[lang].chartLabelBac, color: '#475569' }, beginAtZero: true, ticks: { color: '#475569' } }
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
