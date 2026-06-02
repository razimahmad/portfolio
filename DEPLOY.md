# razimahmadov.com — domen al + yayımla

Tam yol: **domen satın al** → **Netlify-a yüklə** → **DNS bağla** → **LinkedIn**

---

## Addım 1: Domen al (razimahmadov.com)

Bir registrar seçin (hamısı işləyir):

- [Namecheap](https://www.namecheap.com)
- [Porkbun](https://porkbun.com)
- [Cloudflare Registrar](https://www.cloudflare.com/products/registrar/)
- [GoDaddy](https://www.godaddy.com)

1. Saytda **razimahmadov.com** axtarın.
2. `.com` mövcuddursa **satın alın** (illik ~10–15 USD).
3. Ödənişdən sonra **Domain list** / **My domains** bölməsinə keçin — DNS idarəetməsi burada olacaq.

> **Məsləhət:** Əgər `razimahmadov.com` tutulubsa, `razimahmadov.dev` və ya `razim.dev` də yaxşı alternativdir (kodda URL-ləri dəyişmək lazım olar).

---

## Addım 2: Portfolio-nu Netlify-a yüklə

1. [https://app.netlify.com](https://app.netlify.com) — hesab açın (GitHub ilə də olar).
2. **Add new site** → **Deploy manually**.
3. Kompüterdə bu qovluğu sürükləyin:

   `C:\Users\user\Documents\portfolio`

   (içində `index.html`, `netlify.toml`, `og.svg` olmalıdır)

4. Deploy **Published** olanda müvəqqəti link alırsınız, məs: `https://random-name-123.netlify.app` — brauzerdə açıb yoxlayın.

### Netlify ayarları

| Sahə | Dəyər |
|------|--------|
| Build command | **boş** |
| Publish directory | `.` |

---

## Addım 3: Domeni Netlify-a bağla

1. Netlify → saytınız → **Domain management** → **Add a domain**.
2. `razimahmadov.com` yazın → **Verify**.
3. **Add domain alias** ilə `www.razimahmadov.com` da əlavə edin (www → əsas domenə yönlənsin).

Netlify iki yol təklif edir — **A** ən sadədir:

### Variant A — A + CNAME (registrar-da qalırsınız)

Netlify **DNS configuration** ekranında göstərilən qeydləri domain satdığınız yerdə əlavə edin:

| Tip | Host / Name | Value (Netlify göstərir) |
|-----|-------------|---------------------------|
| **A** | `@` | `75.2.60.5` (və ya Netlify-in verdiyi IP) |
| **CNAME** | `www` | `your-site-name.netlify.app` |

*(IP və netlify.app adı sizin paneldə fərqli ola bilər — həmişə Netlify-dakı rəqəmləri yazın.)*

### Variant B — Netlify DNS (nameserver)

Registrar-da **nameserver**-ləri Netlify-ın verdiyi 4 ünvana dəyişin. Sonra bütün DNS Netlify-da idarə olunur.

4. **HTTPS** → **Verify DNS** / **Provision certificate** — DNS yayılınca (5 dəq – 48 saat) avtomatik aktiv olur.
5. **Domain settings** → əsas domen kimi `razimahmadov.com` seçili olsun.

Yoxlama: [https://razimahmadov.com](https://razimahmadov.com) açılmalıdır.

---

## Addım 4: Yeniləmələr

Saytda dəyişiklik etdikdən sonra:

- **Manual deploy:** eyni qovluğu Netlify-a yenidən drag & drop, və ya
- **Git:** GitHub repo + Netlify **Import from Git** (sonrakı deploy avtomatik).

`index.html` artıq `https://razimahmadov.com` üçün canonical və LinkedIn önizləmə (`og:*`) ilə hazırdır.

---

## Addım 5: LinkedIn

1. Post: link olaraq **https://razimahmadov.com**
2. Profil → **Add profile section** → **Add link**
   - Title: `Portfolio`
   - URL: `https://razimahmadov.com`

---

## Tez-tez problemlər

| Problem | Həll |
|---------|------|
| Sayt açılmır | DNS 24 saata qədər gecikə bilər; [dnschecker.org](https://dnschecker.org) ilə `razimahmadov.com` yoxlayın |
| SSL xətası | Netlify-da **HTTPS** → **Verify DNS configuration** |
| Köhnə səhifə | Brauzer cache / gizli pəncərədə açın |
| www işləmir | `www` üçün CNAME əlavə edin |

---

## Xülasə checklist

- [ ] Domen alındı (`razimahmadov.com`)
- [ ] Portfolio Netlify-da publish
- [ ] Domain management-da domen əlavə
- [ ] Registrar-da A + CNAME (və ya nameserver)
- [ ] HTTPS yaşıl / aktiv
- [ ] https://razimahmadov.com işləyir
- [ ] LinkedIn-ə link qoyuldu
