# Liascript zur Bruchrechnung

Dieses Skript führt grundlegende Bruchrechnungen (Addition, Subtraktion, Multiplikation und Division) durch und kürzt die Ergebnisse, wenn möglich.

```liascript
(* Bruchrechnungen *)

(* Funktion zum Kürzen eines Bruchs *)
kürze[Zähler, Nenner] :=
  let
    ggt := größterGemeinsamerTeiler[Zähler, Nenner]
  in
    (Zähler / ggt, Nenner / ggt)

(* Funktion zum Berechnen des größten gemeinsamen Teilers (ggT) *)
größterGemeinsamerTeiler[a, b] :=
  if b = 0 then
    a
  else
    größterGemeinsamerTeiler[b, a mod b]
