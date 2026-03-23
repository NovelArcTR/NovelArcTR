╔═══════════════════════════════════════════════════════════════════════════════╗
║                                                                               ║
║  🚀 NOVELARC - GITHUB + SUPABASE + VERCEL DEPLOYMENT REHBERİ                 ║
║                                                                               ║
║             TAM HAZıR KOD - GITHUB'A DOĞRUDAN DEPLOY YAPACAKSINIZ             ║
║                                                                               ║
║                          A'DAN Z'YE TÜRKÇE REHBER                           ║
║                                                                               ║
╚═══════════════════════════════════════════════════════════════════════════════╝

BÖLÜM İÇİNDEKİLER:

1. ÖN HAZIRLIK
2. GITHUB KURULUMU
3. SUPABASE KURULUMU  
4. VERİTABANI OLUŞTURMA
5. VERCEL DEPLOYMENT
6. SUPABASE API ANAHTARLARINI EKLEME
7. SİTE AYARLARINI GÜNCELLEME
8. DEPLOYMENT BAŞLATMA
9. DOĞRULAMA VE TEST
10. SORUN GİDERME

═══════════════════════════════════════════════════════════════════════════════

BÖLÜM 1: ÖN HAZIRLIK

Başlamadan önce şu hesapları açın (TAM BEDAVA):

1.1 GitHub Hesabı Açma
─────────────────────────────────────────────────────────────────────────────────

ADIM 1:
  Tarayıcıda: https://github.com

ADIM 2:
  Sağ üst "Sign up" tıklayın

ADIM 3:
  Formu doldurun:
  • Email: Gerçek email adresiniz
  • Password: Güçlü şifre (not alın!)
  • Username: novelarc (veya başka isim)

ADIM 4:
  "Create account" tıklayın

ADIM 5:
  Email doğrulamasını yapın (mailinize kod gelecek)

✅ GitHub hesabınız hazır!


1.2 Supabase Hesabı Açma
─────────────────────────────────────────────────────────────────────────────────

ADIM 1:
  Tarayıcıda: https://app.supabase.com

ADIM 2:
  "Sign up with GitHub" tıklayın (GitHub hesabınızla giriş)

ADIM 3:
  Supabase izinlerini onayla

✅ Supabase hesabınız hazır!


1.3 Vercel Hesabı Açma
─────────────────────────────────────────────────────────────────────────────────

ADIM 1:
  Tarayıcıda: https://vercel.com

ADIM 2:
  "Sign Up" tıklayın

ADIM 3:
  "Continue with GitHub" seçin

✅ Vercel hesabınız hazır!

═══════════════════════════════════════════════════════════════════════════════

BÖLÜM 2: GITHUB KURULUMU

2.1 Repository Oluşturma
─────────────────────────────────────────────────────────────────────────────────

ADIM 1:
  GitHub.com'a giriş yapın

ADIM 2:
  Sağ üst köşede "+" tıklayın

ADIM 3:
  "New repository" seçin

ADIM 4:
  Formu şöyle doldurun:

  Repository name:
  └─ novelarc-app

  Description (isteğe bağlı):
  └─ Türkçe Light Novel Okuma Platformu

  Public seçin:
  └─ ✓ Public (herkese açık)

  Initialize:
  └─ ✓ Add a README file
  └─ ✓ Add .gitignore: Node

ADIM 5:
  "Create repository" tıklayın

✅ GitHub repo oluşturuldu!


2.2 Bilgisayarınızda Kurulum
─────────────────────────────────────────────────────────────────────────────────

ADIM 1:
  Bilgisayarınızda Terminal/Command Prompt açın

ADIM 2:
  Git'i yapılandırın (ilk kez yapıyorsanız):

  $ git config --global user.name "Adınız"
  $ git config --global user.email "email@gmail.com"

ADIM 3:
  Repository'yi klonlayın:

  $ git clone https://github.com/KULLANICIADI/novelarc-app.git
  $ cd novelarc-app

  (KULLANICIADI yerine GitHub kullanıcı adınızı yazın)

ADIM 4:
  Dosyaların başarıyla indiğini kontrol edin:

  $ ls -la

  (Files listesi görülmelidir)

✅ Repository bilgisayarınızda var!


2.3 Proje Dosyalarını Ekleme
─────────────────────────────────────────────────────────────────────────────────

