# TR
# Taş Kağıt Makas Oyunu
Karanlık temalı, animasyonlu, kullanıcı karşısında bilgisayarın rastgele seçim yaptığı taş-kağıt-makas oyunu. Skorlar localStorage'a kaydedilir; sayfa yenilendiğinde puan tablosu korunur.

## Canlı Önizleme

[Proje önizleme.](https://dursunkokturk.github.io/JavaScript-Project-Game-Rock-Paper-Scissor/)

## Özellikler

- Bilgisayara Karşı Oyna — Bilgisayar her turda Math.random() ile rastgele seçim yapar
- Anlık Sonuç Alanı — Kazandın / Kaybettin / Berabere durumu; seçilen emojiler ve açıklama metniyle birlikte gösterilir
- Pop Animasyonu — Her hamle sonrası sonuç kutusu scale ile animasyona girer
- Puan Tablosu — Sen, Bilgisayar ve Beraberlik skorları üst kısımda anlık güncellenir
- localStorage Kalıcılığı — Üç skor ayrı anahtarlarla kaydedilir; sayfa yenilendiğinde kaybolmaz
- Oyunu Sıfırla — Tüm skorlar sıfırlanır, localStorage güncellenir ve sonuç alanı temizlenir
- Duyarlı Buton Düzeni — Mobilsde butonlar alt alta, tablette ve masaüstünde yan yana dizilir
- CSS Değişkenleri ile Tema — Tüm renkler :root üzerinden yönetilir; kolay özelleştirme

## Oyun Kuralları

| Kullanıcı      | Bilgisayar  | Sonuç      |
| -------------- |-------------| -----------|
| Taş            | Makas       | Kazandın   |
| Kağıt          | Taş         | Kazandın   |
| Makas          | Kağıt       | Kazandın   |
| Herhangi       | Aynısı      | Beraberlik |
| Diğer durumlar | —           | Kaybettin  |


## Duyarlı Düzenler

| Ekran    | Genişlik         | Buton Düzeni                              |
| -------- |------------------| ------------------------------------------|
| Mobil    | 375px Varsayılan | Alt alta, yatay (ikon + metin yan yana)   |
| Tablet   | ≥ 767px          | Yan yana, dikey (ikon üstte, metin altta) |
| Masaüstü | ≥ 1024px         | Yan yana, daha büyük boyutlar             |

## Teknolojiler
 
| Teknoloji  | Açıklama                                                                        |
| ---------- |---------------------------------------------------------------------------------|
| HTML5      | Semantik sayfa yapısı                                                           |
| CSS3       | CSS değişkenleri, Flexbox, @keyframes, @media sorguları                         |
| JavaScript | Oyun mantığı, DOM manipülasyonu, localStorageGoogle FontsSpace Mono, Bebas Neue |

## Proje Yapısı
rock-paper-scissor/ <br>
├── index.html <br>
└── assets/ <br>
    ├── css/ <br>
    │   └── style.css <br>
    └── js/ <br>
        └── rock-paper-scissor.js <br>

## Kurulum
Proje herhangi bir bağımlılık gerektirmez.
bash# Repoyu klonlayın
git clone https://github.com/kullanici-adi/rock-paper-scissor.git

### Proje klasörüne girin
cd rock-paper-scissor

### index.html dosyasını tarayıcıda açın
open index.html

#### Not: 
rock-paper-scissor.js dosyası defer ile yüklenir; DOM hazır olmadan önce çalışmaz.


## Tasarım Detayları

- Tema: Tam karanlık (dark-only)
- Renk Paleti (CSS değişkenleri):

    - --bg: #0a0a0f — Sayfa arka planı
    - --surface: #13131a — Kart ve buton yüzeyi
    - --accent: #e8ff00 — Neon sarı (kullanıcı skoru, kazanma durumu, hover)
    - --accent2: #ff3c6e — Neon pembe (bilgisayar skoru, kaybetme durumu)
    - --muted: #666 — İkincil metin ve beraberlik durumu


- Fontlar: Bebas Neue (başlık ve skorlar) · Space Mono (buton ve detay metni)
- Arka Plan Efekti: İki renkte radial gradient ile hafif ışıma
- Animasyon: pop keyframe ile scale(1.08) zıplama efekti (0.25s)
