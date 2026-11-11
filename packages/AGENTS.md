# Paketlerde çalışma

Kök AGENTS.md ve docs/OWNERSHIP.md geçerlidir.

- profile/discovery/matching/chat/moderation/account: yalnız seçilen özellikte çalış; src/domain, application, adapters, ui sınırlarını koru.
- Sibling özelliğin iç kodunu import etme. İhtiyaç duyulan port dışarıdan verilir; eksik servis yerel fake ile karşılanır.
- contracts: yalnız ortak tip/port sözleşmesi; özellik veya framework bağımlılığı ekleme.
- ui: yalnız sunum; iş kuralları, auth ve DB yok.
- testing: ortak test yardımcıları; üretim paketlerinin buraya bağımlı olmasına izin verme.
- Her paketin gerçek kurulum/test komutunu kendi README dosyasında tut. Ortak workspace değişikliği #4 alanıdır.
