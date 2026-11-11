# Agalarla Date

Arkadaş ekibinin birlikte geliştirdiği dating uygulaması.

## Durum
Proje başlangıç aşamasında. Uygulama kodu ve kurulum komutları henüz yok.
Web/mobil ve teknoloji seçimi ekip tarafından netleştirilecek. Bağımsız kod paketleri için TypeScript ve fake adaptör başlangıç sözleşmesi docs/CONTRACTS.md içinde.

## Önerilen ilk sürüm
18+ davetli test grubu; geliştirme demosunda kurgu profiller.
1. Kayıt ve profil: takma ad, kısa tanıtım, ilgi alanları ve fotoğraf.
2. Profil keşfi, beğenme/geçme ve karşılıklı beğenide tek eşleşme.
3. Yalnız eşleşen kullanıcılar arasında metin mesajlaşması.
4. Eşleşme kaldırma, engelleme, şikayet ve hesap silme.

İlk sürüm dışında: ödeme, GPS, yapay zekâ eşleştirme, görüntülü görüşme.
18+ beyanı kimlik/yaş doğrulaması anlamına gelmez.

## Birlikte çalışma
[Katkı rehberi](CONTRIBUTING.md) ve [başlangıç görevleri](docs/BACKLOG.md).
13 görevin hepsi hemen seçilebilir; numaralar sıra değildir. Ortak portlara uygun fake adaptörlerle geliştirin.
Her görev için ayrı dal, küçük PR ve bir ekip arkadaşının incelemesi önerilir.
Gerçek parçaların birleştirilmesi docs/INTEGRATION.md kontrol listesiyle izlenir.
`main` çalışır sürümü temsil eder. Koruma kuralları henüz uygulanmadı.

## İlk demo kabulü
İki test hesabı profil oluşturur, karşılıklı beğeniyle eşleşir ve mesajlaşır.
Engellenen hesap yeni mesaj gönderemez; şikayet yetkili inceleme ekranına düşer.
Üçüncü hesap başka bir eşleşmenin mesajlarını API üzerinden de okuyamaz.

## Açık kararlar
Platform, teknoloji, teslim tarihi, ekip kullanıcı adları ve görev sahipleri.
