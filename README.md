# İnci Akademi — Video Portalı

Şirket içi eğitim videolarını barındıran modern web portalı. Sıfır backend, tamamen statik.

## Kurulum (10 dakika)

### 1. Repo oluştur
```bash
# GitHub'da yeni repo aç: inci-video-portal
git clone https://github.com/KULLANICI_ADIN/inci-video-portal
cd inci-video-portal
# Bu dosyaları kopyala
git add . && git commit -m "init" && git push
```

### 2. GitHub Pages aç
`Settings → Pages → Source: GitHub Actions` seç. Push ettikten sonra otomatik deploy edilir.

### 3. Video ekle
`videos.json` dosyasını düzenle:

```json
{
  "id": "9",
  "title": "Video Başlığı",
  "description": "Açıklama",
  "category": "SAP ERP",
  "tags": ["SAP"],
  "duration": 1800,
  "views": 0,
  "date": "2026-03-30",
  "youtube_id": "YouTube_Video_ID",
  "new": true
}
```

**Kategoriler:** `SAP ERP` · `CRM` · `İnsan Kaynakları` · `Finans` · `Genel`

### 4. Gerçek video bağla

**Seçenek A — YouTube Unlisted:**
- YouTube'a yükle → Görünürlük: "Gizli (Unlisted)"
- Video ID'yi `youtube_id` alanına yaz

**Seçenek B — SharePoint Stream URL:**
- `youtube_id` alanını sil
- `"url": "sharepoint_stream_linki"` ekle
- Native HTML5 player otomatik devreye girer

## Özellikler

- Dark / Light mod (localStorage'da saklanır)
- Gerçek zamanlı arama
- Kategori filtreleme (sidebar + pill)
- İzleme ilerlemesi (localStorage — tarayıcı başına)
- "Tamamlandı" işaretleme
- YouTube embed veya native HTML5 player
- Mobil uyumlu

## Mimari

```
GitHub Repo
├── index.html      # Tüm uygulama (tek dosya)
├── videos.json     # Video kataloğu (burası güncellenir)
└── .github/
    └── workflows/
        └── deploy.yml  # Otomatik GitHub Pages deploy
```

Entra ID SSO ve Graph API entegrasyonu sonraki faz için hazır mimari.
