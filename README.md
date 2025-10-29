# football-player-perf
Polynomial Regression ve Ridge Regularization kullanarak futbol verilerinde non-lineer ilişkileri modelleyen performans analizi projesi.

⚽️ Futbolcu Performansı Tahmini — Polinom Regresyon (2024–2025)
🎯 Proje Özeti

Bu proje, Football Players Stats 2024–2025 veri setini kullanarak futbolcuların sezon performanslarını (📊 Goal + Assist toplamı) tahmin etmeyi amaçlar.
Amaç, oyuncuların istatistiksel verileri üzerinden non-lineer ilişkileri yakalayıp, performanslarını matematiksel olarak modellemektir.

⚙️ Kullanılan Modeller ve Adımlar

🔧 Veri Hazırlığı

age sütunundaki eksikler ortalama ile dolduruldu

pass_accuracy (Cmp%) değerleri pozisyona göre ortalama ile tamamlandı

Kolon isimleri sadeleştirildi ve Python uyumlu hale getirildi


📊 EDA (Veri Analizi)

Korelasyon (Heatmap) analizi ile anlamlı ilişkiler incelendi

expected_goals, expected_assists, progressive_passes, shots_on_target değişkenlerinin performansla güçlü ilişkisi gözlemlendi


🧠 Modelleme

Polynomial Regression (degree = 2) ile doğrusal olmayan ilişkiler modellendi

Ridge Regression (alpha = 500) kullanılarak modelin ezberlemesi (overfitting) engellendi

📈 Sonuçlar
Metrik	Değer
🎯 R² Skoru	0.9798
📉 MSE	Çok düşük
⚙️ MAE	~0.02

Model, futbolcu performansının yaklaşık %98’ini doğru tahmin etmektedir.

🎨 Görselleştirmeler
🔹 Korelasyon Haritası
sns.heatmap(df_col.corr(), annot=True, cmap="coolwarm")

🔹 3D Scatter Grafiği
ax.scatter(
    df_col["age"],
    df_col["minutes_played"],
    df_col["goal_assist_total"],
    c=df_col["goal_assist_total"],
    cmap="rainbow",
    marker='o',
    alpha=0.7
)


Grafik, yaş–oynadığı dakika–performans ilişkisini renk skalasıyla göstermektedir 🌈

🧩 Kullanılan Özellikler

age

minutes_played

expected_goals

expected_assists

pass_accuracy

progressive_passes

shots_on_target

goal_assist_total (hedef değişken)


💡 Çıkarımlar

expected_goals ve expected_assists performansı en çok etkileyen değişkenlerdir

progressive_passes ve shots_on_target oyuncunun katkısını artıran faktörlerdir

age ile performans arasında ters-U biçimli (non-lineer) bir ilişki gözlemlenmiştir


🧰 Kullanılan Kütüphaneler

pandas

numpy

seaborn

matplotlib

scikit-learn


🏁 Sonuç

Bu proje, futbol istatistiklerinden non-lineer performans ilişkilerini ortaya çıkarmayı amaçlayan bir çalışmadır.
Polynomial Regression + Ridge Regularization kombinasyonu sayesinde model, yüksek doğrulukta sonuçlar üretmiştir.

“İyi bir model sadece tahmin etmez — anlam kazandırır.” ⚙️

📂 Veri Seti: Kaggle — Football Players Stats 2024–2025
👤 Hazırlayan: Emrehan Şephanelioğlu
