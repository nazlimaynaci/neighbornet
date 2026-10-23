# Mobil uygulama (Flutter)

Sorumlu: Nazlım Aynacı

## Kurulum

Depo kök klasöründe:

```bash
flutter create --org com.neighbornet --project-name neighbornet mobile
cd mobile
flutter run
```

## Planlanan paketler

`flutter_riverpod`, `go_router`, `drift`, `drift_flutter`, `flutter_map`, `latlong2`,
`connectivity_plus`, `dio`, `geolocator`, `uuid`, `firebase_messaging`, `flutter_secure_storage`

## Klasör yapısı (lib/)

```
core/      tema, router, 112 uyarı bileşeni
data/      Drift tabloları, repository'ler
sync/      outbox, senkronizasyon servisi
features/  auth, needs, offers, safety, map, matches, profile
```
