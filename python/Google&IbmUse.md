
#AI API : IBM, KAKAO, GOOGLE, SALTLUX

## IBM

# inside IBM

- 솔루션? 우리가 처한 문제 상황에 대해 이를 해결할 수 있는 방법

- 시스템, 소프트웨어, 서비스가 포함된 것

# IBEM Cloud

 - Tone Analyzer
 
 - 텍스트에서 감정 및 언어 톤을 감지
 
 
 
 # Python 가상 환경 
 
 ![가상환경이미지](https://miro.medium.com/max/960/1*1YLROYjbje6dPoqM8M3L9w.png)
 
 - 가상환경(Virtual nvironments)
 
 - 자신이 원하는 Python 환경을 구축하기 위해 필요한 모듈만 담아 놓은 바구니, 각 가상환경은 독립적으로 관리됨
 
 - 가상머신은 크게 2가지 virtualenv와 conda를 사용함. 
 
 
 - 가상환경 구축 후 IBM tone analyzer Text 테스트 
 
 - 예제 소스 
 
 ``` import json
from ibm_watson import ToneAnalyzerV3
from ibm_cloud_sdk_core.authenticators import IAMAuthenticator

authenticator = IAMAuthenticator('key')
tone_analyzer = ToneAnalyzerV3(
    version='2017-09-21',
    authenticator=authenticator
)

tone_analyzer.set_service_url('url')

text = 'Team, I know that times are tough! Product '\
    'sales have been disappointing for the past three '\
    'quarters. We have a competitive product, but we '\
    'need to do a better job of selling it!'

tone_analysis = tone_analyzer.tone(
    {'text': text},
    content_type='application/json'
).get_result()
print(json.dumps(tone_analysis, indent=2))```

- result 결과가 json 형태로 나옴 

``` "document_tone": {
    "tones": [
      {
        "score": 0.6165,
        "tone_id": "sadness",
        "tone_name": "Sadness"
      },
      {
        "score": 0.829888,
        "tone_id": "analytical",
        "tone_name": "Analytical"
      }
    ]
  },
  "sentences_tone": [
    {
      "sentence_id": 0,
      "text": "Team, I know that times are tough!",
      "tones": [
        {
          "score": 0.801827,
          "tone_id": "analytical",
          "tone_name": "Analytical"
        }
      ]
    },
    {
      "sentence_id": 1,
      "text": "Product sales have been disappointing for the past three quarters.",
      "tones": [
        {
          "score": 0.771241,
          "tone_id": "sadness",
          "tone_name": "Sadness"
        },
        {
          "score": 0.687768,
          "tone_id": "analytical",
          "tone_name": "Analytical"
        }
      ]
    },
    {
      "sentence_id": 2,
      "text": "We have a competitive product, but we need to do a better job of selling it!",
      "tones": [
        {
          "score": 0.506763,
          "tone_id": "analytical",
          "tone_name": "Analytical"
        }
      ]
    }
  ]
}```





