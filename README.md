# Projekt_Task_Manager

# zadání č. 1
ukoly = []

# Funkce pro přidání nového úkolu
def pridat_ukol():
    nazev = input("Zadejte název úkolu: ")
    popis = input("Zadejte popis úkolu: ")
    ukol = {"nazev": nazev, "popis": popis}
    ukoly.append(ukol)
    print(f"Úkol '{nazev}' byl přidán.\n")

# Funkce pro zobrazení všech úkolů
def zobrazit_ukoly():
    if len(ukoly) == 0:
        print("Žádné úkoly nejsou k dispozici.\n")
    else:
        print("Seznam úkolů:")
        for i in range(len(ukoly)):
            u = ukoly[i]
            print(f"{i+1}. {u['nazev']} - {u['popis']}")
        print()

# Funkce pro odstranění úkolu
def odstranit_ukol():
    zobrazit_ukoly()

    if len(ukoly) == 0:
        return

    cislo = input("Zadejte číslo úkolu, který chcete odstranit: ")

    if cislo.isdigit():
        cislo = int(cislo)
        if 1 <= cislo <= len(ukoly):
            smazany = ukoly.pop(cislo - 1)
            print(f"Úkol '{smazany['nazev']}' byl odstraněn.\n")
        else:
            print("Neplatné číslo úkolu.\n")
    else:
        print("Zadejte platné číslo.\n")

# Hlavní menu programu
def hlavni_menu():
    while True:
        print("Správce úkolů - Hlavní menu")
        print("1. Přidat nový úkol")
        print("2. Zobrazit všechny úkoly")
        print("3. Odstranit úkol")
        print("4. Konec programu")

        volba = input("Vyberte možnost (1-4): ")

        if volba == "1":
            pridat_ukol()
        elif volba == "2":
            zobrazit_ukoly()
        elif volba == "3":
            odstranit_ukol()
        elif volba == "4":
            print("Program končí.")
            break
        else:
            print("Neplatná volba. Zkuste to znovu.\n")

# Spuštění programu
hlavni_menu()
