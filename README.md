"Spēlējamies" šeit
https://mrexid.github.io/izdienas-kalkulators/izd_pens_apr_iem_ievp_vk_jauns.html

“Aprēķina sākuma datums (precīzam stāžam)” ir atslēga tam, lai stāžs “augtu” nevis tikai pa gadiem, bet pa mēnešiem.
Ko tas nozīmē kalkulatorā

    Interpretācija: tas ir atskaites datums, uz kuru Jūs esat norādījis “Izdienas stāžs šodien (gadi)”.
    Citiem vārdiem — cik stāža man ir šajā datumā.

    No šī datuma kalkulators iet uz priekšu pa mēnešiem (1 mēneša solis) un katrā potenciālajā datumā:

        vecumu skaita pēc dzimšanas datuma,

        stāžu skaita kā:
  <img width="844" height="58" alt="image" src="https://github.com/user-attachments/assets/668ac6c6-786e-41e4-ad01-6d3b2acd3811" />


        Ja “Turpināšu dienestu = Nē”, stāžs nemainās — tas ir konstants neatkarīgi no laika.

Precizitāte “pa mēnešiem”

    Funkcija aprēķina pilnu mēnešu skaitu starp “Aprēķina sākuma datumu” un vērtēšanas datumu. Ja diena mēnesī vēl nav “pilna”, tas mēnesis netiek ieskaitīts.
    (Piemēram, no 2025-08-15 līdz 2025-09-14 ir 0 pilni mēneši; līdz 2025-09-15 — 1 pilns mēnesis.)

    Tāpēc stāžs pieaug 0.0833… gada (1/12) solī.

Kur tas tiek lietots

    Agrākā iespējamā datuma meklēšana (Esošais un Plānotais scenārijs) — skenē pa mēnešiem no “Aprēķina sākuma datuma” līdz brīdim, kad vienlaikus izpildās:

        Esošais: vecums ≥ 50 un stāžs ≥ 20.

        Plānotais: vecums ≥ plānotais min. vecums un stāžs ≥ plānotais min. stāžs
        (abi sliekšņi kopš 2027. gada palielinās par 0.5 gada gadā: vecums 50→55, stāžs 20→25; tas attiecas uz visiem).

    Gada tabula — katram gadam rāda stāžu uz 31.12., izmantojot to pašu mēnešu skaitīšanu no sākuma datuma.

Praktisks piemērs

    Ievade:

        Dzimšanas datums: 1981-06-15

        Izdienas stāžs šodien: 26.00

        Aprēķina sākuma datums: 2025-08-06

        Turpināšu dienestu: Jā

    Tad 2027-02-06 (pēc 18 pilniem mēnešiem) stāžs būs: 26 + 18/12 = 27.50 gadi.

    Ja Turpināšu dienestu = Nē, stāžs arī 2027-02-06 paliek 26.00.

Īpašas piezīmes un malas gadījumi

    Ja jau sākuma datumā nosacījumi izpildās (piem., vecums un stāžs jau sasniegti), agrākais datums būs tieši sākuma datums.

    Ja sākuma datums ir “pārāk vēls” un Jūs neturpināt dienestu, bet nosacījumi vēl nav sasniegti, kalkulators var neatrast atbilstību līdz 2060. gadam.

    Rādīšanai stāžs tiek noapaļots līdz 2 zīmēm aiz komata (skaitļošanā saglabājas pilnā precizitāte).

    Atvaļinājumi bez atalgojuma, nepilns darba laiks u.tml. netiek atsevišķi modelēti — vienkāršības dēļ pieņemam, ka, ja izvēlēts “Turpināšu = Jā”, stāžs krājas vienmērīgi pa mēnešiem.


    Kā tas strādā formulā

    Ievadītais stāžs šodien (gadi) = Jūsu stāžs tieši “Aprēķina sākuma datumā”.

    Pēc tam (ja turpināt dienestu) katrs pilns mēnesis pievieno 1/12 gada stāža:
 <img width="574" height="73" alt="image" src="https://github.com/user-attachments/assets/1a715788-ea24-4adb-8d09-dbef28fdc04e" />


    “Pilns mēnesis” nozīmē, ka līdz tā pašai mēneša dienai ir aiztecējis vesels mēnesis.
    Piem.: no 06.08. līdz 06.09. = 1 mēnesis, bet līdz 05.09. = 0.

    Vecums tiek rēķināts precīzi pēc dzimšanas datuma.

    Agrākais pensijas datums ir pirmais mēnesis, kad vienlaikus izpildās vecuma un stāža minimumi (Esošais vai Plānotais scenārijs).

Praktiskais piemērs

Dzimis: 1981-04-13
Stāžs “šobrīd”: 26 gadi un 6 dienas
1) Kā to ievadīt
Ir divi ērti varianti — abi pareizi:

A. Ievadiet stāžu decimālajos gados un kā sākuma datumu norādiet tieši šo pašu “šodienas” datumu.

    6 dienas ≈ 6/365 ≈ 0,016 gadi → ievadiet 26,02 (noapaļojot līdz 2 zīmēm).

    “Aprēķina sākuma datums” = šodien (tas pats brīdis, uz kuru stāžs ir 26,02).

B. Ja gribat pilnīgi bez noapaļošanas:

    Ievadiet 26,016 (ja ļaujat vairāk zīmju aiz komata),

    “Aprēķina sākuma datums” = šodien.

    Rezultāts abos gadījumos būs praktiski vienāds; atšķirība ~1–2 dienas stāžā noapaļošanas dēļ.

2) Kā stāžs krājas tālāk
Pieņemot, ka Turpināšu dienestu = Jā un “Aprēķina sākuma datums” ir, piemēram, 2025-08-06:

    2025-09-06: +1 pilns mēnesis → stāžs ≈ 26,02 + 1/12 = 26,10 gadi.

    2026-08-06: +12 mēneši → stāžs ≈ 27,02 gadi.

    Katrs pilns mēnesis stāža procentu bāzi palielina par ≈0,1667 p.p. (jo +2 p.p. par gadu ⇒ 2/12 = 0,1667).

Ja izvēlaties Turpināšu dienestu = Nē, tad stāžs paliek 26,02 neatkarīgi no datuma.
Ko tas maina attiecībā uz agrāko pensijas datumu

    Esošais regulējums: minimums 50 gadi un 20 gadu stāžs.
    Jums stāžs jau pārsniedz 20 gadus, tādēļ agrākais datums būs 50. dzimšanas diena – 2031-04-13.

    Plānotais regulējums (attiecas uz visiem): no 2027. gada min. vecums un min. stāžs aug par 0,5 gadā (līdz 55 un 25).
    2031. gadā min. vecums būs 52,5 un min. stāžs 22,5.
    Jūsu stāžs (arī ja neturpinātu) jau pārsniedz min. stāžu, tāpēc “pudeles kakls” ir vecums:
    52,5 gadi Jums būs 2033-10-13 → tas arī būs agrākais datums plānotajā scenārijā.

    “Aprēķina sākuma datums” šeit ietekmē precīzu stāžu tieši agrākajā datumā un līdz ar to procentu (jo +2 p.p. par katru pilnu stāža gadu). Taču pats agrākais mēnesis nemainās, kamēr min. stāžs jau ir izpildīts.
