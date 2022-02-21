# Programın kapanması için sys modülünü çağırıyoruz.
import sys
# Otobüsün koltuklarını ekleyeceğimiz boş bir liste oluşturuyoruz.
koltuklar = []


class Yolcu():
    # Yolcu sınıfına ait olacak öznitelikleri tanımlıyoruz.
    def __init__(self,isim = None,soyisim = None,cinsiyet = None):
        self.isim = isim
        self.soyisim = soyisim
        self.cinsiyet = cinsiyet
    # Her öznitelik için get ve set methotlarını tanımlıyoruz.
    def get_isim(self):
        return self.isim
    def get_soyisim(self):
        return self.soyisim
    def get_cinsiyet(self):
        return self.cinsiyet
    def set_isim(self,isim):
        self.isim = isim
    def set_soyisim(self,soyisim):
        self.soyisim = soyisim
    def set_cinsiyet(self,cinsiyet):
        self.cinsiyet = cinsiyet
    # Sınıfın nesnelerini string haline getimesi içi __str__() metotu kullanıyoruz. 
    # Bir nesne üzerinde print() veya str() fonksiyonu çağrıldığında çağrılır.
    # Birnevi __str__ ile print() override (üstü yazılır) edilir.
    def __str__(self):
        return str(self.isim)+ " " +str(self.soyisim)+ " , " +str(self.cinsiyet)



# Yolcu sınıfının özniteliklerini Koltuk sınıfına ekleyerek miras(inherit) ediyoruz.
class Koltuk(Yolcu):
    # Koltuk sınıfına ait olacak öznitelikleri tanımlıyoruz.
    def __init__(self,koltukno,koltukDurum = False,yolcu = None):
        self.koltukno = koltukno
        self.koltukDurum =False
        self.yolcu = None
    # Her öznitelik için get ve set methotlarını tanımlıyoruz.
    def get_koltukno(self):
        return self.koltukno
    def get_koltukDurum(self):
        return self.koltukDurum
    def get_yolcu(self):
        return self.yolcu
    def set_koltukno(self,koltukno): 
        self.koltukno = koltukno
    def set_koltukDurum(self,koltukDurum):
        self.koltukDurum = koltukDurum
    def set_yolcu(self,yolcu):
        self.yolcu = yolcu
    # Sınıfın nesnelerini string haline getimesi için __str__() metotu kullanıyoruz. 
    # Bir nesne üzerinde print() veya str() fonksiyonu çağrıldığında çağrılır.
    # Birnevi __str__ ile print() override (üstü yazılır) edilir.
    def __str__(self):
        return str(self.koltukno)+" , "+str(self.koltukDurum)


