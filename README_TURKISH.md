# Cosmos Validator Kayıt Defteri

Bu depo REStake'ten çıkarılmış ve kabaca tekrar düzenlenmiş bir yapıya dönüştürülmüştür.

REStake'e özgü bir depo yapmak yerine, bu repo burada zincirde saklanamayan validator özniteliklerini tutmak için kullanılabilir.

Bunun amacı kendisini kanıtladıktan sonra [Cosmos](https://github.com/cosmos) organizasyonuna geçmesidir. Bunun rüyası, [Zincir Kayıt Defteri](https://github.com/cosmos/chain-registry)'nin validator versiyonu olmaktır.

**Bu çok fazla devam eden bir çalışmadır ve tüm yorumlar hoş karşılanır.** Herhangi bir fikriniz veya öneriniz varsa lütfen bir Sorun (Issue) gönderin.

## Yapı

Her bir validator işleminin kendi dizini vardır. Bu dizinin içinde şu anda iki dosya bulunmaktadır:

### profile.json

İşleminiz için genel ad ve [keybase.io](https://keybase.io/) PGP parmak izi kimliği. Bu, şu anda REStake'de kullanılmıyor, ancak kaydınıza ek açıklamaya yardımcı oluyor.

```JSON
{
  "$schema": "../profile.schema.json",
  "name": "ECO Stake 🌱",
  "identity": "5992A6D423A406D6"
}
```

### chains.json

Validatorunuz için zincir bilgileri ve REStake özellikleri.

```JSON
{
  "$schema": "../chains.schema.json",
  "name": "ECO Stake 🌱",
  "chains": [
    {
      "name": "akash",
      "address": "akashvaloper1xgnd8aach3vawsl38snpydkng2nv8a4kqgs8hf",
      "restake": {
        "address": "akash1yxsmtnxdt6gxnaqrg0j0nudg7et2gqczud2r2v",
        "run_time": [
          "09:00",
          "21:00"
        ],
        "minimum_reward": 1000
      }
    },
    {
      "name": "cerberus",
      "address": "cerberusvaloper1tat2cy3f9djtq9z7ly262sqngcarvaktr0w78f",
      "restake": {
        "address": "cerberus1yxsmtnxdt6gxnaqrg0j0nudg7et2gqczd38dxa",
        "run_time": "every 15 minutes",
        "minimum_reward": 100000000
      }
    },
    ...
}
```

## JSON API 

Validator kayıt defteri, [validators.cosmos.directory](https://validators.cosmos.directory) adresinden bir JSON API'si aracılığıyla kullanılabilir. Bu API'nın yapısı, büyük bir sürüm numarasına ulaşana kadar yakın gelecekte değişebilir.

Örnek uç noktalar:

- [validators.cosmos.directory](https://validators.cosmos.directory)
- [validators.cosmos.directory/ecostake](https://validators.cosmos.directory/ecostake)
- [validators.cosmos.directory/ecostake/profile](https://validators.cosmos.directory/ecostake/profile)
- [validators.cosmos.directory/ecostake/chains](https://validators.cosmos.directory/ecostake/chains)
- [validators.cosmos.directory/chains/osmosis](https://validators.cosmos.directory/chains/osmosis)

## Katkı

İşleminize istediğiniz değişiklikleri yapın. Bir PR gönderin ve mümkün olan en kısa sürede birleştirilecektir. - REStake, bu depodan otomatik olarak güncellenir, böylece bu işlemi çok hızlandırır.

Kayıt defterinin bir bütün olarak geliştirilmesine katkıda bulunmak istiyorsanız, sorunları (Issues) kontrol edin ya da Discord/Twitter/E -posta/nerede olursa olsun iletişime geçin.
