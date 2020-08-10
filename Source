#pelissä vaadittavat alkutiedot
import random
import time
pelaajaEnergia = 100
zombiEnergia = 70
hamisEnergia = 85
lohisEnergia = 175
damageLista = []
k = 0
e = 0
#syötteen tarkistus
def tarkistus(syote):
    while True:
        try:
            ase = int(input("valitse ase (1, 2, 3): "))
        except ValueError:
            print("Anna _numero_!!!")
            continue
        if ase <= 3 and ase > 0:
            return ase            
        else:
            print("anna numero 1, 2, 3")
#aseiden määrittely
def aseenValinta(ase0):    
    #kirves
    if ase0 == 1:  
        damage = random.randint(25,40)
        print("hyökkäsit kirveellä")
        print("teit viholliseen ", damage , " vahinkoa")
        print("")
        return damage
    #musketti   
    if ase0 == 2:
        hutiLaukaus = random.randint(1,4)
        print("hyökkäsit musketilla")
        if hutiLaukaus >= 3:
            damage = 100
            print("teit viholliseen ", damage, " vahinkoa")
            print("")
            return damage
        else:
            damage = 0
            print("ammuit ohi")
            print("")
            return damage
    #soihtu    
    if ase0 == 3:
        damage = 60
        print("hyökkäsit soihdulla")
        print("teit viholliseen " , damage , " vahinkoa")
        print("")
        return damage
#vihollisten aseet   
#zombie
def hampaat(ase4):
    damage = random.randint(5, 10)
    print("Zombie puri sinuun " , damage , " vahinkoa")
    print("")
    return damage
#hämis
def seitti(ase5):
    damage = random.randint(10, 25)
    print("Hämähäkki ampui sinuun seittiä " , damage , " edestä vahinkoa")
    print("")
    return damage
#lohikäärme
def lohis(ase6):
    damage = random.randint(0,30)
    if damage == 0:
        print("sinä väistit, lohikäärme ampui ohi")
        return damage
    print("lohikäärme ampui tulta sinua päin " , damage , " edestä vahinkoa")
    print("")
    return damage
#-------------------------------------------------------------------------------------------------------------------------------------
#peli alkaa introlla
#--------------------------------------------------------------------------------------------------------------------------------------
print("Tervetuloa Ritari Ässän seikkailuun")
print("")
nimi = input("Hei pelaaja, annatko nimesi: ")
print("")
while True:
    valmis = input("""Meidän tehtävänä on pelastaa Prinsessa pulasta. Paha noita on kaapannut Prinsessan 
luolaan josta meidän tulee pelastaa hänet. Sinä -> """ + nimi + """ <- olet minun aseenkantajani. Oletko valmis? (k/e): """)  
    if valmis == "k":
        print("Hyvä, seikkailu alkaa")
        print("")
        break
    if valmis == "e":
        print("")
        print("Ei sillä väliä, seikkailu alkaa kuitenkin")
        print("")
        break
    else:
        print("-------------------------")
        print("Anna kirjain 'e' tai 'k'")
        print("-------------------------")
