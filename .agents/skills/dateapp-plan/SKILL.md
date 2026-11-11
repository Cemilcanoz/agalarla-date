---
name: dateapp-plan
description: Agalarla Date issue kapsamını, dosya sahipliğini ve küçük PR teslimini planla; görev seçerken veya mevcut plan değişirken kullan.
---

# Bağımsız görev planı

Repo kökündeki [AGENTS.md](../../../AGENTS.md) esas alınır.
[OWNERSHIP](../../../docs/OWNERSHIP.md) içinden issue alanını, [ARCHITECTURE](../../../docs/ARCHITECTURE.md) içinden sınırlarını bul.

- Issue'nun amacını ve kabul ölçütlerini koru. İstenen dilim için en fazla beş maddelik plan: dosyalar, portlar, çıktı ve doğrulama.
- 13 iş sırasız başlayabilir. [CONTRACTS](../../../docs/CONTRACTS.md) v0 üzerinden eksik servislerin fake adaptörünü tanımla.
- Başka modülün geliştirilmesini bu issue'ya taşıma. Ortak sözleşme çelişiyorsa geçici varsayımı açık yaz ve sözleşme değişikliğini ayrı ele al.
- Bugünkü plan isteğini uygulama kodu talebine dönüştürme. Kod istenmişse kısa planı hazırlayıp yetkili kapsamda devam et.
- Kısmi teslim issue'yu kapatmaz; PR'da kalan ölçütleri göster.

Kaynak yaklaşım: [Superpowers writing-plans](https://github.com/obra/superpowers/blob/main/skills/writing-plans/SKILL.md). Bu dosya projeye özel kısa yönergedir; upstream paketin kurulumu değildir.
