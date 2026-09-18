# Türkiye Regional Economic Intelligence (Karar Destek Modeli)

Türkiye'nin 26 NUTS-2 ekonomik bölgesine ait TÜİK ve TCMB makroekonomik göstergelerini konsolide eden, SQL tabanlı analitik modelleme ve Power BI gösterge paneli ile bölgesel yatırım ve büyüme potansiyelini ölçen karar destek projesi.

---

## Proje Özeti & İş Problemi
Bölgesel kalkınma dinamikleri, gelir dağılımı ve barınma/kira maliyeti baskısı gibi faktörler yatırımların coğrafi dağılımında kritik rol oynar. Ancak kamuya açık verilerin parçalı ve farklı formatlarda olması, bütünleşik bir karar destek mekanizması kurmayı zorlaştırır.

Bu projede TÜİK ve TCMB EVDS veri kaynakları bir araya getirilerek ilişkisel bir veri tabanında (SQLite) modellenmiş; ileri düzey SQL sorguları ile 30 kritik iş sorusu yanıtlanmış ve karar alıcılar için türetilmiş bir **Ekonomik Çekicilik Skoru** geliştirilmiştir.

---

## Kullanılan Teknolojiler & Beceriler
- **Veri Modelleme & Analiz:** SQL (SQLite) — CTE (Common Table Expressions), Window Functions (`RANK`, `DENSE_RANK`, `NTILE`, `PERCENT_RANK`), Subqueries, Multi-table JOINs, Aggregations
- **Veri Manipülasyonu & ETL:** Python, Pandas, NumPy
- **İş Zekası & Görselleştirme:** Power BI, DAX (KPI Hesaplamaları, Dinamik Filtreleme), İleri Düzey Excel
- **Versiyon Kontrolü:** Git, GitHub

---

## Analitik Metodoloji & SQL Mimarisi
1. **Veri Konsolidasyonu & Modelleme:** 26 NUTS-2 bölgesi için nüfus, kişi başı GSYH, işsizlik, konut satışları ve tüketici fiyat endeksi gibi göstergeler tekilleştirilerek ilişkisel şemaya dönüştürüldü.
2. **İleri Seviye SQL Sorgu Tasarımı:**
   - Pencere fonksiyonları (Window Functions) ile bölgeler arası kümülatif pay ve yüzdelik dilim (percentile) hesaplamaları.
   - CTE yapıları ile bölgesel büyüme oranlarının periyodik kıyaslanması.
3. **Ekonomik Çekicilik Skoru (Metrik Türetme):** Gelir artış ivmesi, sanayi/ticaret hacmi ile konut ve kira baskısı ağırlıklandırılarak her bölge için normalize edilmiş bir çekicilik skoru formüle edildi.
4. **Power BI Dashboard:** Karar vericilerin bölgeleri filtreleyebileceği, metrikleri dinamik olarak karşılaştırabileceği interaktif arayüz kurgulandı.

---

## Temel Bulgular & İçgörüler
- **Bölgesel Ayrışma:** Batı metropollerinde kişi başı gelir yüksek olmasına rağmen konut ve maliyet baskısı neticesinde göreli çekicilik skorunun orta Anadolu üretim havzalarına doğru kaydığı tespit edildi.
- **Konsantrasyon Analizi:** Ekonomik katma değerin ve finansal hacmin belirli bölgelerde kümelendiği `NTILE` ve `PERCENT_RANK` analizleriyle doğrulandı.
- **İş Kararı Desteği:** Türetilen skorlama modeli; bölgesel yatırım dağılımı, depo/tesis lokasyon seçimi ve hedef pazar analizleri için doğrudan referans metrik haline getirildi.

---

## Proje Dizini
```text
├── data/
│   ├── raw/                 # TÜİK ve TCMB kaynaklı ham veriler
│   └── processed/           # SQLite veritabanı ve temizlenmiş tablolar
├── sql/
│   ├── schema.sql           # Tablo yapıları ve ilişkiler
│   └── 30_business_queries.sql # Window functions ve CTE içeren analitik sorgular
├── powerbi/
│   └── regional_intelligence.pbix # Power BI Dashboard dosyası
├── notebooks/
│   └── etl_pipeline.ipynb   # Veri temizleme ve dönüştürme adımları
├── figures/                 # Dashboard ekran görüntüleri ve SQL çıktıları
├── requirements.txt         # Python kütüphane bağımlılıkları
└── README.md                # Proje dokümantasyonu
```

## Hızlı Başlangıç & İnceleme

| Adım | İşlem | Detay |
| :--- | :--- | :--- |
| **1. Repoyu Al** | `git clone https://github.com/resulcanca/regional-economic-intelligence.git` | Proje dosyalarını yerel ortama çeker. |
| **2. Veritabanı** | `data/processed/economic_intelligence.db` | SQLite üzerinde doğrudan incelenebilir. |
| **3. SQL Analizleri** | `sql/30_business_queries.sql` | Window functions & CTE analiz sorgularını içerir. |
| **4. Raporlama** | `powerbi/regional_intelligence.pbix` | Power BI Desktop ile panoyu tam ekran açın. |

---

## İletişim & Ağ

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Resul_Canca-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/resulcanca)
[![GitHub](https://img.shields.io/badge/GitHub-resulcanca-181717?style=flat&logo=github&logoColor=white)](https://github.com/resulcanca)
[![Kaggle](https://img.shields.io/badge/Kaggle-resulcanca-20BEFF?style=flat&logo=kaggle&logoColor=white)](https://kaggle.com/resulcanca)
[![Medium](https://img.shields.io/badge/Medium-@resulcanca-000000?style=flat&logo=medium&logoColor=white)](https://medium.com/@resulcanca)
[![Email](https://img.shields.io/badge/E--posta-resulcanca@gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:resulcanca@gmail.com)
