<script setup>
import { Head, Link } from "@inertiajs/vue3";

defineProps({
    canLogin: {
        type: Boolean,
    },
    canRegister: {
        type: Boolean,
    },
    laravelVersion: {
        type: String,
        required: true,
    },
    phpVersion: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <Head title="Inizia il Test" />
    <div class="bg-gray-50 text-black/50 dark:bg-black dark:text-white/50">
        <img
            id="background"
            class="absolute -left-20 top-0 max-w-[877px]"
            src="https://laravel.com/assets/img/welcome/background.svg"
        />
        <div
            class="relative min-h-screen flex flex-col items-center justify-center selection:bg-[#FF2D20] selection:text-white"
        >
            <div class="relative w-full max-w-2xl px-6 lg:max-w-7xl">
                <header
                    class="grid grid-cols-2 items-center gap-2 py-4 lg:grid-cols-3"
                >
                    <div class="flex lg:justify-center lg:col-start-2">
                        <h1 class="text-2xl font-bold dark:text-white">
                            Il Test
                        </h1>
                    </div>
                    <nav v-if="canLogin" class="-mx-3 flex flex-1 justify-end">
                        <Link
                            v-if="$page.props.auth.user"
                            :href="route('dashboard')"
                            class="rounded-md px-3 py-2 text-black ring-1 ring-transparent transition hover:text-black/70 focus:outline-none focus-visible:ring-[#FF2D20] dark:text-white dark:hover:text-white/80 dark:focus-visible:ring-white"
                        >
                            Dashboard
                        </Link>

                        <template v-else>
                            <Link
                                :href="route('login')"
                                class="rounded-md px-3 py-2 text-black ring-1 ring-transparent transition hover:text-black/70 focus:outline-none focus-visible:ring-[#FF2D20] dark:text-white dark:hover:text-white/80 dark:focus-visible:ring-white"
                            >
                                Log in
                            </Link>

                            <Link
                                v-if="canRegister"
                                :href="route('register')"
                                class="rounded-md px-3 py-2 text-black ring-1 ring-transparent transition hover:text-black/70 focus:outline-none focus-visible:ring-[#FF2D20] dark:text-white dark:hover:text-white/80 dark:focus-visible:ring-white"
                            >
                                Register
                            </Link>
                        </template>
                    </nav>
                </header>

                <div
                    class="mx-auto text-sm w-2/3 space-y-2 text-center rounded-lg bg-white p-6 shadow-[0px_14px_34px_0px_rgba(0,0,0,0.08)] ring-1 ring-white/[0.05] lg:pb-10 dark:bg-zinc-900 dark:ring-zinc-800"
                >
                    <p>
                        Questo test richiede la creazione di una semplice
                        applicazione di raccolta delle candidature di
                        programmatori da aggiungere al nostro team.
                    </p>

                    <p>
                        Sono presenti i modelli degli utenti e delle
                        candidature(application), mentre sono da creare le
                        componenti front-end e back-end per consentirne
                        l'inserimento.
                    </p>

                    <p>
                        Sotto trovi gli step da completare per creare la tua
                        applicazione. Trovi le richieste minime per creare la
                        tua app, e dei requisiti extra se vuoi cimentarti in
                        qualcosa di più avanzato. <b>Riesci a finirla?</b>
                    </p>
                </div>

                <main class="my-6">
                    <div class="grid gap-6 lg:grid-cols-2 lg:gap-8">
                        <div
                            class="flex items-start gap-4 rounded-lg bg-white p-6 shadow-[0px_14px_34px_0px_rgba(0,0,0,0.08)] ring-1 ring-white/[0.05] lg:pb-10 dark:bg-zinc-900 dark:ring-zinc-800"
                        >
                            <div
                                class="flex font-bold text-[#FF2D20] size-12 shrink-0 items-center justify-center rounded-full bg-[#FF2D20]/10 sm:size-16"
                            >
                                Start
                            </div>

                            <div class="pt-3 sm:pt-5">
                                <h2
                                    class="text-xl font-semibold text-black dark:text-white"
                                >
                                    Requisiti Base
                                </h2>

                                <ul class="mt-4 text-sm/relaxed list-disc">
                                    <li>
                                        Aggiungi la tipologia di utente,
                                        permettendo di definire se normale o
                                        amministratore
                                    </li>
                                    <li>
                                        Crea un controller per gestire le
                                        Application come risorsa, gestendo così
                                        il CRUD del modello delle candidature
                                    </li>
                                    <li>
                                        Aggiungi le routes e il menu di
                                        navigazione per le candidature
                                    </li>
                                    <li>
                                        Nella pagina principale delle
                                        candidature l'utente normale può
                                        scegliere di inserire una nuova
                                        candidatura o vedere la lista di quelle
                                        già inviate
                                    </li>
                                    <li>
                                        Nella pagina principale delle
                                        candidature l'utente amministratore vede
                                        la lista completa delle candidature
                                    </li>
                                    <li>
                                        Nella lista delle candidature gli utenti
                                        sono in grado di modificare o cancellare
                                        le proprie candidature
                                    </li>
                                    <li>
                                        Nella lista delle candidature gli utenti
                                        amministratori possono accettare o
                                        cancellare le candidature degli utenti
                                    </li>
                                    <li>
                                        Dare la possibilità agli utenti di
                                        vedere lo stato delle proprie
                                        candidatura (accettata, rifiutata o in
                                        attesa)
                                    </li>
                                </ul>
                            </div>
                        </div>

                        <div
                            class="flex items-start gap-4 rounded-lg bg-white p-6 shadow-[0px_14px_34px_0px_rgba(0,0,0,0.08)] ring-1 ring-white/[0.05] lg:pb-10 dark:bg-zinc-900 dark:ring-zinc-800"
                        >
                            <div
                                class="flex font-bold text-[#FF2D20] size-12 shrink-0 items-center justify-center rounded-full bg-[#FF2D20]/10 sm:size-16"
                            >
                                Bonus
                            </div>

                            <div class="pt-3 sm:pt-5">
                                <h2
                                    class="text-xl font-semibold text-black dark:text-white"
                                >
                                    Requisiti Extra
                                </h2>

                                <ul class="mt-4 text-sm/relaxed list-disc">
                                    <li>
                                        Utilizza fin da subito Git, creando un
                                        branch di sviluppo e aggiungendo le tue
                                        modifiche in modo incrementale
                                    </li>
                                    <li>
                                        Crea un Factory delle Application e
                                        utilizzalo per popolare il database con
                                        il comando seed di laravel
                                    </li>
                                    <li>
                                        All'inserimento di una candidatura
                                        inviare una mail agli amministratori
                                    </li>
                                    <li>
                                        All'accettazione o rifiuto di una
                                        candidatura inviare una mail al
                                        candidato
                                    </li>
                                    <li>
                                        Aggiungere nella dashboard degli
                                        amministratori le statistiche delle
                                        candidature (nr candidature, candidati,
                                        accettate, rifiutate, in attesa)
                                    </li>
                                    <li>
                                        Accertarsi che un utente normale non
                                        possa accedere alle candidature di un
                                        altro utente
                                    </li>
                                    <li>
                                        Utilizza la libreria
                                        <a
                                            class="text-red-600 underline hover:text-red-400"
                                            target="_blank"
                                            href="https://primevue.org/vite/"
                                            >PrimeVue</a
                                        >
                                        per implementare le liste delle
                                        candidature come
                                        <a
                                            class="text-red-600 underline hover:text-red-400"
                                            target="_blank"
                                            href="https://primevue.org/datatable/"
                                            >DataTable</a
                                        >
                                    </li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </main>

                <div
                    class="mx-auto text-sm w-2/3 space-y-1 text-center rounded-lg bg-white p-6 shadow-[0px_14px_34px_0px_rgba(0,0,0,0.08)] ring-1 ring-white/[0.05] lg:pb-10 dark:bg-zinc-900 dark:ring-zinc-800"
                >
                    <h2 class="text-base font-bold py-1">Quando hai finito</h2>
                    <p>
                        Fai un pull-request sulla repository oppure crea uno zip
                        da inviarci via mail (Hint: lo zip non dovrebbe superare
                        i 5MB). Esamineremo il codice che hai scritto.
                    </p>
                    <h2 class="text-base font-bold py-1">Cosa esamineremo</h2>
                    <p>
                        Guarderemo se il codice funziona e se i requisiti sono
                        rispettati... ma guarderemo anche tutto il resto: la
                        qualità e l'ordine del codice, l'inventiva per risolvere
                        un problema, quanto conosci Laravel, le ottimizzazioni,
                        i piccoli dettagli e come lavori con Git (in caso di
                        utilizzo).
                    </p>
                    <p>
                        Non aver paura di osare, di stravolgere tutto, o, al
                        contrario, di usare la nostra traccia, o di essere
                        troppo banale. <br />Prova - se ti va - a stupirci.<br />Segui
                        i principi del clean code, per noi sono importanti!
                    </p>
                </div>

                <footer
                    class="py-8 text-center text-sm text-black dark:text-white/70"
                >
                    Laravel v{{ laravelVersion }} (PHP v{{ phpVersion }})
                </footer>
            </div>
        </div>
    </div>
</template>
