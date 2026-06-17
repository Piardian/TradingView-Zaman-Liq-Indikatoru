# TrendFlowing Pro - TradingView Zaman ve Likidite Indikatoru

Bu repo, TradingView icin Pine Script v6 ile hazirlanmis `TrendFlowing Pro` indikatorunu icerir. Indikator; seans zamanlarini, onceki gun seviyelerini, 1H/4H high-low alanlarini ve cift tepe/cift dip yapilarini grafik uzerinde daha okunabilir hale getirmek icin tasarlanmistir.

## Projenin Amaci

Finansal grafiklerde zaman bazli piyasa davranisini takip etmek, ozellikle Asya, Londra ve New York seanslarinda olusan fiyat araliklarini gormek icin onemlidir. Bu indikatorun amaci, TradingView grafikleri uzerinde kritik seans bolgelerini ve likidite seviyelerini otomatik olarak isaretleyerek teknik analiz surecini daha duzenli ve hizli hale getirmektir.

Indikator tek basina alim-satim sinyali uretmekten cok, kullanicinin kendi stratejisini uygularken takip etmek isteyebilecegi zaman araliklarini, onceki mum seviyelerini ve olasi formasyon bolgelerini gorsellestirir.

## Ana Ozellikler

- Asya seansi kutusu
- Londra killzone kutusu
- New York killzone kutusu
- Turkiye saati bazli zaman hesaplama
- Yaz/kis saati kaymasi icin manuel ayar
- Onceki gun high/low seviyeleri: `PDH` ve `PDL`
- Onceki 4H mum high/low seviyeleri
- Onceki 1H mum high/low seviyeleri
- 15 dakika ve uzeri zaman dilimlerinde cift tepe/cift dip tespiti
- Renkleri ve gosterimleri kullanici tarafindan degistirilebilir ayarlar
- Grafik ustunde kutu, cizgi ve etiketlerle sade gorsellestirme

## Dosyalar

- `trendflowing-pro.pine`: TradingView Pine Script v6 indikator kodu.

## TradingView'e Yukleme

1. TradingView hesabinizda bir grafik acin.
2. Alt menuden `Pine Editor` bolumune girin.
3. `trendflowing-pro.pine` dosyasinin icerigini kopyalayin.
4. Pine Editor icindeki mevcut kodu silip bu kodu yapistirin.
5. `Save` ile kaydedin.
6. `Add to chart` secenegiyle indikatoru grafige ekleyin.

## Zaman Dilimi Mantigi

Indikator, saat hesaplamalarinda `Europe/Istanbul` zaman dilimini kullanir. Turkiye saati UTC+3 oldugu icin Asya, Londra ve New York seanslari Turkiye saatine gore takip edilir.

Varsayilan seans ayarlari:

| Bolge | Varsayilan Zaman |
| --- | --- |
| Asya | 02:00 - 10:00 |
| Londra | 10:00 - 13:00 |
| New York | 15:30 - 18:30 |

`Kis Saati` ayari aktif edildiginde Londra ve New York seanslari 60 dakika kaydirilir. Bu ayar, yaz/kis saati farklarinin grafikte daha dogru temsil edilmesi icin eklenmistir.

## Seans Kutulari

Asya, Londra ve New York seanslari grafik uzerinde renkli kutularla gosterilir. Her kutu, ilgili seans boyunca olusan en yuksek ve en dusuk fiyat araligini takip eder.

Bu bolum ozellikle:

- seans acilislarini gormek,
- seans ici fiyat araligini izlemek,
- Londra ve New York killzone davranisini ayirt etmek,
- zaman bazli likidite analizini desteklemek

icin kullanilabilir.

Not: Seans kutulari sadece 1 saatten kucuk zaman dilimlerinde gosterilecek sekilde ayarlanmistir.

## PDH ve PDL Seviyeleri

`PDH` onceki gunun en yuksek seviyesini, `PDL` ise onceki gunun en dusuk seviyesini ifade eder. Indikator bu seviyeleri kisa kesik cizgiler ve etiketlerle gosterir.

