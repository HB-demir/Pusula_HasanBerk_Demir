# Pusula_HasanBerk_Demir hasanberkdemir01@gmail.com
## 📌 Proje Özeti

Bu proje, bir hastaneden elde edilen veriler üzerinde **Uygulama Süresi (dakika)** değişkenini tahmin etmeye yönelik veri hazırlama ve özellik mühendisliği çalışmasıdır.  
Amaç, hastaların demografik bilgileri, kronik hastalık durumları, tedavi bilgileri, alerjileri, başvurdukları bölümler ve uygulama yapılan bölgeler gibi faktörleri düzenleyerek temiz bir veri seti oluşturmak ve daha sonraki modelleme adımlarına uygun hale getirmektir.  

### 1. Veri Temizleme ve Düzenleme  
- Eksik değerler `"Bilinmiyor"` etiketi ile dolduruldu.  
- Veri tutarlılığı için yazım hataları düzeltildi (örn. *Volteren → Voltaren*, *Hiportiroidizm → Hipotiroidizm*).  
- Çok az sayıda görülen nadir kategoriler **“Diğer”** altında toplandı.  
- Tekrarlayan bilgiler HastaNo bazında birleştirildi ve eksik değerlerin hastanın diğer kayıtlarından tamamlanması sağlandı.  

### 2. Özellik Mühendisliği  
- **Sayısal değişkenler**: `Yas`, `TedaviSuresi` doğrudan kullanıma hazır hale getirildi.  
- **Kategorik değişkenler**:  
  - **One-Hot Encoding**: `Cinsiyet`, `KanGrubu`, `KronikHastalik` (multi-label → multi-hot), `Bolum`, `Alerji`, `UygulamaYerleri`  
  - **Binary Encoding**: `Uyruk` (Türkiye vs Diğer)  
- Bu işlemler sonucunda her kategorik özellik uygun şekilde dönüştürüldü ve veri seti analiz/modelleme için hazır hale getirildi.  

Sonuç olarak, proje kapsamında sağlık verilerindeki eksiklikler giderilmiş, kategorik çeşitlilik düzenlenmiş ve veri standardizasyonu sağlanmıştır. Bu aşamalar sayesinde veri seti, daha sonraki analiz ve tahmin modelleri için güçlü bir temel oluşturmuştur.  
## 🚀 Kurulum ve Çalıştırma

```bash
# 1) Depoyu Klonlayın
git clone https://github.com/<kullanici-adi>/<repo-adi>.git
cd <repo-adi>

# 2) Sanal Ortam Oluşturun (Önerilir)
python -m venv .venv

# macOS / Linux
source .venv/bin/activate

# Windows
.\.venv\Scripts\activate

# 3) Bağımlılıkları Yükleyin
pip install --upgrade pip
pip install -r requirements.txt

# 4) Veri Dosyasını Yerleştirin
# Ham CSV dosyanızı data/raw/ klasörüne koyun (örn. data/raw/hastane.csv)
# Büyük dosyaları .gitignore içine eklemeyi unutmayın

# 5) Çalıştırma
# Jupyter Notebook ile
jupyter notebook

# veya Python Script ile
python main.py
