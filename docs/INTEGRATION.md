# Gerçek uygulamayı birleştirme kontrolü

Görev seçimi serbesttir; ilk yerel teslimler birbirini beklemez. #13 entegrasyon takibidir:
stub sürücüyle hemen başlanır ama gerçek ortak demo doğrulanmadan #13 ve milestone kapanmaz.

## Sorumluluk
#4 sahibi uygulama/workspace entegrasyonunu, #13 sahibi ortak demo ve eksiklerin takibini üstlenir.
Her modül sahibi kendi adaptörünü kabuğa bağlamak için #4 ile birlikte çalışır; bütün kodu tek kişi taşımaz.
İsimler belli olunca issue assignee alanına yazılır. Şu an kimse atanmış değildir.

## İlk çalışma oturumundaki hedef
- Herkes tek aktif issue ve ilk küçük PR dilimini seçer; tahmini teslim zamanını issue'ya yazar.
- #4 sahibi ekipten platform/araç kararını alıp apps/web/README.md içine kaydeder. Diğerleri bu sırada port/fake ve saf kurallarla ilerler; ayrı framework/lockfile düzeni kurmaz.
- Kod görevinin ilk PR'ı: dar dış giriş/port, fake ile tek davranış, bir anlamlı test ve çalıştırma komutu. Tüm özelliği bitirmeyi bekleme.
- Tasarım/belge görevinin ilk PR'ı: ekipçe incelenebilen tek ekran veya tek somut belge bölümü.
- Başka arkadaş README adımlarını kendi bilgisayarında çalıştırır; eksik önkoşulu PR'a yazar. Çalıştırmadıysa geçti demez.

## Ortak demoya giden kısa yol
1. Kabuk + profil: aynı apps/web içinde A/B örnek profili görünür.
2. Keşfet + eşleşme: A/B karşılıklı beğeniyle tek eşleşme oluşturur.
3. Sohbet: aynı uygulamada eşleşmenin tarafları mesajlaşır; C erişemez.
Önce fake ile bağlantılar doğrulanabilir; gerçek adaptör kabulü aşağıdaki listede ayrı tutulur.
Bu, görevlere başlama sırası değil, ortak demo kontrol sırasıdır.

## Haftalık kısa demo
Ekip ortak saat belirler; otomasyon kurulmadı. En güncel main aynı uygulamada çalıştırılır.
“Bende çalışıyor” yerine commit, komut, fake/gerçek durumu ve gözlenen sonuç paylaşılır.
Biten ve bağlanmayan parçalar aşağıdaki tabloda görünür kalır. Görev sahibi gelemiyorsa kısa
handoff bırakır: dal/PR, çalışan komut, kalan iş. Haberleşmeden görev başka kişiye atanmaz.

| Parça | Yerel PR / test | Kabuğa bağlantı | Gerçek servis kanıtı |
|---|---|---|---|
| Profil #6 | Yok | Yok | Yok |
| Keşfet #7 | Yok | Yok | Yok |
| Eşleşme #8 | Yok | Yok | Yok |
| Sohbet #9 | Yok | Yok | Yok |
| Moderasyon #10 | Yok | Yok | Yok |
| Hesap #11 | Yok | Yok | Yok |

#13 sahibi tabloyu kanıt bağlantılarıyla günceller. Modül issue'su yerel teslimle kapanabilir;
bağlantı borcu bu tabloda ve açık #13 altında kalır.

## Gerçek uygulama kabulü

- [ ] Platform/teknoloji önerisi ekipçe kesinleştirildi.
- [ ] Paketler uygulama kabuğuna bağlandı, fake adaptörler gerçek servislerle değiştirildi.
- [ ] Gerçek auth, sunucu/DB erişim kuralları ve gizli değişkenler doğrulandı.
- [ ] Eşzamanlı karşılıklı beğeni gerçek DB'de tek eşleşme oluşturuyor.
- [ ] Engel/silme keşfet ve mesaj erişimini gerçek servis üzerinde kapatıyor.
- [ ] Gerçek A/B hesapları profil → beğeni → eşleşme → mesaj akışını tamamlıyor.
- [ ] C hesabı doğrudan API isteğiyle diğer konuşmayı okuyamıyor/yazamıyor.
- [ ] Hesap silme/veri saklama politikası kesinleşti ve uygulandı.
- [ ] Gerçek paket komutları CI'a bağlandı; gereken kontroller geçti.
- [ ] Demo sonuçları gerçek / stub ayrımıyla kaydedildi.
