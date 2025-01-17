# TON Fingerprints

![cover](img/banner.png)

This is a NFT Collection of unique digital fingerprints created based on the algorithm for generating basic rings using a noise texture. Like human fingerprints, you can now use them for the Web 3.0 and metaverse era as digital biometric information on The Open Network.

## Browser Extension

### Step 1

Google Chrome: Please navigate to [Tampermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?utm_source=usz) and install it.

![alt text](img/image-2.png)

### Step 2

Click 'Install' to install a TON Fingerprints [userscript](https://github.com/mir-one/fingerprints/releases).

![alt text](img/image-1.png)

### RRP

The list price, also known as the manufacturer's suggested retail price, or the recommended retail price, or the suggested retail price of a product is the price at which its manufacturer notionally recommends that a retailer sell the product.

$Price = {{AmountCollection-AmountGoup} \over Rarity}*100％$

$Stage_1 = Price$

$Stage_2 = {Price Stage_1 \over 3 }+ Price Stage_1$

$Stage_3 = {Price Stage_2 \over 3} + Price Stage_2$

$Stage_4 = {Price Stage_3 \over 3} + Price Stage_3$

$Stage_5 = {Price Stage_4 \over 3} + Price Stage_4$

$Stage_6 = {Price Stage_5 \over 3} + Price Stage_5$

$Floor = {Price Stage_6 \over AmountGroupSale} + Price Stage_6$

![alt text](img/image-3.png)

## Domain fingerprints.ton

[fingerprints.ton](http://fingerprints.ton)

![img](img/fingerprints.ton.png)

TON DNS is a service that allows users to assign a human-readable name to crypto wallets, smart contracts, and websites. With TON DNS, access to decentralized services is analogous to access to websites on the internet.

## Public entry proxies

For familiarization with TON Sites you can use one of the public entry proxies:

- **in1.ton.org** port 8080
- **in2.ton.org** port 8080
- **in3.ton.org** port 8080

You can set them in the settings of a regular browser as HTTP proxy server.

[TON DOCS](https://ton.org/docs/#/web3/sites-and-proxy)

[TON DNS](https://telegra.ph/TON-DNS-06-30)

[TON Sites, TON WWW, and TON Proxy](https://telegra.ph/TON-Sites-TON-WWW-and-TON-Proxy-09-29-2)

## TON Site

```bash
fingerprints@ton:~$

apt-get update && apt-get upgrade -y
apt-get install -y nginx
apt-get clean all

apt-get install -y systemd

# echo "daemon off;" >> /etc/nginx/nginx.conf
rm /var/www/html/index.nginx-debian.html
cp fingerprints.ton/index.html /var/www/html/index.nginx-debian.html
cp fingerprints.ton/images/03-logo_blue-2.svg /var/www/html/images/
cp fingerprints.ton/images/03-ton_logo_dark_background.svg /var/www/html/images/
...

mkdir -p /var/cache/swap/
dd if=/dev/zero of=/var/cache/swap/swap0 bs=64M count=64
chmod 0600 /var/cache/swap/swap0
mkswap /var/cache/swap/swap0
swapon /var/cache/swap/swap0
swapon -s

cd /root
mkdir TON
cd TON
apt-get update
apt install -y build-essential cmake clang openssl libssl-dev zlib1g-dev gperf wget git curl libreadline-dev ccache libmicrohttpd-dev
git clone --recurse-submodules https://github.com/SpyCheese/ton.git
mkdir build
cd build
cmake ../ton
wget https://ton-blockchain.github.io/global.config.json
cmake --build . --target lite-client
cmake --build . --target func
cmake --build . --target fift
cmake --build . --target tonlib-cli
cmake --build . --target rldp-http-proxy
cmake --build . --target generate-random-id

```

```bash
fingerprints@ton:~$
cd /root/TON
mkdir keyring
cd keyring
/root/TON/build/utils/generate-random-id -m adnlid
```

Copy key + adnlid

```bash
echo "adnl: "
read adnl_address

echo "IP: "
read ip_address_host

cd /root/TON
/root/TON/build/rldp-http-proxy/rldp-http-proxy -p 8080 -a $ip_address_host:3333 -A $adnl_address -L '*' -C /root/TON/build/global.config.json --verbosity 3
```

## 📊 Histogram

| ![Genesys](img/Genesis.png) | ![Count](<img/Count%20lines%20_Amount_,%20era%20Genesis%20(red).png>) |
| --------------------------- | --------------------------------------------------------------------- |
| ![Array](img/Array.png)     | ![Era](img/Era%20Genesis_Rarity%20vs%20_Era%20Genesis_Lines_.png)     |

### Rarity name

![RC](img/RarityCategory.png)

| Amount | Counter | Rarity | Price   | Category       | RU Category             |
| ------ | ------- | ------ | ------- | -------------- | ----------------------- |
| 2351   | 15      | 23,51% | 0,822   | Common         | Привлекательный         |
| 1597   | 16      | 15,97% | 0,826   | Infrequent     | Удивительно приятный    |
| 1453   | 14      | 14,53% | 1,010   | Extraordinary  | Необыкновенно красивый  |
| 987    | 17      | 9,87%  | 1,026   | Specialized    | Пленительный            |
| 898    | 13      | 8,98%  | 1,029   | Quirky         | Очаровательный          |
| 610    | 18      | 6,10%  | 1,111   | Unheard        | Впечатляющий            |
| 377    | 19      | 3,77%  | 1,404   | Inimitable     | Восхитительный          |
| 343    | 12      | 3,43%  | 1,745   | Unconventional | Завораживающий          |
| 238    | 11      | 2,38%  | 1,872   | Uncommonplace  | Удивительно ценный      |
| 233    | 20      | 2,33%  | 1,937   | Unparalleled   | Интригующий             |
| 212    | 10      | 2,12%  | 2,074   | Remarkable     | Необыкновенный          |
| 144    | 21      | 1,44%  | 2,357   | Rarefied       | Прекрасный              |
| 131    | 9       | 1,31%  | 3,471   | Outstanding    | Загадочный              |
| 89     | 22      | 0,89%  | 3,932   | Abnormal       | Превосходный            |
| 81     | 8       | 0,81%  | 5,248   | Curious        | Исключительный          |
| 55     | 23      | 0,55%  | 5,748   | Exceptionable  | Чудесный                |
| 50     | 7       | 0,50%  | 10,770  | Peculiar       | Трепетный               |
| 34     | 24      | 0,34%  | 10,889  | Unmatched      | Уникально выразительный |
| 31     | 6       | 0,31%  | 16,293  | Distinctive    | Удивительный            |
| 21     | 25      | 0,21%  | 27,678  | Precious       | Особенный               |
| 19     | 5       | 0,19%  | 36,937  | Exclusive      | Специфический           |
| 13     | 26      | 0,13%  | 49,900  | Unprecedented  | Необычный               |
| 12     | 4       | 0,12%  | 76,823  | Singular       | Особый                  |
| 8      | 27      | 0,08%  | 90,809  | Unusual        | Отличительный           |
| 7      | 3       | 0,07%  | 142,757 | Exceptional    | Неповторимый            |
| 2      | 28      | 0,02%  | 166,567 | Amazing        | Индивидуальный          |
| 1      | 1       | 0,01%  | 249,900 | Scarce         | Оригинальный            |
| 1      | 2       | 0,01%  | 249,900 | Uncommon       | Эксклюзивный            |
| 1      | 29      | 0,01%  | 249,900 | Rare           | Редкий                  |
| 1      | 30      | 0,01%  | 249,900 | Unique         | Уникальный              |

## Owner list

If nft has owner address on presale stage - it will be minted with that owner, if not it will be minted with minter as owner.
List [here](nfts.csv)

Example:

```csv
0
1
2,EQCjNf6y_RhVATipbgKpCBAa8h5z6mwIXv3oDY7UZRyv0w3m
```

This will create 3 NFTs. NFTs with index `0` and `1` will be owned by you wallet, while NFT with index `2` will be owned by `EQCjNf6y_RhVATipbgKpCBAa8h5z6mwIXv3oDY7UZRyv0w3m`

## Collection

Content: ipfs://bafkreidikvhz6epgy43qohc3bmqhz4rqekcvzguqebtbpgkw2qo36jr56y

```json
{
  "name": "TON Fingerprints",
  "description": "This is a collection of 10 000 unique digital fingerprints created based on the algorithm for generating basic rings using a noise texture. Like human fingerprints, you can now use them for the Web3 and Metaverse era as digital biometric information on The Open Network.",
  "image": "ipfs://bafkreigdf236ojpw3gyp7pgmbkfdfzok4odwpqkhvmvhpssxhujnhpqaam",
  "external_link": "https://nft.mir.one/fingerprints",
  "fee_recipient": "EQCjNf6y_RhVATipbgKpCBAa8h5z6mwIXv3oDY7UZRyv0w3m"
}
```

## Algorithm for generating basic rings using a noise texture

```glsl
vec2 hash2( vec2 p )
{
    p = vec2( dot(p,vec2(63.31,127.63)), dot(p,vec2(395.467,213.799)) );
    return -1.0 + 2.0*fract(sin(p)*43141.59265);
}

void main(void)
{
    float invzoom = 64.;
    vec2 uv = invzoom*((gl_FragCoord.xy-0.5*resolution.xy)/resolution.x);
    float bounds = smoothstep(9.,10.,length(uv*vec2(0.74,0.55)));

    float a=0.;
    vec2 h = vec2(floor(7.*time), 0.);
    for(int i=0; i<50; i++){
        float s=sign(h.x);
        h = hash2(h)*vec2(15.,20.);
        a += s*atan(uv.x-h.x, uv.y-h.y);
    }

    uv += (3-5.).*abs(hash2(h));

    a+=atan(uv.y, uv.x);

    float w = 0.8;
    float p=(1.-bounds)*w;
    float s = min(0.3,p);
    float l = length(uv)+0.319*a;

    float m = mod(l,2.);
    float v = (1.-smoothstep(2.-s,2.,m))*smoothstep(p,p+s,m);

    glFragColor = vec4(v,v,v,1.);
}
```

### Variations

Every Fingerprint can be composed of up to 10 properties:

1. Count - Line counter
2. Area - %Area of fingerprint
3. Perimeter - The length of the outside boundary of the fingerprint
4. Ellipse Major - Primary axis of the fingerprint ellipse
5. Minor - Secondary axis of the fingerprint ellipse
6. Angle - Angle is the angle between the primary axis and a line parallel to the X-axis of the fingerprint
7. Circularity - 4π ×[Area]/[Perimeter]² with a value of 1.0 indicating a perfect circle. As the value approaches 0.0, it indicates an increasingly elongated shape
8. Integrated density - The sum of the values of the pixels in the image fingerprint. This is equivalent to the product of Area and Mean Gray Value
9. Skewness - The third order moment about the mean
10. Kurtosis - The fourth order moment about the mean

### Metadata

SVG files include:

```xml
<metadata>
  <rdf:RDF
    xmlns:rdf = "http://www.w3.org/1999/02/22-rdf-syntax-ns#"
    xmlns:rdfs = "http://www.w3.org/2000/01/rdf-schema#"
    xmlns:dc = "http://purl.org/dc/elements/1.1/"
    xmlns:cc = "http://creativecommons.org/ns#">
    <cc:license rdf:resource="http://creativecommons.org/publicdomain/zero/1.0/deed.en"/>
    <cc:permits rdf:resource="http://creativecommons.org/ns#Reproduction"/>
    <rdf:Description about="https://nft.mir.one/fingerprints"
      dc:title="TON Fingerprints"
      dc:description="This is a unique digital fingerprint created based on the algorithm for generating basic rings using a noise texture. Like human fingerprints, you can now use it for the Web3 and Metaverse era as digital biometric information."
      dc:publisher="MIR | Machine Intelligence Research"
      dc:date="2022-02-22"
      dc:format="image/svg+xml"
      dc:language="en" >
      <dc:creator>
      <rdf:Bag>
        <rdf:li>EQBondcvD2_aOFADXSWJHs4ZazQDuEl9_wNvGGPxI8hGuOFU</rdf:li>
        <rdf:li>ipfs://bafkreihj7iub3fhmhq6jn62noukt5wxn3gv6bvcg7wmt6ywvlurefezckq</rdf:li>
      </rdf:Bag>
      </dc:creator>
    </rdf:Description>
  </rdf:RDF>
</metadata>
```

Getgems NFT + btn

```json
{
  "name": "Name",

  "description": "Description",

  "image": "link",

  "buttons": [
    {
      "label": "Open TON Fingerprints",

      "uri": "https://getgems.io/fingerprints"
    }
  ],

  "attributes": [
    {
      "trait_type": "Attribute",

      "value": "Value"
    }
  ]
}
```

### Scan

Telegram Mini App [Fingerprint Scanner](https://t.me/fingerprint_scanner_bot/scan)
| | | | |
|-|-|-|-|
|![image](https://github.com/mir-one/fingerprints/assets/24755187/d1a6cfc4-51ef-4835-8361-0119a00f186e) |![image](https://github.com/mir-one/fingerprints/assets/24755187/24385c99-c42c-4b0b-9d5e-e4ff4d1f215c) |![image](https://github.com/mir-one/fingerprints/assets/24755187/457bae64-1307-491e-a72d-a1468f2181a0) | ![image](https://github.com/mir-one/fingerprints/assets/24755187/b6d4bff2-c94d-472e-a138-c45533ace73f) |

FS is an exciting WebApp in which you have to scan digital fingerprints and earn bulbs and keys. Using an incredibly accurate scanner, your task is to recognize and collect fingerprints in order to get the maximum amount of game resources.

The main feature of the game is the motivation of players through the achievement standings. You will be able to compete with other players, comparing your results and rising in the ranking. Be the best and become the real masters of fingerprint scanning!

"Scanner" is based on the NFT collection of open source with [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) Universal license - [TON Fingerprints](https://getgems.io/collection/fingerprints). Unique and impressive fingerprints are waiting for you, which you can collect and use for your own purposes.

Immerse yourself in the fascinating world of fingerprint scanning, compete with friends and reach new heights in the "Scanner"!

#### Level system

![alt text](img/image.png)

The leveling system is the independent progression system in which players earn XP (Experience Points) at the end of a completed scanning and is displayed in the upper left corner of the main menu.

```typescript
export const getXpForNextLevel = (currentLevel: number) =>
  currentLevel ** 2 + currentLevel + 33;
```

![xp](img/XP%20vs%20_Level_.png)

| Level | XP    | With accumulation |
| ----: | ----- | ----------------- |
|     1 | 33    | 33                |
|     2 | 39    | 72                |
|     3 | 45    | 117               |
|     4 | 53    | 170               |
|     5 | 63    | 233               |
|     6 | 75    | 308               |
|     7 | 89    | 397               |
|     8 | 105   | 502               |
|     9 | 123   | 625               |
|    10 | 143   | 768               |
|    11 | 165   | 933               |
|    12 | 189   | 1122              |
|    13 | 215   | 1337              |
|    14 | 243   | 1580              |
|    15 | 273   | 1853              |
|    16 | 305   | 2158              |
|    17 | 339   | 2497              |
|    18 | 375   | 2872              |
|    19 | 413   | 3285              |
|    20 | 453   | 3738              |
|    21 | 495   | 4233              |
|    22 | 539   | 4772              |
|    23 | 585   | 5357              |
|    24 | 633   | 5990              |
|    25 | 683   | 6673              |
|    26 | 735   | 7408              |
|    27 | 789   | 8197              |
|    28 | 845   | 9042              |
|    29 | 903   | 9945              |
|    30 | 963   | 10908             |
|    31 | 1025  | 11933             |
|    32 | 1089  | 13022             |
|    33 | 1155  | 14177             |
|    34 | 1223  | 15400             |
|    35 | 1293  | 16693             |
|    36 | 1365  | 18058             |
|    37 | 1439  | 19497             |
|    38 | 1515  | 21012             |
|    39 | 1593  | 22605             |
|    40 | 1673  | 24278             |
|    41 | 1755  | 26033             |
|    42 | 1839  | 27872             |
|    43 | 1925  | 29797             |
|    44 | 2013  | 31810             |
|    45 | 2103  | 33913             |
|    46 | 2195  | 36108             |
|    47 | 2289  | 38397             |
|    48 | 2385  | 40782             |
|    49 | 2483  | 43265             |
|    50 | 2583  | 45848             |
|    51 | 2685  | 48533             |
|    52 | 2789  | 51322             |
|    53 | 2895  | 54217             |
|    54 | 3003  | 57220             |
|    55 | 3113  | 60333             |
|    56 | 3225  | 63558             |
|    57 | 3339  | 66897             |
|    58 | 3455  | 70352             |
|    59 | 3573  | 73925             |
|    60 | 3693  | 77618             |
|    61 | 3815  | 81433             |
|    62 | 3939  | 85372             |
|    63 | 4065  | 89437             |
|    64 | 4193  | 93630             |
|    65 | 4323  | 97953             |
|    66 | 4455  | 102408            |
|    67 | 4589  | 106997            |
|    68 | 4725  | 111722            |
|    69 | 4863  | 116585            |
|    70 | 5003  | 121588            |
|    71 | 5145  | 126733            |
|    72 | 5289  | 132022            |
|    73 | 5435  | 137457            |
|    74 | 5583  | 143040            |
|    75 | 5733  | 148773            |
|    76 | 5885  | 154658            |
|    77 | 6039  | 160697            |
|    78 | 6195  | 166892            |
|    79 | 6353  | 173245            |
|    80 | 6513  | 179758            |
|    81 | 6675  | 186433            |
|    82 | 6839  | 193272            |
|    83 | 7005  | 200277            |
|    84 | 7173  | 207450            |
|    85 | 7343  | 214793            |
|    86 | 7515  | 222308            |
|    87 | 7689  | 229997            |
|    88 | 7865  | 237862            |
|    89 | 8043  | 245905            |
|    90 | 8223  | 254128            |
|    91 | 8405  | 262533            |
|    92 | 8589  | 271122            |
|    93 | 8775  | 279897            |
|    94 | 8963  | 288860            |
|    95 | 9153  | 298013            |
|    96 | 9345  | 307358            |
|    97 | 9539  | 316897            |
|    98 | 9735  | 326632            |
|    99 | 9933  | 336565            |
|   100 | 10133 | 346698            |
|   101 | 10335 | 357033            |
|   102 | 10539 | 367572            |
|   103 | 10745 | 378317            |
|   104 | 10953 | 389270            |
|   105 | 11163 | 400433            |
|   106 | 11375 | 411808            |
|   107 | 11589 | 423397            |
|   108 | 11805 | 435202            |
|   109 | 12023 | 447225            |
|   110 | 12243 | 459468            |
|   111 | 12465 | 471933            |
|   112 | 12689 | 484622            |
|   113 | 12915 | 497537            |
|   114 | 13143 | 510680            |
|   115 | 13373 | 524053            |
|   116 | 13605 | 537658            |

This is a function that calculates the amount of experience needed to reach the next level in a game or progress system. The function takes the current level (as a number) and uses it to calculate the required experience.

The mathematical expression `currentLevel ** 2 + currentLevel + 33` is used inside the function, which consists of three parts:

1. `currentLevel ** 2` is squaring the current level. This value is added to the total amount of experience to increase it with each level.

2. `currentLevel` is the current level. It is added to the result of the first part of the expression to increase the amount of experience even more.

3. `33` is a constant value that is added to the result of the first two parts of the expression. It may represent some basic need for experience or an additional reward for reaching the next level.

As a result, the function returns the total amount of experience needed to reach the next level, based on the current level.

Example:

- 1 Lelel = 35 XP (Experience Points)
- 50 Level = 2583 XP
- 100 Level = 10133 XP

#### Weighted Random

This function takes an array of items as input and returns a randomly selected item based on their weights.

```typescript
interface Item {
  weight: number;
  [key: string]: any;
}

export function getWeightedRandomItem<T extends Item>(items: T[]): T {
  const weights = items.reduce((acc, item, i) => {
    acc.push(item.weight + (acc[i - 1] ?? 0));
    return acc;
  }, [] as number[]);
  const random = Math.random() * (weights.at(-1) ?? 0);
  return items[weights.findIndex((weight) => weight > random)];
}
```

The function starts by calculating the cumulative weights of the items. It uses the reduce method to iterate over the items array and calculate the cumulative weight for each item. The acc parameter represents the accumulator array, which starts with an empty array. For each item, the function calculates the cumulative weight by adding the item's weight to the previous cumulative weight in the accumulator array `(acc[i - 1] ?? 0)`. The `??` operator is used to handle the case when there is no previous cumulative weight, in which case it defaults to 0. The calculated cumulative weight is then pushed into the accumulator array `(acc.push(item.weight + (acc[i - 1] ?? 0)))`.

After calculating the cumulative weights, the function generates a random number between 0 and the last cumulative weight in the weights array `(weights.at(-1) ?? 0)`. The at method is used to access the element at the specified index, with negative values representing the position from the end of the array. The `??` operator is used to handle the case when there are no items in the array, in which case it defaults to `0`.

Finally, the function finds the index of the first cumulative weight in the weights array that is greater than the random number. It uses the findIndex method to iterate over the weights array and returns the index of the first element that satisfies the provided condition (weight > random).

The function then returns the item at the found index in the items array `(items[weights.findIndex((weight) => weight > random)])`, which represents the randomly selected item based on their weights.

```typescript
export const scanDrop: ScanDrop[] = [
  {
    itemId: "Unique",
    weight: 0.01, // = 0.01% or 1 / 10 000 Fingerprints
  },
  {
    itemId: "Rare",
    weight: 0.01,
  },
  {
    itemId: "Uncommon",
    weight: 0.01,
  },
  {
    itemId: "Scarce",
    weight: 0.01,
  },
  {
    itemId: "Amazing",
    weight: 0.02,
  },
  {
    itemId: "Exceptional",
    weight: 0.07,
  },
  {
    itemId: "Unusual",
    weight: 0.08,
  },
  {
    itemId: "Singular",
    weight: 0.12,
  },
  {
    itemId: "Unprecedented",
    weight: 0.13,
  },
  {
    itemId: "Exclusive",
    weight: 0.19,
  },
  {
    itemId: "Precious",
    weight: 0.21,
  },
  {
    itemId: "Distinctive",
    weight: 0.31,
  },
  {
    itemId: "Unmatched",
    weight: 0.34,
  },
  {
    itemId: "Peculiar",
    weight: 0.5,
  },
  {
    itemId: "Exceptionable",
    weight: 0.55,
  },
  {
    itemId: "Curious",
    weight: 0.81,
  },
  {
    itemId: "Abnormal",
    weight: 0.89,
  },
  {
    itemId: "Outstanding",
    weight: 1.31,
  },
  {
    itemId: "Rarefied",
    weight: 1.44,
  },
  {
    itemId: "Remarkable",
    weight: 2.12,
  },
  {
    itemId: "Unparalleled",
    weight: 2.33,
  },
  {
    itemId: "Uncommonplace",
    weight: 2.38,
  },
  {
    itemId: "Unconventional",
    weight: 3.43,
  },
  {
    itemId: "Inimitable",
    weight: 3.77,
  },
  {
    itemId: "Unheard",
    weight: 6.1,
  },
  {
    itemId: "Quirky",
    weight: 8.98,
  },
  {
    itemId: "Specialized",
    weight: 9.87,
  },
  {
    itemId: "Extraordinary",
    weight: 14.53,
  },
  {
    itemId: "Infrequent",
    weight: 15.97,
  },
  {
    itemId: "Common",
    weight: 23.51,
  },
  {
    itemId: "facquire", // failure acquire
    weight: 20, // = 20%
    isFailure: true,
  },
  {
    itemId: "fenroll", // failure enroll
    weight: 20,
    isFailure: true,
  },
];
```

### License

1. CC0
2. Universal NFT License

### Attribution

```json
{
  "attributes": [
    {
      "trait_type": "Count",
      "value": 1
    },
    {
      "trait_type": "Area",
      "value": 2
    },
    {
      "trait_type": "Perimeter",
      "value": 3
    },
    {
      "trait_type": "Major",
      "value": 4
    },
    {
      "trait_type": "Minor",
      "value": 5
    },
    {
      "trait_type": "Angle",
      "value": 6
    },
    {
      "trait_type": "Circularity",
      "value": 7
    },
    {
      "trait_type": "Integrated density",
      "value": 8
    },
    {
      "trait_type": "Skewness",
      "value": 9
    },
    {
      "trait_type": "Kurtosis",
      "value": 10
    }
  ]
}
```

## Donation

[Fingerprints.ton](https://tonapi.io/account/EQCjNf6y_RhVATipbgKpCBAa8h5z6mwIXv3oDY7UZRyv0w3m)

Jetton Donation

[EQDEcJlTPBymzUqOJ15QR44vIlPIHhsWllrIafWpPdeHiuNR](https://tonapi.io/account/EQDEcJlTPBymzUqOJ15QR44vIlPIHhsWllrIafWpPdeHiuNR)
