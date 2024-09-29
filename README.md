# proje
# CO2 Emisyon Takip Programı

def emisyon_hesapla(emisyonlar):
    """Yıllık emisyon değişimini hesaplar."""
    if len(emisyonlar) < 2:
        return None

    ilk_yil = emisyonlar[0]
    son_yil = emisyonlar[-1]
    değişim = son_yil - ilk_yil
    yüzdelik_değişim = (değişim / ilk_yil) * 100

    return değişim, yüzdelik_değişim

def main():
    print("Küresel Isınma Emisyon Takip Programı")
    emisyonlar = []

    while True:
        try:
            veri = input("Yıllık CO2 emisyonunu girin (çıkmak için 'q' girin): ")
            if veri.lower() == 'q':
                break
            emisyon = float(veri)
            emisyonlar.append(emisyon)
        except ValueError:
            print("Lütfen geçerli bir sayı girin.")

    if len(emisyonlar) >= 2:
        değişim, yüzdelik_değişim = emisyon_hesapla(emisyonlar)
        print(f"Toplam Değişim: {değişim} ton")
        print(f"Yüzdelik Değişim: {yüzdelik_değişim:.2f}%")
    else:
        print("Yeterli veri sağlanmadı.")

if __name__ == "__main__":
    main()
