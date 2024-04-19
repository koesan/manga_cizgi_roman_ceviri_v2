# Manga ve Çizgi Roman Çevirici ve Renklendirici

Bu proje, yapay zeka kullanarak farklı dillerdeki mangaları veya çizgi romanları herhangi bir dile çevirir ve renksiz mangaları renklendirir. Proje, çeşitli aşamalardan oluşmaktadır ve farklı işlevleri gerçekleştirmek için çeşitli kütüphaneleri kullanır.
Renkli manga veya çizgi romanları çevirir, renksiz manga veya çizgi romanları çevirir ve istenilirse renklendirebilir.

Kodda yapılacak değişiklik ile farklı diller arası çevri işlemide gereçekleştirilebilinir.

# ÖZELLİKLER


* OCR

Resimlerdeki metinleri çıkarmak için OCR kullanılmaktadır. Bu projede PaddleOCR kütüphanesi tercih ettim. 
Paddleocr kütüphanesi diğer ocr kütüphanelerinden (EasyOCR, Pytesseract) daha hızlı ve daha iyi sonuç verdiği için projede kullanmaya karar verdim.

* Çevri 

Çevri için öncelikle transformırs kütüphanesi ile farklı dil modellerini çevri için kullanmayı planlıyordum. Testlerim sonucunda istediğim başarıda sonuç vermediği için deepl api kullanmaya karar verdim. 
Deepl api kullanmak için  https://www.deepl.com/en/pro-api sayfasından kaydolun ve anahtarınızı alın.
Kodda 13. satırdaki api = "APİ-KEY" kısmına anahtarınızı ekleyin

* İnpanting

Resme çevrilmiş metinleri eklemek için önce resim üzerindeki metinlerin kaldırılması gerekiyor. Bunun için simple-lama-inpainting kütüphanesi ile metinlerin üzerine kareler yerleştirerek yapay zekanın kapalı kısımları doldurması sağlanıyor.

* Renklendirme

siyah beyaz resimleri renklendirmek için https://github.com/qweasdd/manga-colorization-v2 projeden yararladnım. bu projeyi kendi koduma uyarlıyarak renksiz resimleri renklendirdim.
kodda 12. satırdaki renklendir = 1 ise reimleri renklendirir. renklendir = 0 ise resimleri renklendirmez.



# Gereksinimler

deepl==1.17.0

opencv-python==4.6.0.66

paddleocr==2.7.3

paddlepaddle==2.6.1

simple-lama-inpainting==0.1.2

torch==2.2.2

torchvision==0.17.2

tqdm==4.66.2

textwrap3==0.9.2 

transformers==4.35.2



# İnput:

![1](https://github.com/koesan/manga_cizgi_roman_ceviri/assets/96130124/f729cc10-4a13-465b-9327-e766f5776625)

![2](https://github.com/koesan/manga_cizgi_roman_ceviri/assets/96130124/bf31bd33-5af8-4563-9d94-67ad22351ef3)

![4](https://github.com/koesan/manga_cizgi_roman_ceviri/assets/96130124/5cd9b5a3-41b3-4ecf-ac2a-5254c6dfb949)




# Output:

![1](https://github.com/koesan/manga_cizgi_roman_ceviri/assets/96130124/4ec53fd6-b182-4668-b7ab-3440b8e4446e)

![2](https://github.com/koesan/manga_cizgi_roman_ceviri/assets/96130124/4e4d36d3-37de-4bce-8d4b-1642b899db09)

![4](https://github.com/koesan/manga_cizgi_roman_ceviri/assets/96130124/3d9e217d-27a4-4af6-a915-15ed7c2fb7e6)
