# Kendi ajanınızla katkı verme

Her arkadaş kendi hesabı/ajanıyla bir görevi üstlenir; hesap veya anahtar paylaşılmaz.
Amaç işi bölmek. Kesin token tasarrufu garantisi yok; kısa bağlam ve küçük PR yeniden çalışma ihtiyacını azaltabilir.

## Başlama
1. 13 issue da hemen seçilebilir. docs/CONTRACTS.md v0 kullan; eksik servisleri kendi paketinde fake adaptörle karşıla.
2. Issue'yu kendine ata; aynı işe iki kişinin başlamaması için durum etiketini güncelle.
3. Güncel main'den görev dalı aç. Ortak şema/sözleşme değişikliklerini önce ilgili görev sahibiyle konuş.
4. Issue içindeki küçük PR dilimlerinden yalnız birini seç. Her dilim bittiğinde ilgili ölçütü işaretle; bütün ölçütler bitmeden issue'yu kapatma.
5. Bir arkadaş diff ve doğrulamayı incelesin. PR açıklamasında kısmi teslim için `Refs #N`, yalnız son teslim için `Closes #N` kullan.

## Ajana kopyalanacak metin
```text
Agalarla Date deposunda issue #N, PR dilimi [başlık] üzerinde çalış.
Önce AGENTS.md dosyasını ve oradan bu işe uygun SKILL.md dosyasını oku.
Ardından issue, CONTRIBUTING.md, docs/CONTRACTS.md ve docs/OWNERSHIP.md oku.
Yalnız ilgili kaynak dosyalarını bul; bütün depoyu/skill kataloglarını bağlama yükleme.
Diğer modülü bekleme; port sözleşmesine uygun fake adaptörle bağımsız teslim et. Gerçek entegrasyon yapıldı deme.
En fazla 5 maddelik kısa plan yaz, sonra seçilen dilimi uygula.
Paylaşılan API/veri biçimini değiştirme; gerekiyorsa önce değişiklik ihtiyacını belirt.
Davranış hatası/erişim kuralı için önce hatayı gösteren hedefli test, sonra en küçük düzeltme yap.
İlgili testleri ve projenin gerekli kontrollerini çalıştır; sonuçları açıkça yaz.
Yeni alt ajan veya geniş refactor başlatma. İki başarısız denemeden sonra kısa teşhisle ekipten yardım iste.
Sonuç: değişen dosyalar, çalıştırılan komut/sonuç, kalan engel. PR'ı incelemeye hazırla.
```

## Birlikte çalışırken
- docs/CONTRACTS.md v0: ortak dil/veri/port başlangıç varsayımları; ürün platformu henüz ekipçe kesinleştirilmedi.
- Issue içindeki dosya alanına sahip çıkın; kök workspace/lockfile yalnız #4 alanıdır.
- Ortak bağımlılık/lockfile, migration ve sözleşme dosyalarında eşzamanlı değişiklikleri koordine edin.
- Ajan konuşmalarını bütün halinde taşımayın; PR'a amaç, değişiklik, test ve kalan işi yazın.
- Doküman/görsel değişiklikte anlamsız test üretmeyin; eşleşme, erişim ve engelleme davranışında gerçek regresyon testi kullanın.
- Web seçilirse çalışan uygulamada temel akışı Playwright ile doğrulayın. Test yapılmadıysa geçti demeyin.

## İncelenen kaynaklar — 11 Kasım 2026
Bu depolar kurulmadı; yöntemleri projeye uyarladık. Bütün otomasyon/ajan zincirlerini açmak gerekli değil.
- [Superpowers brainstorming](https://github.com/obra/superpowers/blob/main/skills/brainstorming/SKILL.md): koddan önce amaç/kapsam kararı (#1–2).
- [Superpowers writing-plans](https://github.com/obra/superpowers/blob/main/skills/writing-plans/SKILL.md): küçük, açık teslimler (#3–11).
- [Superpowers test-driven-development](https://github.com/obra/superpowers/blob/main/skills/test-driven-development/SKILL.md): davranış testi ve en küçük uygulama (#6–11).
- [Anthropic webapp-testing](https://github.com/anthropics/skills/blob/main/skills/webapp-testing/SKILL.md): çalışan web uygulamasında arayüz doğrulama (#5, #12–13).

Bağlam sınırı, alt ajan açmama ve iki başarısız deneme sonrası devir, bu ekibin kullanım limitleri için önerilen uyarlamalardır; kaynakların ölçülmüş token garantisi değildir.

Modüler yerleşim: docs/ARCHITECTURE.md. Kabuk apps/web; özellikler packages/<modül>; başka özelliğin iç dosyaları import edilmez.

## Repo ile gelen ajan yönergeleri
AGENTS.md ana giriş; packages/AGENTS.md ve apps/AGENTS.md ilgili alanın ek kurallarıdır.
Üç kısa proje skill'i .agents/skills altında bulunur. Skill keşfi kullandığınız araca göre değişir;
her araçta otomatik yüklenme garantisi yoktur. Claude için CLAUDE.md ana dosyayı işaret eder.
Başka bir ajan kullanıyorsanız şu metni verin:

```text
Önce bu reponun AGENTS.md dosyasını oku ve ilgili proje skill'ini aç.
Issue #N'nin yalnız seçtiğim dilimini modüler plana ve dosya sahipliğine uyarak tamamla.
```

Clone/pull bu dosyaları da getirir; global eklenti kurmak gerekmez.
Bunlar ajan yönergeleridir, teknik engelleme sistemi değildir. CI/branch koruması henüz kurulmuş sayılmaz;
#5 kapsamında otomatik kontroller ayrıca hazırlanacaktır. Mimari uyum PR incelemesinde kontrol edilir.