Bu seviyeler teknik analizde sik kullanilir; fiyat onceki gunun yuksegine veya dusugune yaklastiginda piyasa tepkisi incelenebilir.

## 4H ve 1H High/Low Seviyeleri

Indikator, onceki 4 saatlik ve onceki 1 saatlik mumun high/low seviyelerini dinamik olarak takip eder.

Bu seviyeler:

- daha kisa vadeli likidite bolgelerini gormek,
- mum bazli destek/direnc alanlarini takip etmek,
- fiyat seviyesinin ihlal edilip edilmedigini izlemek

icin kullanilabilir.

Kodda bu seviyeler ihlal edildiginde ilgili cizgilerin temizlenmesi icin kontrol mekanizmasi bulunur. Boylece grafikte gecerliligini kaybetmis seviyelerin kalabalik olusturmasi azaltilir.

## Cift Tepe ve Cift Dip Tespiti

Indikator, 15 dakika ve uzeri zaman dilimlerinde pivot yapilarini inceleyerek cift tepe ve cift dip benzeri formasyonlari yakalamaya calisir.

Bu mekanizma su ayarlara dayanir:

- `Pivot Lookback`: Pivotun kac bar geriye bakilarak hesaplanacagi.
- `Tolerans (%)`: Iki tepe veya iki dip arasindaki kabul edilebilir fiyat farki.
- `Maks. Bar Mesafesi`: Iki pivot arasindaki en fazla bar mesafesi.
- `Min. Geri Cekilme (%)`: Formasyonun anlamli sayilmasi icin gereken minimum geri cekilme.

Cift tepe tespitinde iki benzer yuksek seviye, aradaki geri cekilme ve tepe seviyesinin kirilip kirilmadigi kontrol edilir. Cift dip tespitinde de benzer sekilde iki dip, aradaki tepki ve dip seviyesinin korunup korunmadigi izlenir.

## Ayarlanabilir Parametreler

Indikator icinde kullanici tarafindan degistirilebilen ayarlar bulunur:

- seanslarin acilip kapatilmasi,
- seans kutu renkleri,
- baslangic ve bitis saatleri,
- PDH/PDL cizgi rengi,
- 1H ve 4H high/low renkleri,
- cift tepe/dip renkleri,
- pivot hassasiyeti,
- tolerans ve geri cekilme yuzdesi.

Bu sayede indikator farkli piyasalara, farkli zaman dilimlerine ve farkli islem stillerine gore uyarlanabilir.

## Teknik Bilgiler

- Dil: Pine Script
- Surum: Pine Script v6
- Platform: TradingView
- Grafik tipi: Overlay indikator
- Maksimum kutu/cizgi/etiket limiti: 500
- Lisans bildirimi: Kod basinda Mozilla Public License 2.0 notu bulunur.

## Kullanim Senaryolari

Bu indikator asagidaki analiz yaklasimlari icin yardimci olabilir:

- seans bazli fiyat hareketi takibi,
- likidite bolgesi analizi,
- onceki gun seviyelerinin izlenmesi,
- 1H ve 4H referans seviyeleriyle intraday analiz,
- cift tepe/dip formasyon kontrolu,
- ICT/killzone benzeri zaman odakli analiz calismalari.

## Onemli Uyari

Bu repo ve indikator egitim, analiz ve gorsellestirme amaciyla paylasilmistir. Buradaki kod herhangi bir finansal tavsiye, alim-satim onerisi veya kesin sinyal sistemi olarak degerlendirilmemelidir.

Finansal piyasalarda islem yapmak risk icerir. Indikatoru kullanmadan once kendi testlerinizi yapmaniz, farkli piyasa kosullarinda kontrol etmeniz ve risk yonetimi uygulamaniz gerekir.

## Kisa Ozet

`TrendFlowing Pro`, TradingView grafiklerinde seans zamanlarini, likidite seviyelerini ve belirli teknik formasyonlari tek panelde takip etmeyi kolaylastiran Pine Script tabanli bir analiz aracidir. Amaci karar vermek yerine, grafigi daha okunabilir hale getirerek kullanicinin kendi stratejisini daha duzenli uygulamasina yardimci olmaktir.
