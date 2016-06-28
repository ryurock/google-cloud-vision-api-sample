# google-cloud-vision-api-sample

google cloud vision api sample



## Usage

```
export GOOGLE_API_KEY=xxxxxxxxx
ruby vision-api-sample.rb
```

## 顔認証

FACE_DETECTION

```
    features: [
      {
        type: 'FACE_DETECTION',
        maxResults: 5
      }
```

### レスポンスフォーマット

顔情報

* 目
	* 右目の位置
	* 左目の位置
* 鼻の位置

等顔のパーツに沿った座標(x,y)と認識した付加情報が返ってくる

感情？情報は基本

* joy Likelihood (喜び可能性)
	* VERY_UNLIKELY (喜びではない)
	* VERY_LIKELY (喜びである)
* sorrowLikelihood (悲しみの可能性)
	* VERY_UNLIKELY (悲しみではない)
	* VERY_LIKELY (悲しみである)
* angerLikelihood (怒りの可能性)
	* VERY_UNLIKELY (怒りではない)
	* VERY_LIKELY (怒りである)
* surpriseLikelihood(驚きの可能性)
	* VERY_UNLIKELY (驚きではない)
	* VERY_LIKELY (驚きである)
* underExposedLikelihood (露出度が強い可能性???)
	* VERY_UNLIKELY (露出度が強くない可能性)
	* VERY_LIKELY (露出度が強い可能性)
* blurredLikelihood (ぼやけた可能性)
	* VERY_UNLIKELY (ぼやけていない可能性)
	* VERY_LIKELY (ぼやけた可能性)
* headwearLikelihood (帽子の可能性)
	* VERY_UNLIKELY (帽子ではない可能性)
	* VERY_LIKELY (帽子の可能性)

で出てくる。


```
          "joyLikelihood": "VERY_UNLIKELY",
          "sorrowLikelihood": "VERY_UNLIKELY",
          "angerLikelihood": "VERY_UNLIKELY",
          "surpriseLikelihood": "VERY_UNLIKELY",
          "underExposedLikelihood": "VERY_UNLIKELY",
          "blurredLikelihood": "VERY_UNLIKELY",
          "headwearLikelihood": "VERY_UNLIKELY"
```

### レスポンスサンプル

