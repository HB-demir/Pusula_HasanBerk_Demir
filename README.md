# Pusula_HasanBerk_Demir hasanberkdemir01@gmail.com
## 📌 Proje Özeti
Bu proje, hastane verileri kullanılarak **Uygulama Süresi (dakika)** değişkenini tahmin etmek amacıyla geliştirilmiştir.  
Amaç, hasta özellikleri ve tedavi bilgilerini kullanarak uygulama süresini öngörmektir.  

---

## ⚙️ Kullanılan Adımlar

1. **Veri Temizleme**
   - Eksik değerler `"Bilinmiyor"` etiketi ile dolduruldu.
   - Yazım hataları düzeltildi (ör. *Volteren → Voltaren*, *Hiportiroidizm → Hipotiroidizm*).
   - Nadir kategoriler **“Diğer”** altında toplandı.

2. **Özellik Mühendisliği**
   - Sayısal değişkenler: `Yas`, `TedaviSuresi`
   - Kategorik değişkenler:
     - One-Hot Encoding: `Cinsiyet`, `KanGrubu`, `KronikHastalik` (multi-label → multi-hot), `Bolum`, `Alerji`, `UygulamaYerleri`
     - Binary Encoding: `Uyruk` (Türkiye vs Diğer)

3. **Modelleme**
   - Temel **Lineer Regresyon** modeli kuruldu.
   - Hedef değişken: **UygulamaSuresi** (dakika cinsinden).

---
