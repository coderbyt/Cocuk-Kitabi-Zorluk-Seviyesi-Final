# Cocuk-Kitabi-Zorluk-Seviyesi-Final
Cocuk-Kitabi-Zorluk-Seviyesi Final
README – Metin Benzerliği Analizi Projesi
Proje Amacı
Bu projede, bir kitap başlıkları veri seti üzerinde farklı metin vektörleştirme teknikleriyle (TF-IDF ve Word2Vec) benzerlik analizleri yapılmış, her modelin performansı karşılaştırmalı olarak değerlendirilmiştir.

Çalışma Adımları ve Açıklamalar
1. Ortam Hazırlığı
Çalışmalar Google Colab ortamında yürütülmüştür. Gerekli Python kütüphaneleri (pandas, nltk, spacy, gensim, scikit-learn) yüklenmiştir. NLTK ve spaCy modelleri indirilerek metin ön işlemede kullanılmıştır.

2. Veri Yükleme ve Ön İzleme
“books.csv” adlı veri seti yüklenmiş, başlıklar incelenmiştir. Veri setinin genel yapısı analiz edilmiştir.

3. Ön İşleme (Preprocessing)
Veri setindeki başlıklar:

Küçük harfe dönüştürülmüş,

Noktalama ve özel karakterlerden arındırılmış,

Stopword’ler (gereksiz sık kelimeler) temizlenmiş,

Hem “lemmatization” (köküne indirgeme, anlamı bozmadan) hem de “stemming” (kelimeyi kök haline indirgeme) uygulanmıştır.

Bu adımlar sonucunda iki ayrı temiz veri seti (lemmatized_books.csv ve stemmed_books.csv) oluşturulmuştur.

4. Vektörleştirme
TF-IDF: Temizlenmiş veri setlerinde her başlık için TF-IDF (Term Frequency – Inverse Document Frequency) vektörleri oluşturulmuştur. Bu sayede her başlık matematiksel olarak bir vektörle temsil edilmiştir.

Word2Vec: Hem lemmatized hem de stemmed veriler için, farklı parametrelerde toplam 16 adet Word2Vec modeli (CBOW/SkipGram, pencere boyutu 2/4, vektör boyutu 100/300) eğitilmiştir. Her başlık, ilgili Word2Vec modeline göre ortalama kelime vektörüne dönüştürülmüştür.

5. Benzerlik Hesaplama
Giriş başlığı olarak veri setinden bir örnek başlık seçilmiştir.

Seçilen başlığın TF-IDF veya Word2Vec vektörü ile veri setindeki diğer başlıkların vektörleri arasında cosine similarity (kosinüs benzerliği) hesaplanmıştır.

Her model için giriş başlığına en çok benzeyen ilk 5 başlık ve benzerlik skorları elde edilmiştir.

6. Değerlendirme ve Karşılaştırma
Her modelin sıraladığı ilk 5 benzer başlık, tablo halinde sunulmuştur.

Benzerlik skorları ve sıralamaları değerlendirilmiş; her öneri için “anlamsal benzerlik” açısından 1–5 arası puan verilmiş, ortalamaları alınmıştır.

Farklı modellerin ilk 5 önerileri arasındaki sıralama tutarlılığı Jaccard benzerlik katsayısı ile 18x18 matris şeklinde analiz edilmiştir.

7. Sonuçlar
Word2Vec modellerinin, özellikle yüksek boyut ve geniş pencere ile eğitilen SkipGram ve CBOW mimarilerinin, anlamsal benzerlikte en başarılı sonucu verdiği gözlemlenmiştir.

TF-IDF modellerinin, yüzeysel benzerlikte iş görse de anlamca zayıf öneriler sunduğu belirlenmiştir.

Model parametrelerinin (window, embedding boyutu, mimari) başarıda belirleyici olduğu, hem sıralama tutarlılığının hem de ortalama benzerlik puanlarının analizlerle ortaya konmuştur.

8. Genel Öneriler
Anlamsal benzerlik gerektiren metin uygulamalarında Word2Vec modellerinin (özellikle SkipGram, büyük vektör boyutu ve pencere ile) tercih edilmesi önerilir.

Sadece anahtar kelime veya yüzeysel arama için TF-IDF yöntemi yeterli olabilir.

Model seçimi, veri setinin büyüklüğüne, metinlerin uzunluğuna ve kullanım amacına göre yapılmalıdır.

Projeyi Kendi Ortamınızda Çalıştırmak İçin
Google Colab veya Jupyter Notebook ortamında, ilgili dosyaları yükleyin.

Gerekli kütüphaneleri yükleyin ve veri ön işlemeden itibaren yukarıdaki adımları sırasıyla izleyin.

Sonuç dosyalarını ve analizleri, ödev raporunuzda kullanmak üzere kaydedin.
