# AkbAI

Bu projede TensorFlow ve Keras kütüphanelerini kullanarak balık resimlerini sınıflandıran bir derin öğrenme modeli oluşturulmuştur. İlk olarak gerekli kütüphaneler yükleniyor ve resimlerin bulunduğu dizinden tüm resim dosyaları toplanıyor. Burada glob kullanılarak belirli uzantılara sahip resimler bulunuyor ve bunlar daha sonra modelde kullanılmak üzere bir listeye alınıyor.

Resim veri seti üzerinde veri artırma teknikleri uygulanıyor. Bu teknikler arasında döndürme, parlaklık ayarlama, zoom yapma ve yatay çevirme gibi işlemler yer alıyor. Bu sayede model, resimlerdeki çeşitlilikten daha iyi öğreniyor ve genelleme kabiliyeti artıyor. Veri artırma işlemi ImageDataGenerator ile yapılıyor ve veri seti eğitim ve doğrulama olarak ikiye bölünüyor.

Model, Keras’ın Sequential yapısıyla oluşturuluyor. Modelde birden fazla gizli katman bulunuyor ve bu katmanlar her seferinde daha az nöron içeriyor. Her katmandan sonra BatchNormalization ve Dropout uygulanarak modelin daha stabil ve aşırı öğrenmeden uzak olması hedefleniyor. Çıkış katmanında softmax aktivasyon fonksiyonu kullanılarak her resim için olasılık dağılımı elde ediliyor.

Model eğitilirken, eğitim sürecini optimize eden çeşitli callback'ler kullanılıyor. EarlyStopping ile model, doğrulama kaybı düştüğünde eğitimi erken durdurabiliyor. Ayrıca, ReduceLROnPlateau ile doğrulama kaybına göre öğrenme oranı ayarlanıyor. Eğitim süresi boyunca doğruluk ve kayıp değerleri izleniyor.

Eğitim tamamlandıktan sonra model test verisiyle test ediliyor. Performans ölçümleri arasında doğruluk, sınıflandırma raporu ve karışıklık matrisi yer alıyor. Sonuçlar, modelin test verisinde ne kadar doğru tahmin yaptığını gösteriyor ve karışıklık matrisi ile yanlış sınıflandırmalar görselleştiriliyor.
