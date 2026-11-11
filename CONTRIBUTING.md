# Birlikte çalışma

1. Başlamadan bir issue seç; neyin tamamlanınca biteceğini yaz ve görevi üstlen.
2. Güncel main üzerinden `feat/12-profil` veya `fix/23-mesaj` gibi iş başına dal aç.
3. Bir PR tek konu çözsün. İlgisiz dosyaları değiştirme.
4. PR içinde ilgili issue, yapılan değişiklik ve nasıl denendiğini belirt.
5. Bir arkadaş kodu incelesin; seçilen otomatik kontroller geçince squash merge yapın.
6. Aynı dosyada çalışacaksanız önce haberleşin. Haftada bir çalışan demo gösterin.

## Bitti tanımı
Kabul ölçütü karşılandı; hata/boş durumları ele alındı; ilgili doğrulama yapıldı;
README değişen kurulum adımlarını anlatıyor ve PR incelendi.

## Veriler
`.env`, parolalar, servis anahtarları ve gerçek kullanıcı veri dışa aktarımları commit edilmez.
Gerekli değişken adları seçilen teknolojiyle `.env.example` içinde belgelenecek.
Mesaj ve profil erişimi yalnız arayüzde değil sunucuda/veritabanında denetlenir.

## Ekip düzeni önerisi
İkişerli üç çalışma alanı: profil/keşfet, eşleşme/mesaj, altyapı/kalite.
Roller sabit olmak zorunda değil; her işi yapanın dışında bir kişi inceler.