```
{
  "responses": [
    {
      "faceAnnotations": [
        {
          "boundingPoly": {
            "vertices": [
              {
                "x": 1003,
                "y": 1515
              },
              {
                "x": 2076,
                "y": 1515
              },
              {
                "x": 2076,
                "y": 2762
              },
              {
                "x": 1003,
                "y": 2762
              }
            ]
          },
          "fdBoundingPoly": {
            "vertices": [
              {
                "x": 1141,
                "y": 1844
              },
              {
                "x": 1932,
                "y": 1844
              },
              {
                "x": 1932,
                "y": 2634
              },
              {
                "x": 1141,
                "y": 2634
              }
            ]
          },
          "landmarks": [
            {
              "type": "LEFT_EYE",
              "position": {
                "x": 1270.097,
                "y": 2061.8894,
                "z": 0.00092600106
              }
            },
            {
              "type": "RIGHT_EYE",
              "position": {
                "x": 1547.0765,
                "y": 2075.8447,
                "z": -155.12715
              }
            },
            {
              "type": "LEFT_OF_LEFT_EYEBROW",
              "position": {
                "x": 1190.2661,
                "y": 1979.0829,
                "z": 79.894279
              }
            },
            {
              "type": "RIGHT_OF_LEFT_EYEBROW",
              "position": {
                "x": 1313.4816,
                "y": 1987.4095,
                "z": -95.871262
              }
            },
            {
              "type": "LEFT_OF_RIGHT_EYEBROW",
              "position": {
                "x": 1451.6733,
                "y": 1996.7168,
                "z": -172.78253
              }
            },
            {
              "type": "RIGHT_OF_RIGHT_EYEBROW",
              "position": {
                "x": 1665.6593,
                "y": 2010.9692,
                "z": -184.47379
              }
            },
            {
              "type": "MIDPOINT_BETWEEN_EYES",
              "position": {
                "x": 1376.29,
                "y": 2061.5564,
                "z": -137.46445
              }
            },
            {
              "type": "NOSE_TIP",
              "position": {
                "x": 1322.9983,
                "y": 2243.3623,
                "z": -218.20735
              }
            },
            {
              "type": "UPPER_LIP",
              "position": {
                "x": 1352.1196,
                "y": 2374.7056,
                "z": -149.89574
              }
            },
            {
              "type": "LOWER_LIP",
              "position": {
                "x": 1353.9309,
                "y": 2473.7861,
                "z": -128.5957
              }
            },
            {
              "type": "MOUTH_LEFT",
              "position": {
                "x": 1276.2567,
                "y": 2409.6316,
                "z": -11.399314
              }
            },
            {
              "type": "MOUTH_RIGHT",
              "position": {
                "x": 1494.0814,
                "y": 2429.4465,
                "z": -135.66414
              }
            },
            {
              "type": "MOUTH_CENTER",
              "position": {
                "x": 1357.1146,
                "y": 2419.2412,
                "z": -128.50845
              }
            },
            {
              "type": "NOSE_BOTTOM_RIGHT",
              "position": {
                "x": 1454.7615,
                "y": 2283.6389,
                "z": -152.06725
              }
            },
            {
              "type": "NOSE_BOTTOM_LEFT",
              "position": {
                "x": 1299.3383,
                "y": 2268.604,
                "z": -65.31311
              }
            },
            {
              "type": "NOSE_BOTTOM_CENTER",
              "position": {
                "x": 1352.9521,
                "y": 2295.936,
                "z": -152.5369
              }
            },
            {
              "type": "LEFT_EYE_TOP_BOUNDARY",
              "position": {
                "x": 1257.2474,
                "y": 2039.0826,
                "z": -17.843637
              }
            },
            {
              "type": "LEFT_EYE_RIGHT_CORNER",
              "position": {
                "x": 1323.9672,
                "y": 2068.4224,
                "z": -29.055658
              }
            },
            {
              "type": "LEFT_EYE_BOTTOM_BOUNDARY",
              "position": {
                "x": 1265.1266,
                "y": 2083.31,
                "z": -0.75843513
              }
            },
            {
              "type": "LEFT_EYE_LEFT_CORNER",
              "position": {
                "x": 1224.4413,
                "y": 2059.7639,
                "z": 59.171185
              }
            },
            {
              "type": "LEFT_EYE_PUPIL",
              "position": {
                "x": 1258.1006,
                "y": 2061.5125,
                "z": -2.69422
              }
            },
            {
              "type": "RIGHT_EYE_TOP_BOUNDARY",
              "position": {
                "x": 1541.8608,
                "y": 2058.0999,
                "z": -176.18483
              }
            },
            {
              "type": "RIGHT_EYE_RIGHT_CORNER",
              "position": {
                "x": 1622.0343,
                "y": 2086.3186,
                "z": -161.96181
              }
            },
            {
              "type": "RIGHT_EYE_BOTTOM_BOUNDARY",
              "position": {
                "x": 1547.3013,
                "y": 2101.1057,
                "z": -158.68855
              }
            },
            {
              "type": "RIGHT_EYE_LEFT_CORNER",
              "position": {
                "x": 1493.3573,
                "y": 2079.58,
                "z": -123.70734
              }
            },
            {
              "type": "RIGHT_EYE_PUPIL",
              "position": {
                "x": 1550.0431,
                "y": 2081.1252,
                "z": -165.61771
              }
            },
            {
              "type": "LEFT_EYEBROW_UPPER_MIDPOINT",
              "position": {
                "x": 1242.84,
                "y": 1943.1686,
                "z": -26.588711
              }
            },
            {
              "type": "RIGHT_EYEBROW_UPPER_MIDPOINT",
              "position": {
                "x": 1551.6553,
                "y": 1963.9197,
                "z": -198.45435
              }
            },
            {
              "type": "LEFT_EAR_TRAGION",
              "position": {
                "x": 1271.2211,
                "y": 2217.4294,
                "z": 455.93988
              }
            },
            {
              "type": "RIGHT_EAR_TRAGION",
              "position": {
                "x": 1909.1074,
                "y": 2261.8872,
                "z": 94.275948
              }
            },
            {
              "type": "FOREHEAD_GLABELLA",
              "position": {
                "x": 1376.913,
                "y": 1987.9856,
                "z": -144.98334
              }
            },
            {
              "type": "CHIN_GNATHION",
              "position": {
                "x": 1364.2478,
                "y": 2621.2776,
                "z": -86.848106
              }
            },
            {
              "type": "CHIN_LEFT_GONION",
              "position": {
                "x": 1225.1389,
                "y": 2426.7222,
                "z": 326.74741
              }
            },
            {
              "type": "CHIN_RIGHT_GONION",
              "position": {
                "x": 1814.6699,
                "y": 2459.0437,
                "z": 0.11285134
              }
            }
          ],
          "rollAngle": 3.4324508,
          "panAngle": -29.033209,
          "tiltAngle": -0.6941908,
          "detectionConfidence": 0.97096157,
          "landmarkingConfidence": 0.41415858,
          "joyLikelihood": "VERY_UNLIKELY",
          "sorrowLikelihood": "VERY_UNLIKELY",
          "angerLikelihood": "VERY_UNLIKELY",
          "surpriseLikelihood": "VERY_UNLIKELY",
          "underExposedLikelihood": "VERY_UNLIKELY",
          "blurredLikelihood": "VERY_UNLIKELY",
          "headwearLikelihood": "VERY_UNLIKELY"
        }
      ]
    }
  ]
}
```

