# basari_olcer
2.proje denemem
sorular=[{"Türkiyenin baskenti neresidir?":"Ankara"},{"En çok nüfus olan il neresidir?":"Istanbul"},{"Fizik sayisal bir ders midir?":"Evet"}]
def quiz():
    while True:

        k=input("Lütfen kullanici adi soyadi giriniz: ")
        if k=="q":
            break
        else:

            dogru_sayisi=0
            for soru in sorular:
                print(list(soru.keys()))
                cevap="Ankara"
                a=input("Lütfen doğru cevabi yaziniz: ").lower().strip().capitalize()
                b=list(soru.values())[0]
                if a==b:

                    print("doğru")
                    dogru_sayisi+=1
                else:
                    print("hata")
            print(dogru_sayisi)
            if dogru_sayisi>=2:
                with open("basari.txt","a",encoding="utf-8") as l:
                    l.write("\n"+k)
            else:
                with open("basarisizlar.txt","a",encoding="utf-8") as l:
                    l.write("\n"+k)
            
quiz()