time.sleep(2)
#infoa pelin toiminnasta
print("""Saavumme luolan sisäänkäynnille. Sisällä törmäämme vastustajiin ja sinun tehtäviin kuuluu valita minulle sopiva ase
Aseina ovat kirves(damage 25-40), musketti pistooli(damage 0 tai 100), soihtu (damage aina 60). Taistelu käydään vuoron perään annettavilla iskuilla 
kunnes toinen on kuollut""")
print("")
print("Olemme kulkeneet luolassa jo jonkin aikaa, yhtäkkiä eteemme astuu Zombie. Anna minulle jokin ase!")
#while ehto ohjelman lopettamiseksi jos pelaaja kuolee
while pelaajaEnergia >= 1:
#taistelu zombieta vastaan
    while True:       
        #syötteen tarkistus ja aseen valinta
        print("------------------------")
        ase = tarkistus(1)
        print("------------------------")
        #damage zombieen ilmoittaminen
        damage = aseenValinta(ase)
        damageLista.append(damage)
        zombiEnergia = zombiEnergia - damage
        print("zombien energia on: ", zombiEnergia)
        time.sleep(3)
        print("")
        if zombiEnergia <= 0:
            print("zombie kuoli")
            break
        #damage pelaajaan ilmoittaminen
        damage = hampaat(1)
        pelaajaEnergia = pelaajaEnergia - damage
        print("Ritarin energia on: ", pelaajaEnergia)
        if pelaajaEnergia < 0:
            break  
        time.sleep(2)
    #jos pelaaja kuoli lopeta peli
    if pelaajaEnergia <= 0:
        break
    #tarina jatkuu..    
    print("")
    print("Hienoa! tapoit zombien. Matka jatkuu syvemälle luolaan.. vastaan alkaa tulla hämähäkin seittiä.")
    print("")
    time.sleep(2) 
    print("VARO!")
    print("")
    time.sleep(3)
    print("hämähäkki hyökkää sinua kohti ja osuu sinuun")
    print("")
    time.sleep(3)
    #taistelu hämistä vastaan
    damage = seitti(1)
    pelaajaEnergia = pelaajaEnergia - damage
    print("Ritarin energia on : ", pelaajaEnergia)
    while True:
        print("hyökkäät hämistä vastaan")
        print("-----------------------")
        #syötteen tarkistus ja aseen valinta
        ase = tarkistus(1)
        print("-----------------------")
        #damage vähentäminen vihollistesta
        damage = aseenValinta(ase)
        damageLista.append(damage)
        hamisEnergia = hamisEnergia - damage
        print("hämiksen energia on: ", hamisEnergia)
        time.sleep(2)
        if hamisEnergia <= 0:
            print("hämis kuoli")
            break
        #damage pelaajaan ilmoittaminen
        damage = seitti(1)
        pelaajaEnergia = pelaajaEnergia - damage
        print("Ritarin energia on: ", pelaajaEnergia)
        if pelaajaEnergia < 0:
            break
        time.sleep(2)
    #jos pelaaja kuoli lopeta peli    
    if pelaajaEnergia <= 0:
        break    
    #taistelu lohikäärmettä vastaan
    time.sleep(3)
    print("")
    print("Olemme selvinneet jo pitkälle, hyvin toimittu! Ritarin energia on: ", pelaajaEnergia )
    print("")
    time.sleep(4)
    print("Saavumme isoon luolaan.. Luolan pimeässä nurkassa kiiltää kaksi isoa silmää ja ilma on usvainen")
    print("")
    time.sleep(4)
    print("Jättimäinen lohikäärme hyökkää teitä kohti")
    print("")
    while True:
        print("hyökkäät lohikäärmettä vastaan")
        #syötteen tarkistus ja aseen valinta
        print("-------------------------------")
        ase = tarkistus(1)
        print("-------------------------------")
        #damage vähentäminen vihollisesta
        damage = aseenValinta(ase)
        damageLista.append(damage)
        lohisEnergia = lohisEnergia - damage
        print("lohikäärmeen energia on: ", lohisEnergia)
        time.sleep(3)
        if lohisEnergia <= 0:
            print("lohikäärme kuoli")
            break
        #damage pelaajaan ilmoittaminen
        damage = lohis(1)
        pelaajaEnergia = pelaajaEnergia - damage
        print("Ritarin energia on: ", pelaajaEnergia)
        if pelaajaEnergia <= 0:
            break
        time.sleep(3)
    #jos pelaaja kuoli lopeta peli
    if pelaajaEnergia <= 0:
        break     
    if zombiEnergia < 0 and lohisEnergia < 0 and hamisEnergia < 0:
        break
#pelin päättäminen
#jos voititte
print("")
print("")
time.sleep(3)
if pelaajaEnergia > 1:
    print("te voititte ja pelastitte prinsessan")
    #printataan pelissä tehty damage
    print("teit pelissä damagea: ", sum(damageLista), " edestä" )
    #pakollinen for :)
    for i in range(5):
        print("hiphiphurraa!")
        time.sleep(1)
#jos hävisitte
if pelaajaEnergia < 1:
    print("Ritari Ässä kuoli, peli päättyi")
input("Paina enter lopettaaksesi pelin")
#pelissä ei välttämättä täyty 10*input ehtoa riippuen random tekijästä. kuitenkin jos käyttää aina ase(3) soihtua niin ehto täyttyy.
#muilla aseilla ehto ei välttämättä täyty riippuen satunnaisesta tekijästä. peli on optimoitu tuohon 10*inputtiin soihdulla, muilla aseilla 
#pelistä olisi tullut turhan pitkä pienentämällä damage rangea.



