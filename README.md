# **Git Türkçe Kullanma Kılavuzu**

Merhaba. Bu repo'da Git ve GitHub'ı dilim döndüğünce ve basit bir şekilde anlatmaya çalışacağım. Lütfen eksik ya da hatalı gördüğünüz konular için PR açmaktan çekinmeyin. :)

## Git Nedir?

Git bir versiyon kontol yazılımıdır ve Linux'un yaratıcısı Linus Torvalds [@torvalds](https://github.com/torvalds) tarafından geliştirilmiştir.

## Neden Git Kullanırız?

Tanımından da anlaşılabileceği üzere, yazılımların versiyonlarını düzenli bir şekilde kontrol etmek için Git'i kullanırız.

Mesela bir yazılım geliştirdiniz ve bunu bir bulutta saklıyorsunuz. Bulutta sakladığınız şey, aslında yazılımın son halidir. Ama GitHub'da saklasaydınız projenin her aşamasını görebilir, yeri geldiğinde yaptığınız değişiklikleri geri alabilir, başka insanların da bu projeye katkıda bulunmasını sağlayabilirdiniz.

## Git Buysa, GitHub Ne?

Güzel soru. Bu soruyu cevaplamadan önce Git'in tanımına dönelim: Git bir versiyon kontol **yazılımıdır**. Yani Git bir yazılımdır. GitHub ise bu yazılım üstüne inşa edilmiş bir **servistir**.

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
6. **Push (İtme)**: Commit ettiğiniz değişikliklerin uzak sunucuya gönderilmesi demektir. `git push`
   1. **Branch**: Projenizin farklı versiyonlarına erişmenize, değişiklik yapmanıza ve kullanmanıza yarar. Push ederken `-u` flag'i ile belirtilir: `git push -u **origin main**`. İlk etapta (git öğrenmeye başlarken yani) branch kullanmanız pek gerekmiyor.
7. **Pull (Çekme)**: Uzak sunucudaki değişiklikleri yerel dosyalara eklemeye yarar. `git pull`
8. **Fork (Çatal)**: Başkasının (ya da kendinizin) yaptığı bir projeyi sizin de repolarınız arasına ekler ve bu projede değişiklik yapabilir, daha sonra pull request'te bulunabilirsiniz.
9. **Pull Request (Çekme isteği)**: Bir repoyu forkladınız