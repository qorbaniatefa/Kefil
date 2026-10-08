# Kefil: Ajanın arkasındaki insanı kanıtla

Ödev 3 (Yeni Deprem Üretmek) için hazırlanmış ürün sunumu ve çalışan demo.

**Canlı demo:** https://KULLANICI_ADIN.github.io/kefil/
**Hazırlayan:** AD SOYAD

## Seçilen deprem

**Ajan çağında kişilik kanıtı (proof of personhood).** Web trafiğinin yarısından fazlası artık insan değil, meşru yapay zekâ ajanları da yaygınlaşıyor. CAPTCHA gibi "otomasyonu engelle" mantığı bu durumda yetersiz kalıyor. Yeni soru şu: bu ajanın arkasında sorumlu, tekil bir insan var mı?

Dayanaklar:

- Y Combinator Güz 2026 Requests for Startups listesindeki 13 talepten biri: "Proving You're Human".
- World, Haziran 2026'da AgentKit erişimini genişletti. Doğrulanmış bir kişi kimliğini ajanına devrediyor ve ajan, sıfır bilgi kanıtıyla arkasında tekil bir insan olduğunu gösteriyor.
- Cloudflare'in 1 Temmuz 2026 raporuna göre internet trafiğinin yarısından fazlası insan değil.

## Klon: ne yaptım?

World AgentKit akışının sadeleştirilmiş, çalışan bir klonu. Tarayıcıda, sunucusuz çalışır ve gerçek ECDSA P-256 imzaları (WebCrypto) kullanır.

1. **İnsan sinyali (demo):** Türkçe karakterli bir cümle elle yazılır, yapıştırma kapalıdır. Tuş vuruşu zamanlaması kontrol edilir.
2. **Yetki belgesi:** İnsan, ajanına kapsamlı ve süreli bir belge verir. Belgede ad, soyad veya biyometri yoktur. Yalnızca takma tanıtıcı, kapsam, süre ve dakikalık istek sınırı bulunur.
3. **Doğrulama:** Web sitesi imzayı, süreyi, kapsamı ve insan başına hız sınırını denetler.

Demoda dört durum denenebilir: geçerli istek, yanlış kapsam, bozulmuş belge, kefilsiz bot.

## Yerelleştirme ve yenilik

- Türkçe arayüz ve Türkçe karakterli insan sinyali.
- Biyometri ve kişisel veri toplamayan, KVKK'ya uygun tasarım hedefi.
- Kapsamlı ve süreli yetki modeli: ajan yalnızca verilen işte, verilen süre ve hız sınırıyla geçerli.
- Yol haritasında takılabilir doğrulama sağlayıcıları (NFC çipli kimlik kartı, e-Devlet tabanlı doğrulama). Bu entegrasyonlar demoda **yoktur**.

## Dürüst sınırlar

- Adım 1'deki zamanlama sinyali yalnızca gösterim içindir. Gerçek bir insanı kanıtlamaz ve kararlı bir saldırgan taklit edebilir.
- İmza anahtarı sayfada üretilir. Üretimde anahtarı bağımsız bir yayıncı tutmalıdır.
- Kişilik kanıtı tek başına yeterli değildir, bir güvenlik katmanı olarak düşünülmelidir.
- World'ün doğrulanmış insan sayısı şirketin kendi bildirimidir, bağımsız denetimli değildir.

## Dosyalar

- `index.html`: tüm ürün sayfası ve demo (tek dosya, bağımlılık yok)

## Kaynaklar

1. Y Combinator, Requests for Startups, Güz 2026 (liste: modelence.com/yc-rfs-fall-2026, bigideasdb.com/yc-request-for-startups-2026)
2. HackerNoon, "World Expands AgentKit so AI Agents Can Prove a Unique Human Is Behind Them", 24 Haziran 2026
3. Proof of Talk, "Proof of personhood, identity and the agentic age" (Cloudflare 1 Temmuz 2026 rakamı, World'ün 17 Nisan 2026 bildirimi)
4. Parity, "When AI Bots Look Human: Why We Need Proof of Personhood", 3 Ağustos 2026
5. Renee DiResta'nın Noema yazısının özeti, 30 Haziran 2026 (letsdatascience.com)
