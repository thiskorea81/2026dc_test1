# 공공자전거 대여 데이터

2011~2012년 미국 워싱턴 D.C. Capital Bikeshare의 일별 자료를 교육용으로 가공한 데이터입니다. 파일명은 `day_missing.csv`입니다.

## 속성 설명

| 속성 | 설명 |
| --- | --- |
| `instant` | 레코드 번호 |
| `dteday` | 날짜(YYYY-MM-DD) |
| `season` | 계절 코드: 1=겨울, 2=봄, 3=여름, 4=가을 |
| `yr` | 연도: 0=2011년, 1=2012년 |
| `mnth` | 월(1~12) |
| `holiday` | 공휴일 여부: 0=아님, 1=공휴일 |
| `weekday` | 요일: 0=일요일, 1=월요일, …, 6=토요일 |
| `workingday` | 근무일 여부: 1=주말도 공휴일도 아닌 날, 0=그 외 |
| `weathersit` | 날씨 코드: 1=맑음·구름 조금, 2=안개·흐림, 3=약한 비·눈 등, 4=강한 비·눈 등 |
| `temp` | 일평균 기온(°C) |
| `atemp` | 일평균 체감온도(°C) |
| `hum` | 일평균 상대습도(%) |
| `windspeed` | 일평균 풍속(원자료 척도, 물리 단위 미확인) |
| `casual` | 해당 날짜의 비회원 대여 건수 |
| `registered` | 해당 날짜의 등록회원 대여 건수 |
| `cnt` | 해당 날짜의 총대여 건수 |

기상 수치는 제공된 원본 설명의 배율로 이미 환산되어 있습니다. 날씨 코드는 원자료의 정의이며, 모든 코드가 이 파일에 포함되는 것은 아닙니다.

## 데이터 불러오기

Google Colab 또는 Jupyter Notebook에서 아래 방법 중 하나를 사용합니다.

### CSV 파일을 직접 올린 경우

`day_missing.csv`를 노트북의 현재 작업 폴더에 업로드한 뒤 실행합니다.

```python
import pandas as pd

df = pd.read_csv('day_missing.csv', parse_dates=['dteday'])
df.head()
```

### GitHub에서 직접 불러오는 경우

공개 저장소 [thiskorea81/2026dc_test1](https://github.com/thiskorea81/2026dc_test1)의 Raw 주소로 바로 불러옵니다.

```python
import pandas as pd

url = 'https://raw.githubusercontent.com/thiskorea81/2026dc_test1/main/day_missing.csv'
df = pd.read_csv(url, parse_dates=['dteday'])
df.head()
```

---

원자료: Hadi Fanaee-T, Bike Sharing Dataset. 교육용으로 일부 값을 비우고 기상 변수의 척도를 환산했습니다. 출처 논문: Fanaee-T & Gama (2013), *Event labeling combining ensemble detectors and background knowledge*, DOI: 10.1007/s13748-013-0040-3.
