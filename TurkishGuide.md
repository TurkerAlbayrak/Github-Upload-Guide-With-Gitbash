# 🚀 Git Bash Kullanarak Proje/Dosyayı GitHub'a Yükleme

**Açıklama:** Bu rehber, Git Bash kullanarak yerel proje dosyalarınızı GitHub'a yüklemek için adım adım, başlangıç seviyesine uygun bir kılavuzdur. Her adım detaylı olarak açıklanmış, ipuçları, sık yapılan hatalar ve çözüm önerileri eklenmiştir. İlk defa kullananlar bile kolayca takip edebilir. 🎉

---

## 📌 Adımlar

### 1️⃣ GitHub'da Bir Depo Oluşturun

* GitHub hesabınıza giriş yapın ve **New Repository** butonuna tıklayın 🆕.
* Depo adını girin (örneğin: `ilk-projem`) ve isteğe bağlı olarak açıklama ekleyin.
* Depo görünürlüğünü seçin: **Public 🔓** veya **Private 🔒**.
* İsteğe bağlı olarak bir **README.md** dosyası ekleyin.
* **Create Repository** butonuna tıklayın ✅.

### 2️⃣ Git Bash (veya Terminal) Açın

* Bilgisayarınızda Git Bash'i açın.
* Proje klasörünüze gidin:

  ```bash
  cd yol/projenizin/klasoru
  ```
* **İpucu:** Doğru klasörde olup olmadığınızı görmek için `ls` (Linux/macOS) veya `dir` (Windows) komutunu kullanın.

### 3️⃣ Projede Git Başlatın

* Aşağıdaki komutu çalıştırın:

  ```bash
  git init
  ```
* **Not:** Bu, projenizde değişiklikleri takip edecek `.git` klasörünü oluşturur.

### 4️⃣ Dosyaları Git'e Ekleyin

* Tüm dosyaları ekleyin:

  ```bash
  git add .
  ```
* Sadece belirli dosyaları eklemek için:

  ```bash
  git add index.html style.css
  ```

### 5️⃣ Değişiklikleri Commit Edin

* Değişiklikleri anlamlı bir mesaj ile kaydedin:

  ```bash
  git commit -m "İlk commit"
  ```

* **İpucu:** Commit mesajları yapılan değişikliği açıklamalıdır.

* **Yaygın hata:** `error: author identity unknown`

  * **Çözüm:** Adınızı ve e-posta adresinizi ayarlayın:

    ```bash
    git config --global user.name "Adınız"
    git config --global user.email "email@ornek.com"
    ```

### 6️⃣ Yerel Depoyu GitHub'a Bağlayın

* GitHub depo URL'sini kopyalayın, örn: `https://github.com/kullaniciadi/proje.git`
* Yerel depoyu remote ile bağlayın:

  ```bash
  git remote add origin https://github.com/kullaniciadi/proje.git
  ```
* **Yaygın hata:** `fatal: remote origin already exists`

  * **Çözüm:** Önce mevcut origin'i silin:

    ```bash
    git remote remove origin
    git remote add origin https://github.com/kullaniciadi/proje.git
    ```

### 7️⃣ Projeyi GitHub'a Gönderin (Push)

* Projeyi remote depoya gönderin:

  ```bash
  git push origin master
  ```
* **Not:** Eğer varsayılan branşınız `main` ise kullanın:

  ```bash
  git push origin main
  ```
* **Yaygın hatalar ve çözümleri:**

  * `error: failed to push some refs` → Yerel branş remote'dan geride:

    ```bash
    git pull origin main --allow-unrelated-histories
    git push origin main
    ```
  * `fatal: Authentication failed` → Doğru GitHub bilgilerini kullanın veya şifre yerine **Personal Access Token (PAT)** kullanın.

### 8️⃣ Projenizin Yüklendiğini Kontrol Edin

* GitHub depo URL'sine gidin.
* Tüm dosyalarınız başarıyla yüklendiğini göreceksiniz! 🎉

---

## ✅ Ekstra Notlar & İpuçları

### `.gitignore` Kullanımı

* Gereksiz dosyaların yüklenmesini engellemek için `.gitignore` ekleyin (örn: `node_modules`, `.env`):

  ```bash
  touch .gitignore
  echo "node_modules/" >> .gitignore
  git add .gitignore
  git commit -m "Add .gitignore"
  ```

### Durum Kontrolü

* Hangi dosyaların staged, unstaged veya untracked olduğunu görmek için:

  ```bash
  git status
  ```

### Hataları Geri Alma

* Dosyayı stage'den çıkarın:

  ```bash
  git reset dosyaadi
  ```
* Son commit'i geri al (history korunur):

  ```bash
  git reset --soft HEAD~1
  ```
* Tüm yerel değişiklikleri iptal et (dikkat!):

  ```bash
  git reset --hard
  ```

### Branch Kullanımı

* Yeni branch oluştur:

  ```bash
  git branch yeni-ozellik
  ```
* Branch değiştirme:

  ```bash
  git checkout yeni-ozellik
  ```
* Branch'i main ile birleştirme:

  ```bash
  git checkout main
  git merge yeni-ozellik
  ```
* Branch silme:

  ```bash
  git branch -d yeni-ozellik
  ```

### Profesyonel İpuçları 💡

* Push etmeden önce her zaman pull yapın:

  ```bash
  git pull origin main
  ```
* Commitleri sık yapın, böylece geçmiş daha temiz olur.
* Anlamlı commit mesajları yazın, işbirliği kolaylaşır.
* Özellikler ve hatalar için branch kullanın.

---

🎉 Artık projeniz GitHub üzerinde canlı ve Git Bash kullanarak yönetmeye hazırsınız!
