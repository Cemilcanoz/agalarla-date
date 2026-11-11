---
name: dateapp-module
description: Agalarla Date özellik modülünü ortak portlarla, bağımsız fake adaptörlerle ve sınırlı dosya alanında geliştirirken kullan.
---

# Modül geliştirme

[AGENTS](../../../AGENTS.md), [OWNERSHIP](../../../docs/OWNERSHIP.md) ve ilgili [CONTRACTS](../../../docs/CONTRACTS.md) bölümünü oku.

- Önce mevcut paket README ve kodunu incele. Şablon README'leri gerçek implementasyon veya test sonucu sayma.
- Yalnız issue'nun paket alanında çalış. Saf kural domain'e, kullanım senaryosu application'a, servis bağlantısı adapters'a, ekran ui'a gider.
- Gerekli portları constructor/factory üzerinden al; sibling paketin src dosyasını veya DB tablosunu doğrudan kullanma.
- Servis yoksa kendi fixtures/adapters alanında sözleşmeye uygun fake hazırla. Bu sahte katmanın sınırlarını README'de yaz.
- Ortak tip paketi hazırsa onu kullan; hazır değilse v0 belgesine bağlı yerel tipleri geçici tut ve kaldırılacak kopyaları teslimde belirt.
- Kök workspace/lockfile #4'e aittir. Yeni bağımlılık ihtiyacını açıkça bildir; başka paketin araç zincirini değiştirme.
- İş kuralı ve erişim değişikliği için hedefli davranış testini önce başarısız, uygulamadan sonra başarılı gözle. Yalnız tasarım/README değişikliğinde davranış testi icat etme.
- Dış giriş src/index.ts üzerinden dar tutulur. Sağlanan/tüketilen portlar, gerçek komutlar ve kalan bağlantılar paket README'sine girer.

Teslimi [dateapp-verify](../dateapp-verify/SKILL.md) ile değerlendir; yeni alt ajan gerekmez.
