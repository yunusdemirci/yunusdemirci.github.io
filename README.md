# Yunus Emre Demirci — Personal Site

Statik, çok sayfalı bir akademik portfolyo. Bağımlılık yok; sadece HTML, CSS
ve birkaç satır JS.

## Dosyalar

| Dosya | Ne işe yarıyor |
|---|---|
| `index.html` | Ana sayfa — bio, araştırma alanları, yayınlar, konuşmalar, iletişim |
| `recommended-papers.html` | Konuya göre gruplanmış okuma listesi |
| `teaching.html` | Verdiğin/asistanlık ettiğin dersler ve ders notları |
| `blog.html` | Kısa yazılar / araştırma günlüğü |
| `cv.html` | Detaylı özgeçmiş |
| `styles.css` | Tüm sayfaların paylaştığı tek stil dosyası |
| `README.md` | Bu dosya |

> `recommended-papers.html`, `teaching.html`, `blog.html` ve `cv.html`
> şu an **yer tutucu içeriklerle** dolu. Sarı/bordo kutudaki "Note" satırı
> dahil, sen gerçek içeriği ekleyince silebilirsin.

## Yerelde önizleme

`index.html` dosyasına çift tıkla — tarayıcıda doğrudan açılır. Üst menüden
sayfalar arası gezinebilirsin.

İstersen küçük bir lokal sunucu da kullanabilirsin:

```bash
cd <bu-klasor>
python3 -m http.server 8000
# tarayıcıda: http://localhost:8000
```

## GitHub Pages'e deploy (en kısa yol)

1. GitHub'da yeni bir repo aç. Repo adı **`<kullanici-adin>.github.io`** olursa
   site doğrudan `https://<kullanici-adin>.github.io` adresinde yayınlanır.
   (Başka isim de olur; o zaman URL `https://<kullanici-adin>.github.io/<repo-adi>` olur.)
2. Bu klasördeki tüm dosyaları repoya yükle:
   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin git@github.com:<kullanici-adin>/<repo-adi>.git
   git push -u origin main
   ```
3. Repo'da **Settings → Pages**'e gir. **Source** olarak `Deploy from a branch`,
   **Branch** olarak `main` / `/ (root)` seç ve **Save**.
4. Birkaç dakika sonra site yayında olur.

## Özelleştirme ipuçları

- **Renk:** `styles.css` içindeki `--accent` değişkeni vurgu rengini (koyu
  bordo) belirliyor. Örneğin `#1f3a8a` (lacivert) ya da `#0a5c4a` (koyu
  yeşil) yaparak tüm sitenin tonunu tek satırda değiştirebilirsin.
- **Font:** Tipografi EB Garamond (gövde) + Inter (etiketler/menü). Google
  Fonts'tan çekiliyor; offline kullanmak istersen her dosyadaki Google Fonts
  `<link>` satırını silip sistem fontuna düşebilirsin.
- **Yeni yayın eklemek:** İlgili `<ol class="pubs">` listesinin sonuna yeni bir
  `<li>` ekle — numaralandırma CSS counter ile otomatik.
- **Yeni sayfa eklemek:** Mevcut sayfalardan birini kopyala, içeriği değiştir,
  sonra **her** sayfanın `<nav>` listesine yeni linki ekle (menü kopyala-yapıştır
  ile güncelleniyor; tek bir include mekanizması yok çünkü saf HTML).
- **İletişim linkleri:** `index.html` → Contact bölümündeki GitHub ve Google
  Scholar linkleri şu an boş profil sayfalarına gidiyor. Kendi URL'lerinle
  güncelle.
- **PDF yükleme:** `teaching.html` ve `cv.html` içindeki `href="#"` linklerini,
  PDF dosyalarını repoya yükledikten sonra `href="files/notes-1.pdf"` gibi
  güncelle.
