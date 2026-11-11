# Agalarla Date — ajan çalışma kuralları

Bu dosya repo kapsamındadır. Kullanıcının açık görev kapsamını koru.

## Başlangıç
- Seçilen issue ve kabul ölçütlerini oku. Issue belirtilmediyse istenen işin dosya alanını OWNERSHIP ile eşleştir; başka işe kendiliğinden geçme.
- [Mimari](docs/ARCHITECTURE.md), [sahiplik](docs/OWNERSHIP.md) ve yalnız gerekli [sözleşme](docs/CONTRACTS.md) bölümlerini oku.
- Değiştireceğin dosyaları ve git durumunu incele; mevcut kullanıcı değişikliklerini koru.
- 13 görev sırasız başlanabilir. Eksik modülü bekleme: sözleşmeye uygun fake adaptör kullan. Çelişkili/eksik sözleşmeyi sessizce değiştirme; dar bir öneriyle belirt.

## Planı koruma
- Tek issue, tek küçük teslim. Dosya alanı docs/OWNERSHIP.md ile sınırlıdır. Kullanıcı açıkça plan/mimari güncellemesi isterse ilgili belgeleri tutarlı güncelle.
- Özellikler birbirinin iç dosyalarını import etmez. domain saf; application portları kullanır; adapters dış servisleri bağlar; ui DB'ye erişmez.
- apps/web paketlerin dış girişlerini bağlar. contracts özellik paketi import etmez. testing üretim bağımlılığı değildir.
- Ortak API/veri biçimi değişikliği ayrı ve açıklanmış PR'dır. #4 kök workspace/lockfile sahibi; diğer görevler kendi alanında kalır.
- Teknoloji/platform önerisini alınmış ekip kararı gibi sunma. Güncel dosyaları kontrol et; iskelet README'sini çalışan kod sanma.

## İlgili skill'i seç
Bütün skill'leri birden yükleme. Dosyalar repo ile gelir; otomatik keşif yoksa doğrudan oku.
- Görev kapsamı/PR dilimi: [dateapp-plan](.agents/skills/dateapp-plan/SKILL.md).
- Özellik/modül kodlama: [dateapp-module](.agents/skills/dateapp-module/SKILL.md).
- Test, hata düzeltme, PR inceleme veya teslim: [dateapp-verify](.agents/skills/dateapp-verify/SKILL.md).

## Çalışma ve teslim
- İstenen iş için gereken dosyaları oku; bütün repo, katalog veya konuşma geçmişini yükleme. Kullanıcı istemedikçe alt ajan zinciri başlatma.
- Hata/erişim kuralı için davranış testi kullan; salt belge değişikliğine yapay test yazma. Mevcut gerekli kontrolleri çalıştır.
- Fake başarısı gerçek auth/DB güvenliği veya eşzamanlılık kanıtı değildir. Gerçek entegrasyon docs/INTEGRATION.md ile ayrıca doğrulanır.
- Çalıştırılmayan testi geçti diye yazma. Teslimde dosyalar, doğrulama komutu/sonucu ve kalan entegrasyonu belirt.
- Kısmi PR: Refs #N; yalnız tüm issue ölçütleri tamamlanınca Closes #N. Bir ekip arkadaşı incelemeden merge etme.
- Anahtarlar, .env ve gerçek kullanıcı veri dışa aktarımları commit edilmez.

## Ortak çalışmayı koru
- Kişi başına tek aktif issue; ilk PR için tüm özelliğin bitmesini bekleme. Port/fake ile tek davranış veya incelenebilir belge dilimi teslim et.
- PR'da başka arkadaşın çalıştırabileceği komutu, önkoşulları ve entegrasyon durumunu yaz.
- Modülün yerel başarısını uygulamanın başarısı sayma. Bağlanmamış işleri docs/INTEGRATION.md ve #13 altında görünür tut.
- #13 stub ile hemen başlar; gerçek ortak demo kanıtı olmadan #13/milestone kapanmaz. #4 bağlama, #13 demo takibi sahibidir; kişiler henüz atanmadı.
