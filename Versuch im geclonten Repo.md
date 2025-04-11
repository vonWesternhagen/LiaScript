# Liascript zur Bruchrechnung ist das das origian?

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

(* Addition von zwei Brüchen *)
addiereBrüche[a1, b1, a2, b2] :=
  let
    gemeinsamerNenner := b1 * b2
    neuerZähler := (a1 * b2) + (a2 * b1)
  in
    kürze[neuerZähler, gemeinsamerNenner]

(* Subtraktion von zwei Brüchen *)
subtrahiereBrüche[a1, b1, a2,
