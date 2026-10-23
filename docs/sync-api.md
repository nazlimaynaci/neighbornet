# Sync sözleşmesi (taslak)

## `POST /sync`

Telefon, gönderilmemiş değişikliklerini ve en son bildiği sunucu sıra numarasını (`since`) gönderir.

```json
{
  "since": 1482,
  "changes": [
    {
      "id": "7f3c2a10-0000-0000-0000-000000000000",
      "type": "need",
      "fields": {
        "category": { "value": "ilaç", "hlc": "1760871600000:0:telA" },
        "urgency":  { "value": 3,      "hlc": "1760871600000:0:telA" },
        "status":   { "value": "open", "hlc": "1760871600000:0:telA" }
      }
    }
  ]
}
```

Sunucu değişiklikleri birleştirir ve telefonun bilmediği, aynı mahalledeki değişiklikleri döndürür:

```json
{ "changes": [ ], "since": 1490 }
```

## HLC biçimi

`<fiziksel zaman ms>:<sayaç>:<cihaz kimliği>`. Karşılaştırma sırası: zaman, sonra sayaç, sonra cihaz kimliği.
