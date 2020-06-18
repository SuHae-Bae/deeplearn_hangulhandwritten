<h1>폰트를 이용한 한글 손글씨 인식</h1>


전체적인 코드는 [이곳](https://github.com/MijeongJeon/KoreanClassification_Keras_Coreml) 과 [이곳]((https://github.com/IBM/tensorflow-hangul-recognition))을 참고하였습니다



1. 데이터 생성
2. 데이터 정제
3. 모델 생성 및 분석



<h3>데이터 생성</h3>
우선 font폴더에 폰트가 받아져있는지 확인해보아야 합니다. 원하는 폰트가 있다면 그걸 이용해도 됩니다. 단, ttf형식의 파일이어야 합니다.


해당 데이터 생성기는 512개의 음절을 만들어냅니다. 컴퓨터의 성능이 좋다면 음절을 더 추가하여 만들 수 있습니다. 음절을 추가할수록 생성되는 글자 데이터 양이 증가합니다.

준비가 완료되면 로컬에서 해당 명령어를 실행시켜줍니다.

```py
python ./tools/hangul-image-generator.py
```

이후 image-data 폴더에 들어가면 생성된 이미지가 들어있는 폴더와 라벨 정보 및 이미지 위치가 들어있는 csv파일이 생성됩니다. 이 csv파일에서 ctr+f로 `\`를 모두 `/`로 바꾸어 주세요.



<h3>
    데이터 정제
</h3>

데이터를 만들어 주었다면 hangul_data.ipynb의 내용을 실행시켜주십시오.



<h3> 모델 생성 및 분석
</h3>

데이터 정제가 끝났다면 hangul_model.ipynb의 내용을 실행시켜 주십시오. 해당 코드를 colab에서 실행시키는 것을 추천드립니다(GPU 사용)

제가 만든 모델은 trained_model2.zip에 들어있으며(용량이 커서 메일로 보낼 예정), 사용한 데이터는 image-data와 used_data입니다. image-data는 raw data이며 used_data가 데이터 정제를 거친 데이터입니다.