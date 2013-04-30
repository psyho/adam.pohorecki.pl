# Clojure

* mam szczwany plan
* kto uczy się nowego języka programowania co rok?
* jakie języki?
* ktoś nie?
* dlaczego warto się uczyć nowych języków?
* dwa powody:
  * bo są dobre do pewnych zastosowań, do których nasz "podstawowy" język się nie nadaje (ObjectiveC, JavaScript, Scala, C#)
  * bo są odmienne od języków, które znamy i wpływają na nasz sposób myślenia i rozwązywania problemów (Haskell)
* Clojure warto się nauczyć z obu powodów

## Co to jest Clojure

* LISP na JVM
* LISPy mają się dobrze od ponad 50 lat

## co jest mocną stroną Clojure?
* prawo Moore'a
* równoległe przetwarzanie będzie coraz ważniejsze z czasem
* Clojure jest językiem stworzonym z myślą o równoległości
* immutable - persistent data structures
* rozdział pojęć wartość/stan/tożsamość
* szereg bazujących na tym konstruktów: var, atom, ref, agent, future, promise
* STM (transakcje ACI na poziomie języka programowania)
* Clojure = współbieżność na bogato
* Dodatkowo: ClojureScript

## dlaczego Clojure zmienia sposób myślenia?

* Clojure nie jest językiem obiektowym
  * mniejsza podstawowa jednostka: funkcja zamiast obiektu
  * rozdział logiki i danych
  * brak dziedziczenia jako mechanizmu powtórnego użycia kodu
  * silny podział logiki na czyste funkcje i modyfikację stanu

## Cloujure jest jak Ruby, ale...

* ekspresywny
* dynamicznie typowany
* pozwala odstrzelić sobie nogę

* build-your-own-language
  * Ruby (bloki, method_missing, define_method): transaction { something }
  * Clojure (makra): (transaction (something))
  * ale... makra mogą więcej (if, %w)

* otwarte klasy
  * Ruby: "foo".classify, :foo.classify, Foo.classify
  * Clojure (classify "foo"), (classify :foo), (classify Foo)
  * Ruby - ryzyko nadpisania, Clojure - nie ma ryzyka

* polimorfizm
  * Ruby: duck typing, po pierwszym argumencie
  * Clojure: po pierwszym argumencie (protokoły), po dowolnym/wielu argumentach (multimethods)

## Resources

* Programming Clojure
* Joy of Clojure
* Clojure Programming
* 4Clojure
