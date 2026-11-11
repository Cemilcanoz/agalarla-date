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
Önce issue, CONTRIBUTING.md ve docs/CONTRACTS.md oku.
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
- Issue içindeki paket klasörüne sahip çıkın; diğer paketleri ve kök lockfile dosyasını değiştirmeyin.
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
