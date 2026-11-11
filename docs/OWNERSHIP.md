# Görev ve dosya sahipliği

Kişi ataması yok; herkes boş bir issue seçip kendini atar. 13 iş sırasız başlanabilir.

| Issue | Alan | Ana teslim |
|---|---|---|
| [#1](https://github.com/Cemilcanoz/agalarla-date/issues/1) | `docs/product` | Ürün briefi, kapsam ve ekran metinleri |
| [#2](https://github.com/Cemilcanoz/agalarla-date/issues/2) | `docs/design; packages/ui` | Tasarım kuralları, ekran taslakları ve iş kuralı içermeyen ortak UI planı |
| [#3](https://github.com/Cemilcanoz/agalarla-date/issues/3) | `packages/contracts; docs/data; docs/CONTRACTS.md` | Port/veri sözleşmeleri ve erişim matrisi |
| [#4](https://github.com/Cemilcanoz/agalarla-date/issues/4) | `apps/web; kök package/lockfile/workspace ayarları` | Uygulama kabuğu, bağımlılık bağlama ve kurulum |
| [#5](https://github.com/Cemilcanoz/agalarla-date/issues/5) | `quality/ci; .github/workflows` | Tek paket kontrolü ve PR CI |
| [#6](https://github.com/Cemilcanoz/agalarla-date/issues/6) | `packages/profile` | Oturum, giriş/çıkış ve profil düzenleme |
| [#7](https://github.com/Cemilcanoz/agalarla-date/issues/7) | `packages/discovery` | Profil listeleme ve beğen/geç kaydı |
| [#8](https://github.com/Cemilcanoz/agalarla-date/issues/8) | `packages/matching` | Karşılıklı beğeni, tek eşleşme ve kapatma |
| [#9](https://github.com/Cemilcanoz/agalarla-date/issues/9) | `packages/chat` | Yetkili okuma/yazma ve sohbet ekranı |
| [#10](https://github.com/Cemilcanoz/agalarla-date/issues/10) | `packages/moderation` | Engelleme, şikayet ve yönetici incelemesi |
| [#11](https://github.com/Cemilcanoz/agalarla-date/issues/11) | `packages/account` | Hesap kapatma/silme ve oturum iptali |
| [#12](https://github.com/Cemilcanoz/agalarla-date/issues/12) | `packages/testing; quality/scenarios` | Kurgu fixture, port fake ve kabul senaryoları |
| [#13](https://github.com/Cemilcanoz/agalarla-date/issues/13) | `quality/demo; docs/INTEGRATION.md` | Stub demo, bağlantı matrisi ve gerçek entegrasyon takibi |

## Ortak dosyalar
- #4: kök paket/workspace/lockfile ayarları. Özellik sahibi ihtiyaç duyduğu bağımlılığı bildirir; kök dosyayı paralel değiştirmez.
- #3: ortak sözleşme; mevcut v0 herkes için yeterli başlangıçtır. Değişiklikte etkilenen modül sahibi review verir.
- #2: ortak UI; özellikler bunu beklemek zorunda değil, basit yerel ekran kullanabilir.
- #12: ortak fake/fixture; özellikler kendi fixtures alanıyla başlayabilir.
- #13: entegrasyon kontrolünü tutar. Gerçek bağlama PR'ında #4 ve ilgili modül sahibi birlikte inceleme yapar.
- Alan dışı değişiklik ayrı PR ve ilgili sahibin incelemesiyle yapılır. Bu belge otomatik branch koruması değildir.
