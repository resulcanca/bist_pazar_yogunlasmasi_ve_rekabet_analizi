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

Kurulum ve İnceleme
Depoyu yerel ortamınıza klonlayın:

Bash
git clone [https://github.com/resulcanca/regional-economic-intelligence.git](https://github.com/resulcanca/regional-economic-intelligence.git)
cd regional-economic-intelligence
SQL sorgularını çalıştırmak için SQLite ortamını başlatın:

Bash
sqlite3 data/processed/economic_intelligence.db < sql/30_business_queries.sql
Dashboard'u görüntülemek için powerbi/regional_intelligence.pbix dosyasını Power BI Desktop üzerinde açın.

İletişim
Resul Canca — LinkedIn • Kaggle • Medium

E-posta: resulcanca@gmail.com
