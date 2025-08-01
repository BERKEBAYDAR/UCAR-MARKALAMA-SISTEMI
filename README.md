# UÇAR Markalama Sistemi

UÇAR Markalama Sistemi, hareketli bir üretim hattında senkronize bir şekilde ürün üzerine işaretleme/etiketleme yapılmasını sağlayan prototip bir sistemdir. Encoder tabanlı konum takibi ve servo motor kontrollü markalama mekanizması ile yüksek doğrulukta zamanlama hedeflenmiştir.

## Projenin Amacı

Bu proje, uçar makas sistemine benzer bir yapı ile ürünün konumuna bağlı olarak gerçek zamanlı markalama işlemini gerçekleştirmeyi amaçlar. 

## Kullanılan Donanımlar

| Bileşen | Model | Açıklama |
|--------|-------|----------|
| **PLC** | GLC-296 | HSC destekli, Pulse-DIR sinyalleriyle uyumlu |
| **Servo Motor** | GSM80F-0750W-20B-30D-KLY | 750W AC servo motor |
| **Servo Sürücü** | GSS3-2RS | Pulse-DIR uyumlu sürücü |
| **Encoder** | OPKON PRI 50 | Pulse-DIR çıkışlı, konum bilgisini sağlar |
| **HMI** | (Opsiyonel) | GLC serisi uyumlu GMT HMI |


## Kontrol Yapısı

- Encoder’dan gelen PULSE-DIR sinyalleri GLC-296 PLC üzerindeki HSC girişine bağlanmıştır.
- PLC, ürün konumunu bu sinyalleri sayarak belirler.
- Markalama yapılacak konuma ulaşıldığında PLC, servo sürücüye tetik verir.
- Servo motor, sisteme bağlı markalama aparatıyla etiketleme işlemini gerçekleştirir.

> Not: Sistemde Siemens S7-1200 PLC başlangıçta düşünülmüş ancak röle çıkışlı olduğu ve PULSE-DIR ya da analog çıkış veremediği için GLC-296 PLC ile değiştirilmiştir.

## Yazılım

- Programlama dili: **Ladder Diagram **
- Geliştirme ortamı: **GMT Suite**
- Kodlama mantığı: Encoder sayımı, eşik kontrolü, zamanlama ve motor tetikleme.

## Sistem Akışı

1. Ürün ray üzerinde ilerler.
2. Encoder’dan gelen sinyaller HSC ile sayılır.
3. Belirli bir pozisyonda servo motora tetik verilir.
4. Servo motor dönerek etiketleme işlemini gerçekleştirir.
5. Sistem sıfırlanır ve bir sonraki ürün için döngü yeniden başlar.


## Test & Sonuç

- Encoder ile yapılan konum takibi sayesinde yüksek hassasiyet elde edilmiştir.
- Servo sistemin hızlı tepkisi sayesinde etiketleme işlemi gecikmesiz gerçekleştirilmiştir.
- Pulse-DIR sinyal yapısı sayesinde sistemin kontrolü net ve kararlı olmuştur.


