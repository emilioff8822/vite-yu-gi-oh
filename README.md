Creo un nuovo componente Search.vue nella cartella components.
Nel file Search.vue, aggiungo un input per la ricerca e una casella di selezione per il tipo di carta.
Utilizzo $emit per inviare l'input di ricerca e il valore della casella di selezione al componente padre (App.vue).
Modifico App.vue per ricevere gli eventi emessi dal componente figlio e aggiorna la chiamata API in base ai valori ricevuti.