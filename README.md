# japon_kirazcicegi_verianalizi

 Sakura Açma Günü Tahmini Projesi

Bu projede Japonya’daki kiraz çiçeklerinin (sakura) tam açma gününü tahmin etmeye çalıştım. Veriyi biraz temizledim, birkaç model denedim ve en iyi sonucu hangisi veriyor diye inceledim.

 Veri Hakkında

Veri seti 1953 ile 2023 yılları arasında Japonya’daki çeşitli şehirlerdeki sakura açma tarihlerini içeriyor.  
Ben bu tarihleri yılın kaçıncı günü olduğunu hesaplayarak çalıştım (örneğin 100. gün = 10 Nisan gibi).

 Neler Yaptım?

- Veriyi long formata çevirdim (her satır bir şehir ve yıl olacak şekilde).
- Tarihleri yılın kaçıncı günü formatına dönüştürdüm.
- Train, validation ve test seti olarak üçe böldüm (zaman sırasına göre).
- 3 tane basit model denedim:
  - Ortalama tahmini (herkese aynı günü verir)
  - Şehre göre ortalama tahmini (her şehir için kendi ortalaması)
  - Linear regression (yıla göre değişim var mı diye)
- Sonuçları MAE (Mean Absolute Error) ile karşılaştırdım.
- Bir de grafik çizdim, görsel olarak farkı daha iyi anlaşılıyor.

## Sonuçlar

Üç farklı model denedim ve her birinin tahmin başarısını MAE (ortalama mutlak hata) ile karşılaştırdım.

Model 1: Herkese aynı günü tahmin eden genel ortalama modeli. MAE değeri yaklaşık 16.3 gün çıktı. Yani ortalama olarak 16 gün sapma yaptı.

Model 2: Her şehir için ayrı ayrı geçmiş ortalamayı kullanan modeldi. Bu model en başarılısı oldu. MAE değeri sadece 5.3 gün.

Model 3: Yıla göre tahmin yapan linear regression modeli. MAE değeri 14.5 gün oldu, yani genel ortalamadan biraz daha iyi ama şehir bazlı model kadar başarılı değil.

Sonuç olarak, şehir bazlı ortalama modeli açık ara en iyi sonucu verdi.

 Kullanılanlar

- Python
- Pandas
- scikit-learn
- Matplotlib
- Jupyter Notebook

 Not

Bu proje tamamen öğrenme amacıyla yapılmıştır. Daha gelişmiş modellemeler ve iklim verileri eklenerek çok daha iyi sonuçlar elde edilebilir.
