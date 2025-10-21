# Enflasyon_Tahmin
Çok Değişkenli Zaman Serisi Enflasyon Tahmin Modeli
Proje Hakkında

Bu proje, Türkiye ekonomisindeki farklı göstergeleri kullanarak TÜFE (Tüketici Fiyat Endeksi) aylık enflasyonunu tahmin etmeyi amaçlamaktadır.
Veri seti EVDS ve diğer kaynaklardan alınmış ekonomik göstergeler (ÜFE, döviz, altın, petrol, M3 para arzı, İTO enflasyonu vb.) kullanılarak hazırlanmıştır.

Veri Hazırlama

Gecikmeli ve hareketli ortalama (HO) değişkenler eklenmiştir.

TÜFE için B ve C endeksleri alınmıştır (enerji ve gıda hariç, fiyat dalgalanmalarından arındırılmış daha stabil alt endeksler).

Tüm değişkenler, modelin öğrenebileceği şekilde aynı zaman aralığına hizalanmıştır.

Kullanılan Modeller

LassoLarsCV – LARS algoritması ile L1 regülarizasyonu kullanan cross-validation modeli.

LassoLarsIC – LARS algoritması ve bilgi kriterleri (AIC/BIC) ile optimal α seçimi.

ElasticNetCV – Lasso ve Ridge karışımı regülarizasyon, yüksek korelasyonlu değişkenler için dengeli.

Tüm modeller, eğitim ve test seti ayrımı yapılarak performans değerlendirilmiştir.

Performans Ölçütleri

R²: Modelin TÜFE varyansını ne kadar açıkladığını gösterir.

RMSE: Tahminlerin ortalama hatasını gösterir, gerçek değerlerden sapmayı ölçer.

Örnek Tablo:

Model	        R2 Train  R2 Test  RMSE
LassoLarsCV	  0.65	    0.77	   1.28
LassoLarsIC  	0.64	    0.76	   1.28
ElasticNetCV	0.66	    0.78	   1.25

Değerler birbirine yakın çıkmış, bu modellerin tutarlı ve stabil olduğunu gösterir.
