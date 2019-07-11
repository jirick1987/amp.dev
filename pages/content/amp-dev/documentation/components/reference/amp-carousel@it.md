---
$category@: layout
formats:
- websites
- email
- ads
teaser:
  text: Mostra più contenuti simili lungo un asse orizzontale.
---

<!--- Reformatted by Reftar! for AMP (go/reftar) on 2019-06-13 -->
<!---
       Copyright 2015 The AMP HTML Authors. Tutti i diritti riservati.

       Rilasciato ai sensi della Licenza Apache, versione 2.0 (la "Licenza");
     è possibile utilizzare questo file esclusivamente in conformità con la Licenza.
     Una copia della Licenza è disponibile all'indirizzo

     http://www.apache.org/licenses/LICENSE-2.0

     Se non diversamente imposto dalla legge vigente o concordato per iscritto,
     il software rilasciato ai sensi della Licenza viene distribuito "COSÌ COM'È",
     SENZA GARANZIE O CONDIZIONI DI ALCUN TIPO, esplicite o implicite.
     Leggi la Licenza per conoscere le autorizzazioni e le limitazioni in vigore
     specifiche della lingua previste dalla Licenza.
-->

#amp-carousel

Un carosello generico per mostrare più contenuti simili lungo un asse orizzontale, progettato per un'ottima flessibilità e prestazioni.

<table>
  <tr>
    <td width="40%"><strong>Script obbligatorio</strong></td>
    <td><code>&lt;script async custom-element="amp-carousel" src="https://cdn.ampproject.org/v0/amp-carousel-0.1.js">&lt;/script></code></td>
  </tr>
  <tr>
    <td class="col-fourty"><strong><a href="https://www.ampproject.org/docs/guides/responsive/control_layout.html">Layout supportati</a></strong></td>
    <td>
      <ul>
        <li>carosello: fixed, fixed-height e nodisplay.</li>
        <li>diapositive: fill, fixed, fixed-height, flex-item, nodisplay e responsive.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td width="40%"><strong>Esempi</strong></td>
    <td>AMP By Example:<ul>
      <li><a href="https://ampbyexample.com/components/amp-carousel/">Esempio di amp-carousel</a></li>
      <li><a href="https://ampbyexample.com/advanced/image_galleries_with_amp-carousel/">Gallerie di immagini con amp-carousel</a></li></ul></td>
    </tr>
  </table>

##Comportamento

Ciascuno degli elementi secondari immediati del componente `amp-carousel` viene considerato un elemento del carosello. Ognuno di questi nodi può avere anche elementi secondari HTML arbitrari.

Il carosello è composto da un numero arbitrario di elementi e da frecce di navigazione per avanzare o tornare indietro di un singolo elemento.

Il carosello passa da un elemento all'altro se l'utente scorre, utilizza le frecce di navigazione o fa clic su una freccia di navigazione facoltativa.

<!--embedded example - displays in ampproject.org -->

<div>
  <amp-iframe height="313" src="https://ampproject-b5f4c.firebaseapp.com/examples/ampcarousel.basic.embed.html" layout="fixed-height" sandbox="allow-scripts allow-forms allow-same-origin" resizable="">
    <div aria-label="Espandi" overflow="" tabindex="0" role="button">Mostra il codice completo</div>
    <div placeholder=""></div>
  </amp-iframe>
</div>

###Passare a una diapositiva specifica

Se imposti un metodo per l'attributo `on` di un elemento su `tap:carousel-id.goToSlide(index=N)`, al tocco o clic dell'utente il carosello con l'ID "carousel-id" avanzerà a index=N, dove la prima diapositiva si trova a index=0, la seconda a index=1 e così via.

Nel seguente esempio, viene mostrato un carosello di tre immagini con in basso dei pulsanti di anteprima. Quando un utente fa clic su uno dei pulsanti, viene visualizzato l'elemento del carosello corrispondente.

<!--embedded example - displays in ampproject.org -->

<div>
  <amp-iframe height="878" src="https://ampproject-b5f4c.firebaseapp.com/examples/ampcarousel.advance-slide.embed.html" layout="fixed-height" sandbox="allow-scripts allow-forms allow-same-origin" resizable="">
    <div aria-label="Espandi" overflow="" tabindex="0" role="button">Mostra il codice completo</div>
    <div placeholder=""></div>
  </amp-iframe>
</div>

##Attributi

