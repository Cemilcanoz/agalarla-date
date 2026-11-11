# Modüler geliştirme planı

## Yaklaşım
Tek depo, bağımsız özellik paketleri, tek uygulama kabuğu. Her paket kendi testleri ve fake
adaptörleriyle çalışılabilir. 13 issue sırasız alınır. Şu an yalnız plan/klasör iskeleti var.
TypeScript ortak modül dili başlangıç varsayımı; framework, backend ve platform ekip kararına açık.
Mobil uyumlu web kabuğu apps/web içinde öneriliyor; servis katmanları framework bağımsız tutulur.

```text
apps/web/                 # ekranları ve gerçek adaptörleri birleştiren kabuk (#4)
packages/
  contracts/              # ortak veri ve port tipleri (#3)
  ui/                     # iş kuralı içermeyen tasarım bileşenleri (#2)
  testing/                # yalnız testlerde kullanılan fake ve fixture (#12)
  profile/                # oturum ve profil (#6)
  discovery/              # keşfet ve beğeni (#7)
  matching/               # eşleşme (#8)
  chat/                   # mesajlaşma (#9)
  moderation/             # engel ve şikayet (#10)
  account/                # hesap yaşam döngüsü (#11)
quality/
  ci/                     # modül kontrolleri (#5)
  scenarios/              # kabul senaryoları (#12)
  demo/                   # stub demo ve entegrasyon sürücüsü (#13)
docs/
  product/                # ürün/kapsam/metin (#1)
  design/                 # tasarım/taslak (#2)
  data/                   # veri/erişim modeli (#3)
.github/workflows/        # CI entegrasyonu (#5)
```

## Özellik paketinin içi
- src/domain/: saf iş kuralları; framework, UI ve DB bilmez.
- src/application/: kullanım senaryoları; domain ve ortak portlar üzerinden çalışır.
- src/adapters/: fake ve gerçek servis bağlantıları. Auth/DB sağlayıcısı ayrıntıları burada kalır.
- src/ui/: opsiyonel özellik ekranları; application katmanını çağırır.
- tests/ ve fixtures/: bağımsız doğrulama ve kurgu veriler.
- src/index.ts: uygulama yazılırken eklenecek tek dış giriş; şimdi kod dosyası oluşturulmadı.

## İzin verilen bağımlılıklar
contracts hiçbir özellik paketini import etmez. domain yalnız saf tip/kural kullanır.
application → domain + contracts; adapters → contracts; ui → application + ortak ui.
Özellik paketi başka özelliğin src içini veya gerçek adaptörünü import etmez.
apps/web her paketin dış girişini import eder ve ihtiyaç duyduğu portları enjekte eder.
packages/testing yalnız test/demo tarafından kullanılabilir; üretim kodunun bağımlılığı olmaz.
Bir özellik verisini başka özellik doğrudan veritabanından değiştirmez; ilgili porta gider.

## Veri ve davranış sahipleri
Profile/Session #6; Reaction #7; Match #8; Message #9; Block/Report #10.
#11 hesap silme sürecini koordine eder, diğer tabloların iş kurallarını kopyalamaz.
#3 ortak şema/erişim tasarımını tutar; gerçek adaptör/migration uygulaması ilgili modülün alanında hazırlanır.
Migrationların uygulama sırası gerçek entegrasyon sırasında birlikte kontrol edilir.

## Modüller birbirini beklemeden nasıl çalışır?
Sohbet MatchPort ve ModerationPort fake'leri alır; gerçek eşleşme/engel koduna ihtiyaç duymaz.
Keşfet ProfilePort ve ModerationPort fake'leriyle çalışır. Eşleşme ReactionPort verisini fake'ten alır.
Fake'ler CONTRACTS v0 davranışını izler; gerçek DB yarış koşulu ve sunucu erişim kontrolünü kanıtlamaz.
Port/type kodu henüz yokken v0 belgesini referans alan yerel test tipleri kullanılabilir;
ortak contracts paketi hazır olunca yerel kopyalar kaldırılır, tek kaynağa bağlanır.

## Birleştirme ve bitti ölçütü
Modül PR'ı: kapsam sınırlı, dış giriş/portları belgeli, ilgili testleri çalışır, gerçek/fake ayrımı açık.
Uygulama teslimi: INTEGRATION.md gerçek servis kontrollerinin tümü geçer. Stub demo bu teslim değildir.
Her PR küçük tutulur; görevlerin kişilere dağılımı OWNERSHIP.md üzerinden serbest seçimle yapılır.