ADIM 1:
  ZIP'ten çıkarılan dosyaları (index.html, package.json, vercel.json vb.)
  klonladığınız novelarc-app klasörüne kopyalayın.

ADIM 2:
  Terminal'de:

  $ git status

  (Değişen dosyaları listeler)

ADIM 3:
  GitHub'a yükleyin:

  $ git add .
  $ git commit -m "İlk commit: NovelArc uygulaması"
  $ git push origin main

  Tarayıcıda GitHub refresh edin → dosyaları göreceksiniz!

✅ Kod GitHub'da!

═══════════════════════════════════════════════════════════════════════════════

BÖLÜM 3: SUPABASE KURULUMU

3.1 Yeni Proje Oluşturma
─────────────────────────────────────────────────────────────────────────────────

ADIM 1:
  Supabase Dashboard'da: https://app.supabase.com

ADIM 2:
  "New Project" tıklayın

ADIM 3:
  Formu doldurun:

  Name:
  └─ novelarc-prod

  Database Password:
  └─ (Güçlü şifre, not alın!)

  Region:
  └─ Istanbul (tr-ist) - Türkiye'den erişim hızlı olur

ADIM 4:
  "Create new project" tıklayın

ADIM 5:
  2-3 dakika bekleyin. Proje yükleniyor...

✅ Supabase projesi oluşturuldu!


3.2 API Anahtarlarını Alma
─────────────────────────────────────────────────────────────────────────────────

ADIM 1:
  Sol menüden: Settings → API

