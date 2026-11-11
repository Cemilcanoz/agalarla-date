# Agalarla Date — ekip başlangıcı

Birlikte dating uygulaması geliştiriyoruz. Plan, modül klasörleri ve ajan yönergeleri hazır.
Şu an uygulama çalışır durumda değil; herkes kendi küçük parçasını geliştirecek.

## 1. Erişim al
Depo özel: GitHub kullanıcı adını Cemil’e gönder ve gelen depo davetini kabul et.
Bağlantı 404 gösteriyorsa doğru GitHub hesabında olduğunu ve daveti kabul ettiğini kontrol et.
Depo: https://github.com/Cemilcanoz/agalarla-date

## 2. Bir görev seç
[Issues listesinden](https://github.com/Cemilcanoz/agalarla-date/issues) üstlenilmemiş bir görev seç.
13 görevin numaraları yapım sırası değil; istediğini alabilirsin.
Kendini Assignees alanına ekle, durum:yapiliyor etiketini seç. Bu alanı değiştiremiyorsan
issue’ya “Bu görevi ben alıyorum” yaz ve Cemil’den atamasını iste.

| İlgini çeken alan | Görev |
|---|---|
| Ürün ve yazılar | #1 |
| Tasarım ve ortak UI | #2 |
| Veri ve ortak arayüzler | #3 |
| Uygulama kabuğu/kurulum | #4 |
| Otomatik kontroller | #5 |
| Giriş ve profil | #6 |
| Keşfet ve beğeni | #7 |
| Eşleşme | #8 |
| Mesajlaşma | #9 |
| Engel ve şikayet | #10 |
| Hesap silme | #11 |
| Test verisi ve senaryolar | #12 |
| Demo ve entegrasyon | #13 |

## 3. Repoyu bilgisayarına al
Git kuruluysa, proje için seçtiğin klasörde:

```sh
git clone https://github.com/Cemilcanoz/agalarla-date.git
cd agalarla-date
git switch -c feat/9-chat
```
Son satır örnek; kendi issue numaranı ve kısa görev adını kullan. Zaten klonladıysan
önce git status ile değişikliklerini kontrol et; temiz main dalında git pull --ff-only çalıştır.
Yerel değişikliklerini silme. Giriş gerekiyorsa kendi GitHub hesabını kullan.

Projeyi kullandığın kod editöründe/ajanında aç. Henüz ortak uygulama çalıştırma komutu yok;
modül kurulum komutları geliştirildikçe ilgili klasörün README dosyasına eklenecek.

## 4. Kendi ajanına bunu gönder
N yerine seçtiğin issue numarasını yaz. Ajan GitHub issue’sunu okuyamıyorsa açıklamasını da yapıştır.

```text
Bu repo Agalarla Date. Issue #N üzerinde çalışacağız.
Önce AGENTS.md, görevin alanındaki ek AGENTS.md ve ilgili .agents/skills SKILL.md dosyasını oku.
Issue kabul ölçütleri, docs/ARCHITECTURE.md, docs/OWNERSHIP.md ve gerekli CONTRACTS.md bölümüne uy.
Yalnız bu issue’nun küçük bir dilimini, bana ait modül klasöründe geliştir.
Diğer modüller hazır değilse ortak sözleşmeye uygun fake adaptör kullan.
Başka modülün içine girme ve yeni alt ajan başlatma.
İlgili doğrulamayı yap; değişen dosyaları, test sonucunu ve kalan entegrasyonu kısa anlat.
```

Global skill kurulumu veya başka birinin AI hesabı/anahtarı gerekmez.
Yönergeler tüm araçlarda kendiliğinden okunmayabilir; başlangıç metnini vermeyi unutma.

## 5. Küçük PR gönder
Değişen dosyaları kontrol et, yalnız görev dosyalarını commit et ve görev dalını GitHub’a push et.
GitHub’da bu daldan main’e Pull Request aç. Ne yaptığını ve nasıl denediğini yaz.
Kısmi işte Refs #N; bütün ölçütler bittiyse Closes #N kullan. Bir arkadaşın incelemesini bekle.

Her modül örnek verilerle ayrı ilerler. Gerçek servislerle birleşim ayrıca doğrulanır;
sadece fake ile test edilen işi “uygulama tamamen çalışıyor” diye sunmayın.

## Kısa bağlantılar
- [Plan ve klasörler](ARCHITECTURE.md)
- [Hangi dosya kimin görevi?](OWNERSHIP.md)
- [Ajan kuralları](../AGENTS.md)
- [AI ile katkı](AI-COLLABORATION.md)

## Birbirimizden kopmamak için
Bir aktif görev al; ilk çalışma oturumunda küçük bir PR çıkar ve tahmini teslimini issue'ya yaz.
Başkasının PR'ını kendi bilgisayarında dene. Her hafta ekipçe belirleyeceğimiz saatte aynı
uygulamanın main sürümünü gösterelim. Çalışan modül ile birleşmiş uygulama durumunu
[entegrasyon tablosunda](INTEGRATION.md) ayrı takip ediyoruz.
