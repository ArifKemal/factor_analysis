# GEMINI.md - Proje Talimatları ve Bağlamı

Bu dosya, bu projede çalışacak olan Gemini CLI ve diğer geliştiriciler için temel rehber ve bağlam sağlar.

## Proje Genel Bakışı
**Factor-Exposure Analyzer**, yarı iletken (semiconductor) ve yapay zeka sektöründeki hisse senetlerinin piyasa faktörlerine duyarlılığını ölçen bir finansal veri bilimi projesidir. **Fama-French 3 Faktör Modeli** (Market, Size, Value) temel alınarak Çoklu Doğrusal Regresyon (OLS) analizi yapar.

### Temel Teknolojiler
- **Dil:** Python 3.x
- **Veri Analizi:** Pandas, Numpy
- **İstatistiksel Modelleme:** Statsmodels (OLS)
- **Görselleştirme:** Matplotlib, Seaborn
- **Platform:** Jupyter Notebook (.ipynb)

## Çalıştırma ve Kurulum
Projenin çalıştırılması için aşağıdaki adımlar izlenmelidir:

1.  **Bağımlılıkların Yüklenmesi:**
    ```bash
    pip install -r requirements.txt
    ```
2.  **Notebook'un Çalıştırılması:**
    `Factor_Exposure_Analyzer.ipynb` dosyasını Jupyter ortamında açın ve tüm hücreleri sırayla çalıştırın.

## Proje Yapısı ve Mimari
Analiz süreci dört ana adımdan oluşur:
1.  **Adım 1 - Veri Üretimi:** Sentetik piyasa faktörleri ve hisse getirileri üretilir (`factor_exposure_data.csv`).
2.  **Adım 2 - Veri İşleme:** Fazla getiriler (Excess Returns) hesaplanır.
3.  **Adım 3 - OLS Regresyon Motoru:** `statsmodels` kullanılarak her hisse için Beta katsayıları hesaplanır.
4.  **Adım 4 - Görselleştirme:** Hesaplanan faktör duyarlılıkları karşılaştırmalı grafiklerle sunulur.

## Geliştirme Kuralları
- **Veri Kaynağı:** Proje şu an için statik/sentetik (mock) veri setleri üzerinden çalışır. Canlı API entegrasyonu planlanmamıştır.
- **Regresyon Denklemi:** $R_i - R_f = \alpha + \beta_{Mkt}(R_m - R_f) + \beta_{SMB}SMB + \beta_{HML}HML + \epsilon$
- **Görselleştirme Stili:** Seaborn `whitegrid` teması ve `viridis` paleti tercih edilir.
- **Dosya Yönetimi:** Üretilen veri setleri (`.csv`) ve geçici dosyalar `.gitignore` ile hariç tutulmalıdır.

## Anahtar Dosyalar
- `Factor_Exposure_Analyzer.ipynb`: Ana uygulama ve analiz notebook'u.
- `requirements.txt`: Gerekli kütüphane listesi.
- `README.md`: Projenin GitHub üzerindeki görünen yüzü ve hızlı başlangıç rehberi.
- `results.png`: Analiz sonuçlarının görsel özeti.