# Koltuk sınıfının özniteliklerini Otobus sınıfına ekleyerek Yolcu(), Koltuk() 
# fonksiyonlarını miras(inherit) ediyoruz.
class Otobus(Koltuk):
    # Otobus sınıfına ait olacak öznitelikleri tanımlıyoruz.
    def __init__(self,plaka=str("28 GRU 454"),KoltukSayısı=int(42)):
        self.plaka = plaka
        self.KoltukSayısı = KoltukSayısı
        
    # Her öznitelik için get methotunu tanımlıyoruz.
    def get_plaka(self):
        return self.plaka
    def get_KoltukSayısı(self):
        return self.KoltukSayısı
    def set_plaka(self,plaka):
        self.plaka = plaka
    def set_KoltukSayısı(self,KoltukSayısı):
        self.KoltukSayısı = KoltukSayısı
    # Sınıfın nesnelerini string haline getimesi için __str__() metotu kullanıyoruz. 
    # Bir nesne üzerinde print() veya str() fonksiyonu çağrıldığında çağrılır.
    # Birnevi __str__ ile print() override (üstü yazılır) edilir.
    def __str__(self):
        return str(self.plaka)+""+str(self.KoltukSayısı)

    # Herhangi bir koltuğa yapılacak rezerve için method tanımlıyoruz.
    def koltukRezerve(self):
        a = input(str("\nİsim: "))
        b = input(str("\nSoyisim: "))
        c = str(input("\nCinsiyet (E/K): ")).upper()
        # Cinsiyet için girilen karakteri sınırladım.
        if c == "E" or c == "K":
            print()
        assert (c == "E" or c == "K"),("Lütfen belirtilen harfleri girin!")
        d = int(input("Koltuk no: "))
        # Eğer girilen koltuk sayısı verilenden küçük veya büyük ise hata veriyoruz.
        if i < 1 or i > 42:
            print()
        assert (i > 1 or i < 42),("Lütfen menüde belirtilen kişi sayısına göre Koltuk Numarası giriniz!")
        
        
        # Yolcu kişisi girilmeden önce koltuğun dolu olup olmadığına bağlı olarak yapılacak işleme karar veriyoruz.
        if koltuklar[d-1].get_yolcu() == None:
            print(ANSI.background(0) + ANSI.color_text(31) + ANSI.style_text(1) +"\n--> Rezerve ediliyor...")
            # Girilen Koltuk No'sunun index'ine girilen kullanıcı tarafından girilen isim, 
            # soyisim, cinsiyet, koltukno değerlerini set methotunu kullanarak atıyoruz.
            koltuklar[d-1].set_isim(a)
            koltuklar[d-1].set_soyisim(b)
            koltuklar[d-1].set_cinsiyet(c)
            koltuklar[d-1].set_koltukno(d)
            # Set methotu ile Koltuk sınıfında olan koltukdurum = False niteliğini, True ile değiştiriyoruz.
            koltuklar[d-1].set_koltukDurum(True)
            # Set methotu ile Koltuk sınıfında olan yolcu = None niteliğini, Dolu ile değiştiriyoruz.
            koltuklar[d-1].set_yolcu("Dolu")
        else:
             print(ANSI.background(0) + ANSI.color_text(31) + ANSI.style_text(1) +"\n!|Bu koltuk dolu, lütfen başka koltuk seçiniz.|!")

    # Girilen tüm yolcuları belirlemek için method tanımlıyoruz.
    def printYolcular():
        # Koltuklar listesinde bulunan x objesi ile koltukDurum niteliği True olan yolcuları seçip printliyoruz.
        for x in koltuklar:
            if x.get_koltukDurum() == True:
                print("\nKoltuk no: " +str(x.get_koltukno())+", "+str(x.get_isim())+" "+str(x.get_soyisim())+", "+str(x.get_cinsiyet()))

    # Yolcuları ve boş koltukları belirlemek için method tanımlıyoruz.
    def printKoltuklar():
        # Koltuklar listesinde bulunan x objesi ile koltukDurum niteliği True ya da False olan yolcuları seçip printliyoruz.
        for x in koltuklar:
            if x.get_koltukDurum() == True:
                print("\n"+str(x.get_koltukno())+"-"+str(x.get_koltukDurum())+", "+str(x.get_isim())+" "+str(x.get_soyisim())+", "+str(x.get_cinsiyet()))
            elif x.get_koltukDurum() == False:
                print("\n"+str(x.get_koltukno())+"-"+str(x.get_koltukDurum())+", "+str(x.get_yolcu()))

    # Boş koltukları belirlemek için method tanımlıyoruz.
    def printBosKoltuklar():
        # Koltuklar listesinde bulunan x objesi ile koltukDurum niteliği False olan yolcuları seçip printliyoruz.
        for x in koltuklar:
            if x.get_koltukDurum() == False:
                print("\n"+str(x.get_koltukno())+"-"+str(x.get_koltukDurum())+", "+str(x.get_yolcu()))

# Plaka'yı printlemek için Otobus sınıfna ait bir nesne tanımlıyoruz.
y = Otobus() 

# Koltuklar listesine 42 adet koltuk atıyoruz.
for i in range(1,43):
    koltuklar.append(Koltuk(i))
    
    
# Terminali renklendirmek için ANSI sınıfı tanımlıyoruz.
class ANSI():
    def background(code):
        return "\33[{code}m".format(code=code)
    def style_text(code):
        return "\33[{code}m".format(code=code)
    def color_text(code):
        return "\33[{code}m".format(code=code)

# Programı başlatması için main() methodu tanımlıyoruz.
def main():
    tercih = 0
    print( ANSI.background(7) + ANSI.color_text(31) + ANSI.style_text(4) + "\n\n{}".format(y.get_plaka()) + ANSI.background(0) + 
              ANSI.color_text(34) + ANSI.style_text(1) +" plakalı "+
              ANSI.background(7) + ANSI.color_text(31) + ANSI.style_text(4) + "{} kişilik".format(y.get_KoltukSayısı()) + ANSI.background(0) + 
              ANSI.color_text(34) + ANSI.style_text(1) +" otobüsümüze hoşgeldiniz...")
    # Programı döngüye sokar.
    while True:
     try:
        print(ANSI.background(0) + ANSI.color_text(37) + ANSI.style_text(1) +"""\n
               MENU 
               """ 
    + ANSI.background(0) + ANSI.color_text(33) + ANSI.style_text(1) +
      """
      1- Rezervasyon yap
      2- Bütün yolcuları görüntüle
      3- Bütün koltukları görüntüle
      4- Bütün boş koltukları görüntüle
      5- Çıkış
        """)
        # Verilen tercihler arasında seçilene göre atama yapıyoruz.
        tercih = int(input(ANSI.background(0) + ANSI.color_text(36) + ANSI.style_text(1) +"Tercihinizi seçin: "))
        if tercih == 1:
            Otobus.koltukRezerve(Yolcu())
        elif tercih == 2:
            Otobus.printYolcular()
        elif tercih == 3:
            Otobus.printKoltuklar()
        elif tercih == 4:
            Otobus.printBosKoltuklar()
        elif tercih == 5:
            sys.exit()
        # Seçilen tercih verilenlerden küçük ya da büyük ise hata verir.
        if tercih > 5 or tercih < 1:
             raise ValueError
     except ValueError:
         print(ANSI.background(0) + ANSI.color_text(31) + ANSI.style_text(1) +"Gösterilen sayılardan birini giriniz!")
main()