以下検証結果

### 無表情の人その1

![porker-face1](https://raw.githubusercontent.com/ryurock/google-cloud-vision-api-sample/master/images/porker-face.jpg?token=ABi0jFvLMZXST405pxIkl0LP3jUC4gv-ks5XbPoZwA%3D%3D)

どの項目もVERY_UNLIKELYになる

```
          "joyLikelihood": "VERY_UNLIKELY",
          "sorrowLikelihood": "VERY_UNLIKELY",
          "angerLikelihood": "VERY_UNLIKELY",
          "surpriseLikelihood": "VERY_UNLIKELY",
          "underExposedLikelihood": "VERY_UNLIKELY",
          "blurredLikelihood": "VERY_UNLIKELY",
          "headwearLikelihood": "VERY_UNLIKELY"
```

### 無表情の人その2

もう少しだけ笑顔？を含んだ感じな人

![porker-face2](https://raw.githubusercontent.com/ryurock/google-cloud-vision-api-sample/master/images/porker-face2.jpg?token=ABi0jFD8Vnky7teL0JRc8gPrCFErWra2ks5XbPo0wA%3D%3D)

どの項目もVERY_UNLIKELYになる

```
          "joyLikelihood": "VERY_UNLIKELY",
          "sorrowLikelihood": "VERY_UNLIKELY",
          "angerLikelihood": "VERY_UNLIKELY",
          "surpriseLikelihood": "VERY_UNLIKELY",
          "underExposedLikelihood": "VERY_UNLIKELY",
          "blurredLikelihood": "VERY_UNLIKELY",
          "headwearLikelihood": "VERY_UNLIKELY"
```



### 嬉しそうな人その1

![near-person2](https://raw.githubusercontent.com/ryurock/google-cloud-vision-api-sample/master/images/funny1.jpg?token=ABi0jN-yxtzIAHnZ41OhU9d6EOnU6_quks5XbPqkwA%3D%3D)


joy Likelihood (喜び可能性)がVERY_LIKELY


```
          "joyLikelihood": "VERY_LIKELY",
          "sorrowLikelihood": "VERY_UNLIKELY",
          "angerLikelihood": "VERY_UNLIKELY",
          "surpriseLikelihood": "VERY_UNLIKELY",
          "underExposedLikelihood": "VERY_UNLIKELY",
          "blurredLikelihood": "VERY_UNLIKELY",
          "headwearLikelihood": "VERY_UNLIKELY
```

### 嬉しそうな人その2

![near-person3](https://raw.githubusercontent.com/ryurock/google-cloud-vision-api-sample/master/images/funny2.jpg?token=ABi0jE2jg8r_dpdoiZz82wbRDJYTBouVks5XbPrLwA%3D%3D)

女性には優しい

joy Likelihood (喜び可能性)がVERY_LIKELY

```
          "joyLikelihood": "VERY_LIKELY",
          "sorrowLikelihood": "VERY_UNLIKELY",
          "angerLikelihood": "VERY_UNLIKELY",
          "surpriseLikelihood": "VERY_UNLIKELY",
          "underExposedLikelihood": "VERY_UNLIKELY",
          "blurredLikelihood": "VERY_UNLIKELY",
          "headwearLikelihood": "VERY_UNLIKELY
```



### 怒ってる人その1


怒ってるのか？どうなんだがわからない顔で検証

```
"angerLikelihood": "VERY_LIKELY"
```

を期待したけども ``` VERY_UNLIKELY ```

![angry-person](https://raw.githubusercontent.com/ryurock/google-cloud-vision-api-sample/master/images/angry1.jpg?token=ABi0jABCLPL794OLEq8KEvgEM6k35hrYks5XbPrwwA%3D%3D)


```
          "joyLikelihood": "VERY_UNLIKELY",
          "sorrowLikelihood": "VERY_UNLIKELY",
          "angerLikelihood": "VERY_UNLIKELY",
          "surpriseLikelihood": "VERY_UNLIKELY",
          "underExposedLikelihood": "VERY_UNLIKELY",
          "blurredLikelihood": "VERY_UNLIKELY",
          "headwearLikelihood": "VERY_UNLIKELY"
```

### 怒ってる人その2

![ner-person](https://raw.githubusercontent.com/ryurock/google-cloud-vision-api-sample/master/images/angry2.jpg?token=ABi0jJcDzPD9AbM7eJy0Z-ba3zG2US3Fks5XbPt8wA%3D%3D)

女性が少しだけ怒ってる感じの顔。この位じゃ ``` angerLikelihood ``` が
``` VERY_LIKELY ``` にならない。

少しだけ、楽しくないって判定になった

```
"joyLikelihood": "UNLIKELY" 
```




```
         "joyLikelihood": "UNLIKELY",
          "sorrowLikelihood": "VERY_UNLIKELY",
          "angerLikelihood": "VERY_UNLIKELY",
          "surpriseLikelihood": "VERY_UNLIKELY",
          "underExposedLikelihood": "VERY_UNLIKELY",
          "blurredLikelihood": "VERY_UNLIKELY",
          "headwearLikelihood": "VERY_UNLIKELY"
```


## 物体認識 LABEL_DETECTION

次は絵を認識してみる。
犬の画像を書いて、犬と認識してくれるかを検証してみる。

### 天才的画伯その１

![dog](https://raw.githubusercontent.com/ryurock/google-cloud-vision-api-sample/master/images/dog5.jpg?token=ABi0jGaxFLGXU_t8yZ20_ooGEGS5_Ec6ks5XbPyzwA%3D%3D)

cartoon 漫画
sculpture 彫刻
nose 鼻
drawing お絵かき
dango だんご

だんごがよくわからない

```
{
  "responses": [
    {
      "labelAnnotations": [
        {
          "mid": "/m/0215n",
          "description": "cartoon",
          "score": 0.90735883
        },
        {
          "mid": "/m/06msq",
          "description": "sculpture",
          "score": 0.85323882
        },
        {
          "mid": "/m/0k0pj",
          "description": "nose",
          "score": 0.83781445
        },
        {
          "mid": "/m/02csf",
          "description": "drawing",
          "score": 0.76977384
        },
        {
          "mid": "/m/012xv6",
          "description": "dango",
          "score": 0.75
        }
      ]
    }
  ]
}
```

### 天才的画伯その2

![dog](https://raw.githubusercontent.com/ryurock/google-cloud-vision-api-sample/master/images/dog1.jpg?token=ABi0jEgXZiWgaa2IhPO_H1p6dFTcQZxjks5XbP3WwA%3D%3D)

cartoon 漫画
drawing お絵かき
sketch スケッチ
aisle 通路

通路？？

```
{
  "responses": [
    {
      "labelAnnotations": [
        {
          "mid": "/m/0215n",
          "description": "cartoon",
          "score": 0.90353215
        },
        {
          "mid": "/m/07glzq",
          "description": "sketch",
          "score": 0.83572245
        },
        {
          "mid": "/m/02csf",
          "description": "drawing",
          "score": 0.74130529
        },
        {
          "mid": "/m/01rd5z",
          "description": "aisle",
          "score": 0.68881238
        },
        {
          "mid": "/m/081rb",
          "description": "writing",
          "score": 0.62101489
        }
      ]
    }
  ]
}
```

### エロ判定

男の乳首はエロ判定になるのか？試してみた

![filter](https://raw.githubusercontent.com/ryurock/google-cloud-vision-api-sample/master/images/filter1.jpg?token=ABi0jPvGCOsE7U0SHbUa2_vZIPpwAJ5kks5XbPv1wA%3D%3D)

"adult": "VERY_LIKELY",

エロですw

```
{
  "responses": [
    {
      "safeSearchAnnotation": {
        "adult": "VERY_LIKELY",
        "spoof": "VERY_UNLIKELY",
        "medical": "VERY_LIKELY",
        "violence": "UNLIKELY"
      }
    }
  ]
}
```


## まとめ

顔のポジションまでは試していないけども、
顔の付加情報はまだまだだなーという印象でした。
