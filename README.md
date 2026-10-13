# Zero-G Platformer 🚀

🎮 https://dijledogan.github.io/zero-g-platformer/ 

Zero-G Platformer, Phaser 3 oyun motoru ve JavaScript kullanılarak geliştirilmiş, yerçekimsiz ortam fizikleri barındıran 2D retro bir bilimkurgu platform oyunudur. Proje, dinamik sahne yönetimi (Scene Management) ve `sql.js` entegrasyonu ile yerel veritabanı üzerinden skor/kargo takibi yapacak şekilde tasarlanmıştır.

## 🎮 Özellikler

* **Fizik Tabanlı Hareket (Jetpack Mekaniği):** Karakterin yerçekimsiz uzay ortamında süzülmesini sağlayan, Phaser Arcade Physics motoruyla desteklenmiş jetpack itiş sistemi.
* **Nesne Yönelimli Sahne Mimarisi (OOP):** 5 farklı zorluk seviyesi, temel bir `BaseLevel` sınıfından kalıtım (inheritance) alınarak inşa edilmiştir. Bu sayede kod tekrarı önlenmiş ve modüler bir yapı kurulmuştur.
* **Dinamik Zorluk ve Yapay Zeka:** 
  * Belirli rotalarda devriye gezen, hızları ve menzilleri seviyeye göre değişen Otonom Dronlar.
  * Final bölümünde (Level 5) oyuncunun koordinatlarını anlık olarak takip eden (Pathfinding/Tracking) Uzaylı Boss.
* **Yerleşik Veritabanı (SQL.js):** Oyuncunun topladığı kargolar ve anlık skorları tarayıcı belleğinde oluşturulan SQLite veritabanında (`Kargolar` ve `Skorlar` tabloları) tutulur ve oyun bitiminde konsola liderlik tablosu olarak yazdırılır.
* **Durum Koruma (Checkpoint):** Karakter hasar aldığında tüm oyunu sıfırlamak yerine, global state üzerinden güncel skor ve can verisi korunarak sadece bulunulan bölüm baştan başlatılır.

## 🛠 Teknolojiler ve Araçlar

* **Dil:** HTML5, CSS3, JavaScript (ES6+)
* **Oyun Motoru:** Phaser 3 (v3.55.2)
* **Veritabanı:** SQL.js (WebAssembly destekli SQLite)
* **Fizik Motoru:** Phaser Arcade Physics

## 📂 Klasör Yapısı

Proje, istemci tarafında çalışacak statik dosyalar olarak organize edilmiştir:

```text
zero-g-platformer/
├── assets/
│   ├── player/          # Astronot karakterine ait sprite sheet ve animasyon kareleri
│   └── tiles/           # Platform, lazer, kargo kutuları ve arka plan dokuları
└── index.html           # Oyun döngüsü (Game Loop), sahneler ve veritabanı konfigürasyonu
