# Veri modeli (taslak)

> Taslak. Ekip toplantısında onaylanacak.

Dört kayıt türü (`need`, `offer`, `safe`, `missing`) tek bir `records` yapısını paylaşır.
Her alan bir değer ve bir HLC zaman damgası taşır.

| Alan | Tür | Kimde | Açıklama |
| --- | --- | --- | --- |
| `id` | UUID | hepsi | Telefonda üretilir |
| `type` | metin | hepsi | `need`, `offer`, `safe`, `missing` |
| `category` | metin | need, offer | su, gıda, ilaç, barınma, giyim, ulaşım, sağlık, diğer |
| `urgency` | sayı 1–3 | need | 1 düşük, 2 orta, 3 yüksek |
| `description` | metin (isteğe bağlı) | hepsi | Sağlık detayı zorunlu değil (KVKK) |
| `geohash` | metin | hepsi | Yaklaşık konum, herkese görünür |
| `lat`, `lng` | ondalık | hepsi | Tam konum; yalnızca eşleşme kabul edilince açılır |
| `radius_km` | sayı | offer | Teklifin ulaşabileceği mesafe |
| `available_until` | tarih-saat | offer | Teklifin geçerlilik süresi |
| `status` | metin | hepsi | `open` → `matched` → `in_progress` → `resolved` / `expired` |
| `neighborhood_id` | metin | hepsi | Kaydın mahallesi |
| `created_by` | UUID | hepsi | Kaydı oluşturan kullanıcı |
| `created_at`, `expires_at` | tarih-saat | hepsi | Varsayılan süre 24 saat |
| `photo_url` | metin (isteğe bağlı) | hepsi | Fotoğraf |
| `deleted` | evet/hayır | hepsi | Silme işareti (tombstone) |

## Birleştirme kuralları

- Her alan için HLC damgası büyük olan kazanır (last-writer-wins).
- `status` geri gitmez: sırası ileride olan kazanır (`open < matched < in_progress < resolved/expired`).
- `deleted = true` bir kez olduktan sonra geri alınmaz.

## Eşleşmeler

`matches`: `need_id`, `offer_id`, `score`, `strategy`, `need_accepted`, `offer_accepted`.
İki kabul ayrı alanlardır, böylece iki tarafın yazdığı birbirini ezmez.

## Toplantıda karar verilecekler

- [ ] Kategori listesi
- [ ] Aciliyet 3 seviye mi, 5 mi?
- [ ] Kayıt kaç saatte düşsün?
- [ ] Yaklaşık konum hassasiyeti (geohash 6 ≈ 1 km)
- [ ] Fotoğraf ilk sürümde olacak mı?
- [ ] Backend dili: Spring Boot mu, NestJS mi?