ADIM 2:
  İki değeri KOPYALAYıN (not alın veya sakla):

  Project URL:
  └─ https://xxxxx.supabase.co
     (Tam URL'yi al, SUPABASE_URL diye not et)

  anon public (API Key):
  └─ eyJhbGc...
     (Tam metni al, SUPABASE_KEY diye not et)

⚠️ ÖNEMLİ: Bu anahtarları kimseyle paylaşmayın!

✅ API anahtarları kaydedildi!

═══════════════════════════════════════════════════════════════════════════════

BÖLÜM 4: VERİTABANI OLUŞTURMA

4.1 SQL Script Çalıştırma
─────────────────────────────────────────────────────────────────────────────────

ADIM 1:
  Supabase Dashboard'da sol menü: SQL Editor

ADIM 2:
  "+ New Query" tıklayın

ADIM 3:
  Aşağıdaki SQL'i yapıştırın:

═══════════════════════════════════════════════════════════════════════════════
CREATE TABLE IF NOT EXISTS novels (
  id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
  title TEXT NOT NULL,
  author TEXT,
  description TEXT,
  content TEXT,
  chapters_count INTEGER DEFAULT 0,
  created_at TIMESTAMP DEFAULT now()
);

CREATE TABLE IF NOT EXISTS comments (
  id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
  novel_id UUID REFERENCES novels(id) ON DELETE CASCADE,
  user_id UUID DEFAULT NULL,
  user_email TEXT,
  content TEXT NOT NULL,
  created_at TIMESTAMP DEFAULT now()
);

INSERT INTO novels (title, author, description, content, chapters_count)
VALUES 
  ('Örnek Roman 1', 'Yazı Adı', 'Bu örnek bir roman açıklamasıdır.', 'Roman içeriğinin başladığı yer. Lorem ipsum dolor sit amet...', 5),
  ('Örnek Roman 2', 'Yazı Adı 2', 'İkinci roman açıklaması.', 'İkinci roman içeriğii...', 3);

═══════════════════════════════════════════════════════════════════════════════

ADIM 4:
  "Run" tıklayın

ADIM 5:
  "Success" mesajı görülmelidir

✅ Veritabanı tablolar oluşturuldu!

═══════════════════════════════════════════════════════════════════════════════

BÖLÜM 5: VERCEL DEPLOYMENT

5.1 Vercel'e GitHub Repo Bağlama
─────────────────────────────────────────────────────────────────────────────────

ADIM 1:
  Vercel Dashboard'da: https://vercel.com/dashboard

ADIM 2:
  "Add New..." tıklayın

ADIM 3:
  "Project" seçin

ADIM 4:
  "Import Git Repository" tıklayın

ADIM 5:
  GitHub'dan repository'yi seçin:
  └─ novelarc-app

ADIM 6:
  "Import" tıklayın

✅ Repository Vercel'e bağlandı!


5.2 Vercel Ayarları
─────────────────────────────────────────────────────────────────────────────────

ADIM 1:
  Project Settings → Environment Variables

ADIM 2:
  İki değişken ekleyin:

  Variable name: SUPABASE_URL
  Value: (Supabase'den aldığınız URL)

  Variable name: SUPABASE_KEY  
  Value: (Supabase'den aldığınız Key)

ADIM 3:
  "Save" tıklayın

✅ Ortam değişkenleri ayarlandı!

═══════════════════════════════════════════════════════════════════════════════

BÖLÜM 6: SUPABASE API ANAHTARLARINI EKLEME

6.1 index.html Dosyasını Güncelleme
─────────────────────────────────────────────────────────────────────────────────

ADIM 1:
  index.html dosyasını metin editörüyle açın (VS Code vs.)

ADIM 2:
  CTRL+F ile ara: "https://xxxxx.supabase.co"

ADIM 3:
  Bulduğunuz satırları değiştirin:

  ÖNCESİ:
  const SUPABASE_URL = 'https://xxxxx.supabase.co';
  const SUPABASE_KEY = 'your_key_here';

  SONRASI:
  const SUPABASE_URL = 'https://xxxxx.supabase.co'; // Aldığınız URL
  const SUPABASE_KEY = 'eyJhbGc...'; // Aldığınız Key

ADIM 4:
  Dosyayı kaydedin

ADIM 5:
  GitHub'a yükleyin:

  $ git add index.html
  $ git commit -m "Supabase anahtarları eklendi"
  $ git push origin main

✅ Supabase bağlantısı yapılandırıldı!

═══════════════════════════════════════════════════════════════════════════════

BÖLÜM 7: SİTE AYARLARINI GÜNCELLEME

7.1 Ana Başlık vs. Ayarlar
─────────────────────────────────────────────────────────────────────────────────

index.html'de şu satırları bulup değiştirebilirsiniz:

<title>NovelArc - Türkçe Light Novel Platformu</title>
  → Tarayıcı sekmesinde görünen başlık

<h1>Türkçe Light Novel Platformu</h1>
  → Ana sayfada görünen başlık

<p>Binlerce romanı ücretsiz okuyun, toplulukla paylaşın</p>
  → Ana sayfada görünen açıklama

İstediğiniz yerleri değiştirebilirsiniz!

═══════════════════════════════════════════════════════════════════════════════

BÖLÜM 8: DEPLOYMENT BAŞLATMA

8.1 Vercel'de Deploy
─────────────────────────────────────────────────────────────────────────────────

ADIM 1:
  Vercel Dashboard'da, projektinize gidin

ADIM 2:
  Otomatik olarak deploy başlayabilir, yoksa:
  "Deploy" düğmesine tıklayın

ADIM 3:
  Kurmaca başlayacak:
  "Building..." → "Ready" (1-2 dakika)

ADIM 4:
  "Ready" yazısını gördüğünde bitti!

ADIM 5:
  URL'i alacaksınız:
  https://novelarc-app.vercel.app (örnek)

✅ Site canlı!


8.2 Siteni Açma
─────────────────────────────────────────────────────────────────────────────────

ADIM 1:
  Vercel tarafından verilen URL'yi tarayıcıya yapıştırın

ADIM 2:
  Enter basın

ADIM 3:
  "NovelArc" başlığını göreceksiniz!

✅ Site açılıyor!

═══════════════════════════════════════════════════════════════════════════════

BÖLÜM 9: DOĞRULAMA VE TEST

9.1 Site Açılıyor mu?
─────────────────────────────────────────────────────────────────────────────────

✅ Site açılıyorsa → Mükemmel!
❌ Site açılmıyorsa → Bölüm 10: Sorun Giderme'ye bakın

9.2 Veriler Yükleniyor mu?
─────────────────────────────────────────────────────────────────────────────────

ADIM 1:
  "Romanları İncele" düğmesine tıklayın

ADIM 2:
  Veritabanına eklediğiniz romanları göreceksiniz:
  ✅ "Örnek Roman 1"
  ✅ "Örnek Roman 2"

✅ Supabase çalışıyor!

9.3 İnteraktiflik Testi
─────────────────────────────────────────────────────────────────────────────────

ADIM 1:
  Bir romana tıklayın

ADIM 2:
  Roman açılıp içeriği yüklenir

ADIM 3:
  Yorum yazın (giriş yap diyebilir - test amaçlı)

✅ Uygulama çalışıyor!

═══════════════════════════════════════════════════════════════════════════════

BÖLÜM 10: SORUN GİDERME

SORUN 1: "Build failed" mesajı
────────────────────────────────────────────────────────────────────────────────

Çözüm:
  1. Vercel'de "Deployments" sekmesine bakın
  2. Hata mesajını okuyun
  3. Genelde:
     - package.json hatalı
     - Dosya eksik
     - Söz dizimi hatası
  4. Hatayı düzeltin ve tekrar push edin


SORUN 2: "Supabase bağlantısı hatası"
────────────────────────────────────────────────────────────────────────────────

Çözüm:
  1. Tarayıcı konsolunu açın (F12)
  2. "Console" sekmesinde hata mesajını görün
  3. Kontrol edin:
     - SUPABASE_URL doğru mu?
     - SUPABASE_KEY doğru mu?
  4. Hatalıysa düzeltip push edin


SORUN 3: "Romanlar yüklenmediği"
────────────────────────────────────────────────────────────────────────────────

Çözüm:
  1. Supabase Dashboard'da SQL Editor'e gidin
  2. Tabloları ve verileri kontrol edin
  3. Veri gözükmüyorsa 4. Bölümü tekrarlayın


SORUN 4: "site.vercel.app açılmıyor"
────────────────────────────────────────────────────────────────────────────────

Çözüm:
  1. İnternet bağlantınızı kontrol edin
  2. Vercel deployments'ini kontrol edin
  3. "Ready" yazması gerekir
  4. GitHub'da değişiklikleri push ettiniz mi?


SORUN 5: "Git push hatası"
────────────────────────────────────────────────────────────────────────────────

SSH Key Hatası Çözümü:

  $ ssh-keygen -t ed25519 -C "email@example.com"

Sorular sorulacak, Enter'e basın.

Sonra GitHub'a key'i ekleyin:
  GitHub → Settings → SSH and GPG keys → New SSH key

~/.ssh/id_ed25519.pub dosyasının içeriğini kopyalayıp yapıştırın.

Şimdi push çalışacak.

═══════════════════════════════════════════════════════════════════════════════

BÖLÜM 11: KOD GÜNCELLEMESİ (Önemli!)

Kodunuzu güncellemek isterse:

ADIM 1:
  Bilgisayarınızda dosyayı değiştirin

ADIM 2:
  Terminal'de:

  $ git add .
  $ git commit -m "Değişiklik açıklaması"
  $ git push origin main

ADIM 3:
  Vercel otomatik olarak deploy eder

ADIM 4:
  1-2 dakika sonra site güncellenir

✅ Otomatik deployment çalışıyor!

═══════════════════════════════════════════════════════════════════════════════

🎉 BAŞARILI DEPLOYMENT!

Eğer buraya kadar geldiyseniz:

✅ GitHub'da kod
✅ Supabase'de veritabanı
✅ Vercel'de yayında
✅ İnternette canlı

Siteniz tamamlanmış!

Herkes ziyaret edebilir:
https://novelarc-app.vercel.app

═══════════════════════════════════════════════════════════════════════════════

💡 İPUÇLARI

1. Vercel Dashboard'dan "Analytics"'e bakarak ziyaretçileri görebilirsiniz

2. GitHub'da kod değişikliği yaparsanız, Vercel otomatik deploy eder

3. Supabase'de daha fazla roman ve veri ekleyebilirsiniz

4. Kendi alanınızı (domain) bağlayabilirsiniz (ücretli)

5. Konsolu açıp (F12) hataları görebilirsiniz

═══════════════════════════════════════════════════════════════════════════════

✨ SONUÇ

Artık:
• Professionel bir web siteniz var
• Veritabanı yönetimi öğrendiniz
• CI/CD (otomatik deploy) kullanıyorsunuz
• Açık kaynak geliştirmesi yapıyorsunuz

Bu beceriler gerçek işlerde kullanılır!

═══════════════════════════════════════════════════════════════════════════════

HIZLI REFERANS SAYFASI:

Supabase: app.supabase.com
GitHub: github.com/KULLANICIADI/novelarc-app
Vercel: vercel.com/dashboard
Site: https://novelarc-app.vercel.app

═══════════════════════════════════════════════════════════════════════════════
