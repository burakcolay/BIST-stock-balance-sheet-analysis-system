# Bilanco-AI

BIST hisseleri için yapay zeka destekli bilanço analiz sistemi.

## Nasıl kullanılır?

1. Yeni bir Claude session'ı aç.
2. Analiz etmek istediğin hisseyi söyle, örneğin:

   > THYAO hissesini analiz et

   İstersen Fintables veya KAP'tan aldığın bilanço görüntüsünü/PDF'ini de ekle — sistem onu esas alır. Vermezsen web'den son bilanço verilerini kendisi arar.

3. Sistem [`bilanco-prompt.md`](bilanco-prompt.md) dosyasındaki talimata göre çalışır:
   - Hissenin daha önce analizi yapılmışsa `hisseler/[KOD]/` klasöründeki şirket profilini ve önceki analizleri okuyup devamlılık kurar.
   - İlk analizse önce şirketi araştırıp profilini oluşturur.
   - Derinlemesine ama öğretici bir bilanço analizi yapar, sonucu `hisseler/[KOD]/analizler/YYYY-QX.md` olarak kaydeder ve commit + push eder.

## Klasör yapısı

```
hisseler/
  [KOD]/               # Örn: THYAO, ASELS
    profil.md          # Şirket profili: ne iş yapar, sektörü, rakipleri
    analizler/
      YYYY-QX.md       # Çeyreklik bilanço analizleri (örn: 2026-Q1.md)
    notlar.md          # Kullanıcı sorularına verilen cevaplar ve değerlendirmeler
```

## Notlar

- Analizler yatırım tavsiyesi değildir; değerlendirme çerçevesi sunar.
- Her analiz kaynağını belirtir; teyit edilemeyen veriler açıkça işaretlenir.
