# **Git Türkçe Kullanma Kılavuzu**

Merhaba. Bu repo'da Git ve GitHub'ı dilim döndüğünce ve basit bir şekilde anlatmaya çalışacağım. Lütfen eksik ya da hatalı gördüğünüz konular için PR açmaktan çekinmeyin. :)

- [**Git Türkçe Kullanma Kılavuzu İçindekiler**](#--git-t-rk-e-kullanma-k-lavuzu--)
  - [Git Nedir?](#git-nedir-)
  - [Neden Git Kullanırız?](#neden-git-kullan-r-z-)
  - [Git Buysa, GitHub Ne?](#git-buysa--github-ne-)
  - [Temel Git Başlıkları ve Git Komutları](#temel-git-ba-l-klar--ve-git-komutlar-)
  - [Git ve GitHub'ın örnek kullanımları.](#git-ve-github--n--rnek-kullan-mlar-)

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
6. **Clone (klon)**: Uzak sunucudaki bir repoyu bilgisayarınıza indirmeye yarar. `git clone https://github.com/onurravli/Git-Turkce-Kullanma-Kilavuzu`
7. **Push (İtme)**: Commit ettiğiniz değişikliklerin uzak sunucuya gönderilmesi demektir. `git push`
   1. **Branch**: Projenizin farklı versiyonlarına erişmenize, değişiklik yapmanıza ve kullanmanıza yarar. Push ederken `-u` flag'i ile belirtilir: `git push -u **origin main**`. İlk etapta (git öğrenmeye başlarken yani) branch kullanmanız pek gerekmiyor.
8. **Pull (Çekme)**: Uzak sunucudaki değişiklikleri yerel dosyalara eklemeye yarar. `git pull`
9. **Fork (Çatal)**: Başkasının (ya da kendinizin) yaptığı bir projeyi sizin de repolarınız arasına ekler ve bu projede değişiklik yapabilir, daha sonra pull request'te bulunabilirsiniz.
10. **Pull Request (Çekme isteği)**: Bir repoyu forkladınız, `git clone` diyerek yerel bilgisayarınıza indirdiniz. Kodları incelerken bazı buglar ya da typolar (yazım yanlışı) buldunuz. Bunları düzelttiniz, `git add --all` diyerek git'e eklediniz ve `git commit -m "Bazı hatalar ve yazım yanlışları buldum` diyerek commitlediniz. Daha sonra `git push -u origin main` diyerek de uzak sunucuya push'ladınız. Bu durumda sadece kendi reponuzdaki hataları düzelttiniz ama asıl forkladığınız repo'da hata ve typolar hala duruyor. Bu durumda ne yapmanız gerekir? Ne yapmalısınız da kendi reponuzdaki değişiklikleri reponun asıl maintainer'ine de ileteceksiniz? İşte bu durumda yapmanız gereken şey bir pull request oluşturmak olacaktır.

## Git ve GitHub'ın örnek kullanımları.

Sanırım bu kısım, yazıdaki en önemli ve işinize en çok yarayacak kısım. GitHub'a geçmeden önce, teme Git komutlarını gerçek hayat uygulamaları üstünden inceleyelim. Eğer bilgisayarınızda git kurulu değilse, işletim sisteminize göre git'i kurun. Ubuntu kullanıcıları `sudo apt-get install git` diyerek, Arch kullanıcıları `sudo pacman -S git` diyerek, Windows kullanıcıları da [bu adresten](https://git-scm.com/download/win) git kurabilirler.

### 1. git clone

Lütfen terminal ya da komut istemini açarak `git clone https://github.com/onurravli/benim-ilk-repom` yazın ve benim-ilk-repom isimli repoyu `clone`'layın. Bu komut, benim-ilk-repom isimli repoyu bilgisayarınıza indirecektir.

### 2. git add

Bu repo içinde merhaba-dunya.txt adında bir dosya oluşturun ve içine istediğiniz şeyleri yazın. Feel free!

Daha sonra `git add --all` ya da `git add merhaba-dunya.txt` komutuyla merhaba-dunya.txt dosyasını git'e ekleyin.