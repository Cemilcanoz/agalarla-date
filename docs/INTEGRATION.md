# Gerçek uygulamayı birleştirme kontrolü

13 görev bağımsız paket teslimidir. Issue kapanması tüm uygulamanın çalıştığı anlamına gelmez.
Milestone aşağıdakiler tamamlanana kadar açık kalır. Birleştirme sorumlusu ekipçe seçilecek.

- [ ] Platform/teknoloji önerisi ekipçe kesinleştirildi.
- [ ] Paketler uygulama kabuğuna bağlandı, fake adaptörler gerçek servislerle değiştirildi.
- [ ] Gerçek auth, sunucu/DB erişim kuralları ve gizli değişkenler doğrulandı.
- [ ] Eşzamanlı karşılıklı beğeni gerçek DB'de tek eşleşme oluşturuyor.
- [ ] Engel/silme keşfet ve mesaj erişimini gerçek servis üzerinde kapatıyor.
- [ ] Gerçek A/B hesapları profil → beğeni → eşleşme → mesaj akışını tamamlıyor.
- [ ] C hesabı doğrudan API isteğiyle diğer konuşmayı okuyamıyor/yazamıyor.
- [ ] Hesap silme/veri saklama politikası kesinleşti ve uygulandı.
- [ ] Gerçek paket komutları CI'a bağlandı; gereken kontroller geçti.
- [ ] Demo sonuçları gerçek / stub ayrımıyla kaydedildi.
