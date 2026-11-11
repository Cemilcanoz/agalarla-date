# Ortak sözleşme v0

Bu belge herkesin sıradan bağımsız başlaması için başlangıç çalışma sözleşmesidir.
Ürün/teknoloji kararı kullanıcı tarafından kesinleştirilmiş değildir. Kod modülleri için
varsayılan ortak dil TypeScript; framework bağımsız servisler ve yerel fake adaptörler kullanın.
#4 kabuk önerisi mobil uyumlu webdir. Platform değişirse servisleri koruyup adaptörleri değiştirin.
Her paket kendi kurulum/test komutunu belgelemeli; kök package/lockfile değiştirmemeli.

## Veri biçimleri
ID string, zaman ISO-8601 UTC string. Kurgu kullanıcılar u-a, u-b, u-c; yönetici u-admin.
- Profile: id, displayName, bio, interests:string[], photoUrl:string|null, active:boolean.
- Reaction: actorId, targetId, kind:like|pass.
- Match: id, userIds:[string,string], status:active|closed.
- Message: id, matchId, senderId, text, createdAt, clientRequestId.
- Block: actorId, targetId.
- Report: id, reporterId, subjectType:profile|message, subjectId, reason, status:open|resolved.
- Session: userId, role:user|admin. Gerçek uygulamada güvenilir sunucu oturumundan türetilir;
  istemcinin gönderdiği role/userId güvenlik kanıtı değildir.

## Adaptör arayüzleri
İşlemler Promise döndürür. Başarı {ok:true,data:T}; hata {ok:false,error:{code,message}}.
Kodlar: UNAUTHENTICATED, FORBIDDEN, NOT_FOUND, VALIDATION, CONFLICT, UNAVAILABLE.
Listeler dizi döndürür; bulunamayan tekil kayıt NOT_FOUND.
- SessionPort: current() -> Session|null; revoke(userId) -> null.
- ProfilePort: get(id) -> Profile; list(viewerId) -> Profile[]; save(actorId,profile) -> Profile.
- ReactionPort: set(actorId,targetId,kind) -> Reaction; listFor(userId) -> Reaction[].
- MatchPort: get(id) -> Match; list(userId) -> Match[]; close(actorId,id) -> Match.
- MessagePort: list(actorId,matchId) -> Message[]; send(actorId,matchId,text,clientRequestId) -> Message.
- ModerationPort: isBlocked(a,b) -> boolean; block(actorId,targetId) -> Block;
  report(actorId,subjectType,subjectId,reason) -> Report; listReports(session) -> Report[];
  resolveReport(session,id) -> Report.
- AccountPort: deactivate(userId) -> null; removeProfile(userId) -> null; revokeSessions(userId) -> null.

## Ortak davranış
Engel kontrolü iki yönlüdür. Mesaj yalnız aktif eşleşmenin taraflarına açık.
Eşleşme çiftini ID sırasına göre normalize edin. Aynı clientRequestId aynı gönderici/eşleşmede
ikinci mesaj oluşturmaz. Profil yalnız sahibi tarafından düzenlenir. Şikayet listesi yöneticiye açıktır.
Silinmiş/pasif profil keşifte görünmez. Sunucu ve DB erişim kontrolleri gerçek adaptörlerde de uygulanır.

## Bağımsız geliştirme
Kendi paketinizde yukarıdaki portların sadece ihtiyacınız olan fake implementasyonlarını yazın.
Fake adaptör test içindir, üretim güvenliği veya DB eşzamanlılığı kanıtı değildir.
Sözleşme değişikliği ayrı PR ile önerilir; sessizce alan/işlem adı değiştirmeyin.
