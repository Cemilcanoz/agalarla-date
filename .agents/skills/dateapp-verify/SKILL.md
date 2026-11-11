---
name: dateapp-verify
description: Agalarla Date değişikliğini test ederken, hata düzeltirken, PR incelerken veya teslim ederken kapsam, modül sınırı ve gerçek-fake ayrımını doğrula.
---

# Doğrulanmış teslim

[OWNERSHIP](../../../docs/OWNERSHIP.md) ve diff'i karşılaştır. Kapsam dışı değişikliği, sibling iç importunu ve UI/domain içinde DB bağımlılığını incele.

İlgili davranışları seç; her görevde bütün listeyi çalıştırma:
- Profil: başka kişinin kaydını değiştirme reddi.
- Keşfet: kendi/pasif/engellenmiş hesabın listeden çıkarılması.
- Eşleşme: karşılıklı beğeni, tekrar istekte tek kayıt; gerçek DB yarış testi fake testten ayrı.
- Mesaj: aktif eşleşme tarafları dışında erişim reddi; clientRequestId tekrarında tek mesaj.
- Moderasyon: çift yönlü engel, şikayet listesinde yönetici erişimi.
- Hesap: pasif/silinmiş hesabın erişiminin kapanması, tekrar istek ve kısmi hata.

Mevcut paket komutlarını kullan; olmayan npm/test komutunu varsayma. İlgili kontroller geçince yalnız yeni değişiklik/hata gerektiriyorsa tekrar çalıştır.
Web çalışır durumdaysa değişen akışı mevcut Playwright altyapısıyla doğrula; başka stack'e yeni araç dayatma.
Dokümanda yerel linkleri ve issue/klasör eşleşmesini kontrol etmek yeterli olabilir.
Hata varsa tekrarlama adımı ve kanıtı topla, tek hipotezi test et; rastgele refactor yapma.

PR özeti: amaç; değişen alan; çalıştırılan komut ve sonuç; çalıştırılmayan kontroller; kalan entegrasyon.
Kısmi PR Refs #N kullanır. Tüm kabul ölçütleri doğrulanmadan issue tamamlandı denmez.
[INTEGRATION](../../../docs/INTEGRATION.md) gerçek uçtan uca kontrolüdür; stub demo başarısı bu kontrolü kapatmaz.

Kaynaklar: [Superpowers TDD](https://github.com/obra/superpowers/blob/main/skills/test-driven-development/SKILL.md), [Anthropic webapp-testing](https://github.com/anthropics/skills/blob/main/skills/webapp-testing/SKILL.md). Buradaki yönergeler yerel uyarlamadır.
