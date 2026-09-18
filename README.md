# BIST Aracı Kurumlar Pazar Payı ve Rekabet Analizi

Borsa İstanbul (BIST) bünyesinde faaliyet gösteren aracı kurumların işlem hacmi verilerini kullanarak pazar yoğunlaşmasını, rekabet seviyesini ve hacim dağılımını ölçen uçtan uca veri analitiği projesi.

---

## Proje Özeti & İş Problemi
Finansal piyasalarda aracı kurumların pazar gücünü ve sektördeki tekel/oligopol risklerini analiz etmek; sermaye piyasalarının derinliğini ve likidite dağılımını anlamak için kritik öneme sahiptir. 

Bu çalışmada, resmi BIST işlem hacmi verileri işlenerek sektörün rekabet yapısı endüstri standardı iktisadi göstergeler ve istatistiksel segmentasyon yöntemleriyle incelenmiştir.

---

## Kullanılan Teknolojiler & Kütüphaneler
- **Python:** Veri manipülasyonu ve modelleme
- **Pandas & NumPy:** Veri temizleme, agregasyon ve metrik hesaplama
- **Plotly & Matplotlib:** İnteraktif dağılım ve konsantrasyon grafikleri
- **Jupyter Notebook:** Analiz ve dokümantasyon ortamı

---

## Metodoloji & Analitik Yöntemler
1. **Veri Temizleme & Ön İşleme:** Hacim serilerindeki aykırı değerlerin kontrolü, eksik veri analizi ve kurum bazlı gruplama.
2. **Herfindahl-Hirschman Endeksi (HHI):** Pazar yoğunlaşma derecesini ve tekel riskini ölçmek için her kurumun pazar payı karesi toplanarak HHI skoru türetildi.
3. **Pareto (80/20) Analizi:** Kümülatif işlem hacminin %80'ini üreten kritik kurum havuzu belirlendi.
4. **Katmanlı Segmentasyon (Tier 1 / Tier 2 / Tier 3):** İşlem hacmi ve pazar payı ağırlıklarına göre sektör oyuncuları 3 ana segmente ayrıldı.

---

## Temel Bulgular (Key Insights)
- **Konsantrasyon Düzeyi:** Sektörün HHI skoru incelendiğinde pazarın dengeli/rekabetçi bir yapı sergilediği, tek bir aktörün aşırı piyasa hakimiyeti kurmadığı gözlemlendi.
- **Pareto Dağılımı:** Toplam işlem hacminin yaklaşık %80'lik kısmının piyasadaki kurumların ilk %20'si tarafından domine edildiği doğrulandı.
- **Segment Dağılımı:** Kurumlar hacim büyüklüklerine göre Tier 1 (Pazar Liderleri), Tier 2 (Orta Ölçekli Büyüme Odaklılar) ve Tier 3 (Niş/Düşük Hacimliler) olarak sınıflandırıldı.

---

## Proje Yapısı
```text
├── data/               # Ham ve işlenmiş veri setleri
├── notebooks/          # Analiz ve görselleştirme adımlarını içeren Jupyter Notebook
├── figures/            # Üretilen grafik ve görselleştirmeler
├── requirements.txt    # Gerekli Python kütüphaneleri
└── README.md           # Proje dokümantasyonu
