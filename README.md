# Soru 1 – Sayı Analizi
sayi = int(input("Bir sayı giriniz: "))

if sayi > 0:
    durum = "Pozitif"
elif sayi < 0:
    durum = "Negatif"
else:
    durum = "Sıfır"

if sayi % 2 == 0:
    tek_cift = "Çift"
else:
    tek_cift = "Tek"

print(durum, tek_cift)


# Soru 2 – Harf Frekansı
kelime = input("Bir kelime giriniz: ")
frekans = {}
for harf in kelime:
    frekans[harf] = frekans.get(harf, 0) + 1
print(frekans)


# Soru 3 – Şifre Kontrolü
sifre = input("Bir şifre giriniz: ")

uzunluk = len(sifre) >= 8
buyuk_harf = any(ch.isupper() for ch in sifre)
rakam = any(ch.isdigit() for ch in sifre)

if uzunluk and buyuk_harf and rakam:
    print("Şifre geçerli.")
else:
    print("Şifre geçersiz. Koşulları kontrol edin.")


# Soru 4 – Liste İşlemleri
liste = [12, 4, 9, 25, 30, 7, 18]
ortalama = sum(liste) / len(liste)
buyukler = [x for x in liste if x > ortalama]
print("Ortalama:", ortalama)
print("Ortalamadan büyük sayılar:", buyukler)


# Soru 5 – Nested Loop (Desen)
for i in range(1, 6):
    print("*" * i)


# Soru 6 – While Döngüsü
toplam = 0
adet = 0
while True:
    sayi = int(input("Bir sayı giriniz (çıkmak için 0): "))
    if sayi == 0:
        break
    toplam += sayi
    adet += 1

if adet > 0:
    print("Toplam:", toplam)
    print("Ortalama:", toplam / adet)
else:
    print("Hiç sayı girilmedi.")


# Soru 7 – Palindrom Kontrolü
kelime = input("Bir kelime giriniz: ")
if kelime == kelime[::-1]:
    print("Palindrom")
else:
    print("Değil")


# Soru 8 – List Comprehension
sonuc = [x**2 for x in range(1, 101) if x % 3 == 0 and x % 5 == 0]
print(sonuc)


# Soru 9 – String İşlemleri
cumle = input("Bir cümle giriniz: ")
kelimeler = cumle.split()
yeni_cumle = " ".join([kelime.capitalize() for kelime in kelimeler])
print(yeni_cumle)


# Mini Proje – Film Yorumu Analizi
yorumlar = []
adet = int(input("Kaç yorum gireceksiniz? "))

for i in range(adet):
    yorum = input(f"{i+1}. yorumu giriniz: ")
    yorumlar.append(yorum)

uzunluklar = [len(y) for y in yorumlar]
iyi_sayisi = sum(1 for y in yorumlar if "iyi" in y.lower())
en_uzun = max(yorumlar, key=len)
en_kisa = min(yorumlar, key=len)
ortalama_uzunluk = sum(uzunluklar) / len(yorumlar)

print("Toplam yorum sayısı:", len(yorumlar))
print('"iyi" geçen yorum sayısı:', iyi_sayisi)
print("En uzun yorum:", en_uzun)
print("En kısa yorum:", en_kisa)
print("Ortalama uzunluk:", ortalama_uzunluk)