<table>
  <tr>
    <td width="40%"><strong>type</strong></td>
    <td>Specifica il tipo di visualizzazione per gli elementi del carosello, che può essere:
      <ul>
        <li><code>carousel</code>(impostazione predefinita): vengono mostrate tutte le diapositive, che possono essere fatte scorrere orizzontalmente. Questo tipo supporta solo i layout `<code>fixed</code>, <code>fixed-height</code> e <code>nodisplay</code>.</li>
        <li><code>slides</code>: mostra una sola diapositiva alla volta. Questo tipo supporta i layout <code>fill</code>, <code>fixed</code>, <code>fixed-height</code>, <code>flex-item</code>, <code>nodisplay</code> e <code>responsive</code>.</li>
      </ul></td>
    </tr>
    <tr>
      <td width="40%"><strong>height (obbligatorio)</strong></td>
      <td>Specifica l'altezza del carosello in pixel.</td>
    </tr>
    <tr>
      <td width="40%"><strong>controls (facoltativo)</strong></td>
      <td>Mostra sempre le frecce destra e sinistra per permettere all'utente di navigare tra gli elementi del carosello sui dispositivi mobili.
          Per impostazione predefinita, le frecce di navigazione scompaiono dopo qualche secondo sui dispositivi mobili.
          Puoi controllare la visibilità delle frecce anche modificando lo stile e utilizzare una query supporti per mostrare le frecce solo quando lo schermo ha una determinata larghezza. Su computer desktop, le frecce vengono mostrate sempre, a meno che non sia presente un solo elemento secondario.</td>
      </tr>
      <tr>
        <td width="40%"><strong>data-next-button-aria-label (facoltativo)</strong></td>
        <td>Imposta l'aria-label per <code>amp-carousel-button-next</code>. Se non viene fornito alcun valore, aria-label viene impostata di default su "Elemento successivo del carosello".</td>
      </tr>
      <tr>
        <td width="40%"><strong>data-prev-button-aria-label (facoltativo)</strong></td>
        <td>Imposta l'aria-label per <code>amp-carousel-button-prev</code>. Se non viene fornito alcun valore, aria-label viene impostata di default su "Elemento precedente del carosello".</td>
      </tr>
      <tr>
        <td width="40%"><strong>data-button-count-format (facoltativo)</strong></td>
        <td>Una stringa di formattazione che appare come <code>(%s of %s)</code>, utilizzata come suffisso dell'aria-label per <code>amp-carousel-button-next</code>/<code>amp-carousel-button-prev</code>. Fornisce informazioni agli utenti che utilizzano uno screen reader per monitorare il loro avanzamento nel carosello. Se non viene fornito alcun valore, quello predefinito è "(%s of %s)".</td>
      </tr>
      <tr>
        <td width="40%"><strong>autoplay (facoltativo)</strong></td>
        <td>Consente di passare alla diapositiva successiva senza alcuna interazione da parte dell'utente.<br>
          Se presente senza un valore:
          <ul>
            <li>Per impostazione predefinita, fa avanzare una diapositiva in intervalli di 5000 millisecondi (5 secondi); sostituibile dall'attributo <code>delay</code>.</li>
            <li>Allega l'attributo <code>loop</code> ad <code>amp-carousel</code> se <code>loop</code> non è già presente.</li>
            <li>Sono necessarie almeno due diapositive per la riproduzione automatica.</li>
            <li>Si applica solo ai caroselli con <code>type=slides</code>.</li>
          </ul>
          Se presente con un valore:
          <ul>
            <li>Allega l'attributo <code>loop</code> ad <code>amp-carousel</code> se <code>loop</code> non è già presente.</li>
            <li>Rimuove l'attributo <code>loop</code> dopo che è avvenuto il numero specificato di ripetizioni.</li>
          </ul></td>
        </tr>
        <tr>
          <td width="40%"><strong>delay (facoltativo)</strong></td>
          <td>Specifica la durata in millisecondi del ritardo dell'avanzamento alla diapositiva successiva quando è attivo <code>autoplay</code>. L'attributo <code>delay</code> si applica solo ai caroselli con <code>type=slides</code>.</td>
        </tr>
        <tr>
          <td width="40%"><strong>loop (facoltativo)</strong></td>
          <td>Consente all'utente di avanzare oltre il primo o l'ultimo elemento. Affinché avvenga la ripetizione, devono essere presenti almeno 3 diapositive. L'attributo <code>loop</code> si applica solo ai caroselli con <code>type=slides</code>.
            <em>Esempio: mostra un carosello di diapositive con controlli, ripetizione e riproduzione automatica ritardata.</em>
            <!--embedded example - displays in ampproject.org -->
            <div>
              <amp-iframe height="446" src="https://ampproject-b5f4c.firebaseapp.com/examples/ampcarousel.controls.embed.html" layout="fixed-height" sandbox="allow-scripts allow-forms allow-same-origin" resizable="">
                <div aria-label="Espandi" overflow="" tabindex="0" role="button">Mostra il codice completo</div>
                <div placeholder=""></div>
              </amp-iframe>
            </div></td>
          </tr>
          <tr>
            <td width="40%"><strong>common attributes</strong></td>
            <td>Questo elemento include <a href="https://www.ampproject.org/docs/reference/common_attributes">attributi comuni</a> estesi ai componenti AMP.</td>
          </tr>
        </table>

##Stili

* Puoi utilizzare il selettore di elementi `amp-carousel` per modificare lo stile del carosello.
* Puoi utilizzare il selettore di classi `.amp-carousel-slide` per concentrarti su elementi specifici del carosello.
* Lo stato visivo di un pulsante `amp-carousel` quando è disattivato è nascosto.
* Per impostazione predefinita, `.amp-carousel-button` utilizza un SVG incorporato come immagine di sfondo dei pulsanti. Puoi sostituire questa impostazione con il tuo SVG o immagine, come nell'esempio riportato di seguito.

*Esempio: SVG incorporato `.amp-carousel-button` predefinito*

```css
.amp-carousel-button-prev {
  left: 16px;
  background-image: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 18 18"><path d="M15 8.25H5.87l4.19-4.19L9 3 3 9l6 6 1.06-1.06-4.19-4.19H15v-1.5z" fill="#fff" /></svg>');
}
```

*Esempio: sostituzione dell'SVG incorporato `.amp-carousel-button` predefinito*

```css
.amp-carousel-button-prev {
  left: 5%;
  background-image: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 18 18"><path d="M11.56 5.56L10.5 4.5 6 9l4.5 4.5 1.06-1.06L8.12 9z" fill="#fff" /></svg>');
}
```

##Convalida

Consulta le [regole amp-carousel](https://github.com/ampproject/amphtml/blob/master/extensions/amp-carousel/validator-amp-carousel.protoascii) nella specifica dello strumento di convalida AMP.