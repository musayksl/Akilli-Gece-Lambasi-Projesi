# Akilli-Gece-Lambasi-Projesi

# Arduino ile Akıllı Gece Lambası Projesi

## Proje Tanımı
Bu proje, LDR (ışık sensörü) yardımıyla ortam ışığını ölçen ve karanlık olduğunda otomatik olarak LED'i yakan bir sistemdir. Gündüzleri ya da ışıklı ortamlarda LED kapalı kalır.

## Kullanılan Malzemeler
- Arduino UNO
- LDR (Işık Sensörü)
- 2 adet LED
- 2 adet 220 Ohm Direnç
- 10K Ohm Direnç
- Breadboard
- Jumper Kablolar

## Devre Bağlantısı
- LDR bir ucu 5V, diğer ucu A0 ve 10K dirençle GND’ye
- LED uzun bacak (anot) → 220 Ohm → D9 pinine  
- LED kısa bacak (katot) → GND

## Kod Açıklaması
Arduino analog pininden (A0) gelen ışık değerine göre karar verir.
```cpp
int ldrPin = A0;
int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int ldrValue = analogRead(ldrPin);
  Serial.println(ldrValue);

  if (ldrValue > 800) {  // Karanlıksa (800 eşik değeri ortamın aydınlığına göre düzenlenebilir )
    digitalWrite(ledPin, HIGH);
  } else {
    digitalWrite(ledPin, LOW);
  }

  delay(200);
}
```

## Lisans
Bu proje MIT Lisansı ile lisanslanmıştır. Daha fazla bilgi için LICENSE dosyasını inceleyin.

> Not: Bu proje, temel bir LDR ışık sensörü uygulamasıdır. Ben bu projeyi hem elektronik pratik yapmak hem de Arduino ile sensör kontrolü öğrenmek amacıyla sıfırdan devre kurarak gerçekleştirdim.












