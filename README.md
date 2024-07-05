# **Git Türkçe Kullanma Kılavuzu**

(Son güncelleme: 11/08/2022)

Merhaba. Bu repo'da Git ve GitHub'ı dilim döndüğünce ve basit bir şekilde anlatmaya çalışacağım. Lütfen eksik ya da hatalı gördüğünüz konular için PR açmaktan çekinmeyin. :)

- [**Git Türkçe Kullanma Kılavuzu İçindekiler**](#git-t%C3%BCrk%C3%A7e-kullanma-k%C4%B1lavuzu)
  - [Git Nedir?](#git-nedir)
  - [Neden Git Kullanırız?](#neden-git-kullanırız)
  - [Git Buysa, GitHub Ne?](#git-buysa-github-ne)
  - [Temel Git Başlıkları ve Git Komutları](#temel-git-başlıkları-ve-git-komutları)

## Git Nedir?

Git bir versiyon kontol yazılımıdır ve Linux'un yaratıcısı Linus Torvalds [@torvalds](https://github.com/torvalds) tarafından geliştirilmiştir.

## Neden Git Kullanırız?

Tanımından da anlaşılabileceği üzere, yazılımların versiyonlarını düzenli bir şekilde kontrol etmek için Git'i kullanırız.

Mesela bir yazılım geliştirdiniz ve bunu bir bulutta saklıyorsunuz. Bulutta sakladığınız şey, aslında yazılımın son halidir. Ama GitHub'da saklasaydınız projenin her aşamasını görebilir, yeri geldiğinde yaptığınız değişiklikleri geri alabilir, başka insanların da bu projeye katkıda bulunmasını sağlayabilirdiniz.

## Git Buysa, GitHub Ne?

Güzel soru. Bu soruyu cevaplamadan önce Git'in tanımına dönelim: Git bir versiyon kontol **yazılımıdır**. Yani Git bir yazılımdır. GitHub ise bu yazılım üstüne inşa edilmiş bir **servistir**. Git açık kaynaklı olduğu için açık kaynak topluluğu tarafından geliştirilirken, GitHub ise ticari bir servistir ve Microsoft tarafından geliştirilir. Ücretsiz ve ücretli sürümleri mevcuttur.

## Temel Git Başlıkları ve Git Komutları

1. **Repository**: Olabilecek en temel ve yüzeysel tanımıyla, kod deposudur. Repository'nin çoğu zaman repo şeklinde kullanılmasına da denk gelebilirsiniz.
2. **Add (Ekle)**: Yerel yaptığınız değişikleri git sistemine eklemenize yarar.
   1. **add --all**: Değişiklik yapılmış tüm dosyaları eklemeye yarar.
   2. **add [[dosya adı]]**: Belirtilen dosya adını eklemeye yarar.
3. **Commit**: Git yazılımına eklediğiniz (added) değişikliklerin Git sunucusuna işlenmesi demektir. `git commit`
   1. **Commit Message**: Commit ederken eklenen mesajdır. Yaptığınız değişikliklerin size ve diğer contributor'ler için açıklayıcı olmasına yardımcı olur. `git commit -m "Commit Mesajı"`
4. **Contributor (Katkıda bulunan)**: Kelime anlamı olarak katkı sağlayan kişi demektir. Projenize ekleme yapan, bir bug ya da typo keşfeden ve bunu size bildiren kişilerdir.
5. **Maintainer (İlgili)**: Bir projeyi geliştiren, yöneten kişilere denir.
6. [**Clone (klon)**](https://github.com/onurravli/Git-Turkce-Kullanma-Kilavuzu/blob/main/git-clone.md#git-clone): Uzak sunucudaki bir repoyu bilgisayarınıza indirmeye yarar. `git clone https://github.com/onurravli/Git-Turkce-Kullanma-Kilavuzu`
7. **Push (İtme)**: Commit ettiğiniz değişikliklerin uzak sunucuya gönderilmesi demektir. `git push`
   1. **Branch**: Projenizin farklı versiyonlarına erişmenize, değişiklik yapmanıza ve kullanmanıza yarar. Push ederken `-u` flag'i ile belirtilir: `git push -u **origin main**`. İlk etapta (git öğrenmeye başlarken yani) branch kullanmanız pek gerekmiyor.
8. **Pull (Çekme)**: Uzak sunucudaki değişiklikleri yerel dosyalara eklemeye yarar. `git pull`
9. **Fork (Çatal)**: Başkasının (ya da kendinizin) yaptığı bir projeyi sizin de repolarınız arasına ekler ve bu projede değişiklik yapabilir, daha sonra pull request'te bulunabilirsiniz.
10. **Pull Request (Çekme isteği)**: Bir repoyu forkladınız, `git clone` diyerek yerel bilgisayarınıza indirdiniz. Kodları incelerken bazı buglar ya da typolar (yazım yanlışı) buldunuz. Bunları düzelttiniz, `git add --all` diyerek git'e eklediniz ve `git commit -m "Bazı hatalar ve yazım yanlışları buldum` diyerek commitlediniz. Daha sonra `git push -u origin main` diyerek de uzak sunucuya push'ladınız. Bu durumda sadece kendi reponuzdaki hataları düzelttiniz ama asıl forkladığınız repo'da hata ve typolar hala duruyor. Bu durumda ne yapmanız gerekir? Ne yapmalısınız da kendi reponuzdaki değişiklikleri reponun asıl maintainer'ine de ileteceksiniz? İşte bu durumda yapmanız gereken şey bir pull request oluşturmak olacaktır.

## Git Commit Desenleri

Git commit mesajlarınızı yazarken belirli bir deseni takip etmek projenin daha iyi yönetilmesine yardımcı olur. Bu desenler, commit mesajlarının daha okunabilir ve anlaşılır olmasını sağlar.

### Geleneksel (Conventional) Commit Mesajları

Tip, kapsam ve açıklama olmak üzere üç bölümden oluşan geleneksel commit mesajları, commit'in amacını ve etkilediği alanı vurgular.

- **Tip**: Commit'in amacını belirtir.
- **Kapsam**: Commit'in etkilediği alanı belirtir.
- **Açıklama**: Commit'in detaylarını belirtir.

```shell
<tip>[kapsam, zorunlu değil]: <açıklama>

[zorunlu olmayan mesaj metni]

[zorunlu olmayan alt metin(ler)]
```

```shell
git commit -m "docs: update conventional commit guidelines"
```

```shell
git commit -m "fix(login): add validation for empty password field"
```

Commit mesajında tip seçimi zorunludur ve sadece 1 adet tip seçilmelidir. Kapsam belirtmek opsiyoneldir.

Aşağıdaki başlıklarda, commit mesajlarında kullanılan tiplere ve açıklamalara yer verilmiştir.

1. **test**: herhangi bir test kodu oluşturma veya değiştirme işlemini gösterir.
Örnek: Birim testlerinin oluşturulması.
2. **feat**: projeye yeni bir özellik geliştirildiğini gösterir.
Örnek: Bir hizmet, işlevsellik, uç nokta vb. eklenmesi.
3. **refactor**: sistem mantığı/kurallarını etkilemeyen kod yeniden düzenlemesi olduğunda kullanılır.
Örnek: Kod incelemesinden sonra kod değişiklikleri.
4. **style**: kod biçimlendirme ve stili değiştiğinde ve sistemi herhangi bir şekilde değiştirmediğinde kullanılır.
Örnek: Stil kılavuzunu değiştirme, lint kuralını değiştirme, girintileri düzeltme, beyaz boşlukları kaldırma, yorumları kaldırma vb.
5. **fix**: sistemi hatalar oluşturan hataları düzeltmek için kullanılır.
Örnek: Beklendiği gibi davranmayan ve hata döndüren bir işlev için bir işleme uygulama.
6. **chore**: sistemi veya test dosyalarını etkilemeyen proje değişikliklerini gösterir. Bunlar geliştirme değişiklikleridir.
Örnek: eslint kurallarını değiştirme, prettier ekleme, .gitignore'a daha fazla dosya uzantısı ekleme
7. **docs**: projedeki belgelerde değişiklik olduğunda kullanılır.
Örnek: API belgelerine bilgi ekleme, README'yi değiştirme vb.
8. **build**: projenin yapım sürecini veya harici bağımlılıklarını etkileyen değişiklikleri göstermek için kullanılır.
Örnek: Gulp, npm bağımlılıklarını ekleme/kaldırma vb.
9. **perf**: sistem performansını artıran bir değişikliği gösterir.
Örnek: ForEach'ü While ile değiştirme vb.
10. **ci**: CI yapılandırma dosyalarında değişiklikler için kullanılır.
Örnek: Circle, Travis, BrowserStack vb.
11. **revert**: önceki bir işlemi geri almaya işaret eder.
