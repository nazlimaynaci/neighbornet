# NeighborNet

Depremler için çevrimdışı öncelikli (offline-first) mahalle dayanışma ve ihtiyaç eşleştirme platformu.
İstanbul Aydın Üniversitesi, Yazılım Geliştirme bitirme projesi (Güz 2026).

> NeighborNet 112, AFAD veya resmi acil durum servislerinin yerini almaz. Hayati tehlikede 112'yi arayın.

## Klasörler

| Klasör | İçerik | Sorumlu |
| --- | --- | --- |
| `mobile/` | Flutter mobil uygulama (Drift, çevrimdışı harita) | Nazlım Aynacı |
| `backend/` | Sunucu: sync API, PostgreSQL + PostGIS, kimlik doğrulama | Ömer Saydamoğlu |
| `web-panel/` | Koordinatör web paneli (React) | Talha Soydaş |
| `test-vectors/` | Birleştirme (merge) test senaryoları, mobil ve backend ortak kullanır | Hepsi |
| `docs/` | Veri modeli, sync sözleşmesi, tasarım notları | Hepsi |

## Yol haritası

| Tarih | Aşama |
| --- | --- |
| 19–25 Ekim | Hazırlık: veri modeli, sync sözleşmesi, kurulumlar |
| 26 Ekim–8 Kasım | Çevrimdışı prototip |
| 9–15 Kasım | **Ara sınav demosu**: iki telefon, internetsiz kayıt, sonra birleşme |
| 16–29 Kasım | Eşleştirme (M1–M3), bildirimler, web panel, güvenlik |
| 30 Kasım–13 Aralık | Simülatör deneyleri, kullanılabilirlik testi (SUS) |
| 14–18 Aralık | Hata düzeltme, rapor |
| 21–30 Aralık | **Final teslim** ve canlı demo |

## Çalışma kuralları

- `main` dalına doğrudan yazmayın; her iş için dal açın (`mobile/kayit-formu` gibi) ve Pull Request gönderin.
- Her PR'ı en az bir ekip arkadaşı inceler.
- İşler GitHub Issues'ta takip edilir.
