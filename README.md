# Yusuf Testi

Oyun: `index.html` · Cevap paneli: `panel.html` · Cevaplar Google Sheets'e kaydedilir (`apps-script.gs`).

## 1. Cevapların kaydedileceği tablo (bir kere, ~2 dakika)

1. sheets.new adresine git, boş bir tablo aç, adını "Yusuf Testi Cevapları" yap.
2. Menüden **Uzantılar > Apps Script**.
3. Açılan editördeki her şeyi sil, `apps-script.gs` dosyasının içeriğini yapıştır, kaydet.
4. Sağ üstte **Dağıt > Yeni dağıtım** > türü **Web uygulaması** seç.
   - Şu kullanıcı olarak yürüt: **Ben**
   - Erişimi olanlar: **Herkes**
5. **Dağıt**'a bas, Google izin isterse kendi hesabını seç ve izin ver
   ("Google bu uygulamayı doğrulamadı" çıkarsa: Gelişmiş > devam et).
6. Çıkan **Web uygulaması URL'sini** kopyala ve `config.js` içindeki `SCRIPT_URL = ''` tırnaklarının arasına yapıştır.

## 2. GitHub'a gönderip ücretsiz yayınlama

Terminal'de:

```bash
cd ~/yusuf-testi
git init -b main && git add . && git commit -m "Yusuf testi"
gh repo create yusuf-testi --public --source=. --push
gh api -X POST repos/josephyusuff/yusuf-testi/pages -f "source[branch]=main" -f "source[path]=/"
```

Bir iki dakika sonra:

- Oyun: https://josephyusuff.github.io/yusuf-testi/
- Panel: https://josephyusuff.github.io/yusuf-testi/panel.html (şifre: `apps-script.gs` içindeki PANEL_KEY)

Not: `apps-script.gs` dosyası şifreyi içerdiği için GitHub'a gönderilmez (`.gitignore`).
