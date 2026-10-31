# 피부 노화와 알츠하이머병: 2표본 멘델리안 무작위분석 (Skin Ageing and Alzheimer's Disease MR)

> "치매 전에 피부가 나빠진다"는 관찰이 인과관계인지 확인하려고, 유전적으로 예측된 얼굴 노화와 알츠하이머병(AD) 사이의 관계를 양방향 2표본 멘델리안 무작위분석(MR)으로 검증했습니다.

---

## 1. 핵심 결과

| 질문 | 답 |
|---|---|
| 유전적으로 얼굴이 더 늙어 보이는 경향은 AD 위험을 높이는가 | **근거 없음.** IVW OR 0.98 (0.56–1.71), p = 0.95 (Kunkle 2019, 59개 변이) |
| 더 큰 AD GWAS에서도 같은가 | 같음. IVW OR 0.89 (0.62–1.28), p = 0.54 (Bellenguez 2022, 74개 변이) |
| AD 소인이 얼굴 노화를 앞당기는가 (역방향) | **근거 없음.** IVW β −0.002 (−0.005–0.002), p = 0.40 |
| APOE를 빼도 같은가 | 같음. IVW β −0.002 (−0.013–0.009), p = 0.68 |
| 방향성 다면발현이 있는가 | Egger 절편 p = 0.45–0.98로 근거 없음 |

**한 줄 요약:** 정방향과 역방향 모두 네 가지 MR 방법에서 유의한 연관이 없었습니다. 관찰연구에서 보고된 얼굴 노화와 치매의 연관(Xu 2024, HR 1.61)은 유전적으로 예측된 피부 노화의 인과 효과라기보다, **공통 위험요인(흡연, 자외선, 사회경제적 지위)이나 전반적 건강 상태에 의한 교란**일 가능성이 더 큽니다.

## 2. 배경과 연구 질문

Xu 등(2024, *Alzheimer's Research & Therapy*)은 UK Biobank 60세 이상 195,329명에서 스스로 "나이보다 늙어 보인다"고 답한 군의 치매 위험이 1.61배(95% CI 1.33–1.96) 높다고 보고했습니다. 하지만 관찰 연관은 교란과 역인과(인지저하 → 자기관리 감소 → 피부 악화)에 취약합니다.

1. 유전적으로 얼굴이 더 늙어 보이는 경향(피부 노화)은 AD 위험을 높이는가?
2. 반대로 AD 소인이 피부 노화를 앞당기는가?

## 3. 데이터 (OpenGWAS, 모두 유럽계)

| 역할 | 형질 | OpenGWAS ID | 출처 | 표본 |
|---|---|---|---|---|
| 노출 | 얼굴 노화 (Facial ageing) | `ukb-b-2148` | UK Biobank, MRC-IEU (2018) | 423,999명 |
| 결과 (주 분석) | 알츠하이머병 | `ieu-b-2` | Kunkle 2019, IGAP | 환자 21,982 / 대조 41,944 |
| 결과 (민감도) | 알츠하이머병 | `ebi-a-GCST90027158` | Bellenguez 2022 | 환자 39,106 / 대조 46,828 |

- **얼굴 노화 문항** (UK Biobank field 1757): "다른 사람들이 보기에 당신은 나이보다 젊어 보입니까, 늙어 보입니까?" 1 젊어 보임 / 2 비슷함 / 3 늙어 보임. GWAS는 이 응답을 연속형으로 분석했습니다.
- **표본 중복**: 노출 GWAS가 UK Biobank이므로, 주 분석은 UK Biobank가 없는 Kunkle 2019를 썼습니다. Bellenguez 2022는 UK Biobank 가족력 기반 사례를 포함해 표본이 겹치므로 민감도 분석으로만 비교했습니다.

## 4. 방법

1. **도구변수 선택**: p < 5×10⁻⁸, LD clumping (r² < 0.001, 10 Mb, 1000 Genomes EUR), F 통계량 ≥ 10
2. **결과 변이 추출**: 결과 GWAS에 없는 변이는 LD 대리 변이(r² ≥ 0.8)로 대체
3. **대립유전자 정렬**: 효과 대립유전자 일치, 가닥 뒤집힘 보정, MAF > 0.42인 회문 SNP 제거
4. **추정**: IVW(다중 랜덤효과), MR-Egger, 가중 중앙값, 가중 최빈값
5. **민감도 분석**: Cochran's Q, MR-Egger 절편, leave-one-out, Steiger 방향성
6. **역방향 MR**: Kunkle 2019 AD 도구변수 → 얼굴 노화. 효과가 큰 APOE 영역(19번 염색체 44.4–46.5 Mb, GRCh37)을 뺀 분석을 함께 수행

**효과 단위**: 정방향은 "유전적으로 예측된 얼굴 노화 점수 1단위 증가당 AD 오즈비", 역방향은 "AD 유전적 소인 로그 오즈 1 증가당 얼굴 노화 점수 변화(β)"입니다.

## 5. 결과

### 5.1 도구변수

| 분석 | 도구변수 | 결과 GWAS 확보 | 정렬 후 분석 |
|---|---|---|---|
| 얼굴 노화 → AD (Kunkle) | 79개 (평균 F 73.5, 최소 F 29.8) | 77개 | 59개 |
| 얼굴 노화 → AD (Bellenguez) | 79개 | 77개 | 74개 |
| AD → 얼굴 노화 | 16개 | | 16개 (APOE 제외 12개) |

모든 도구변수의 F 통계량이 10을 넘어 약한 도구변수 편향 가능성은 낮습니다.

### 5.2 정방향: 얼굴 노화 → 알츠하이머병

| 결과 GWAS | 방법 | SNP | OR (95% CI) | p |
|---|---|---|---|---|
| Kunkle 2019 (주) | IVW | 59 | **0.98 (0.56–1.71)** | 0.95 |
| | MR-Egger | 59 | 0.86 (0.28–2.64) | 0.80 |
| | 가중 중앙값 | 59 | 0.84 (0.41–1.74) | 0.64 |
| | 가중 최빈값 | 59 | 0.88 (0.43–1.80) | 0.73 |
| Bellenguez 2022 (민감도) | IVW | 74 | 0.89 (0.62–1.28) | 0.54 |
| | MR-Egger | 74 | 0.70 (0.34–1.44) | 0.34 |
| | 가중 중앙값 | 74 | 0.83 (0.56–1.23) | 0.35 |
| | 가중 최빈값 | 74 | 0.87 (0.60–1.28) | 0.49 |

- 두 AD GWAS와 네 가지 방법 모두 신뢰구간이 1을 포함했습니다.
- 점추정치는 모두 1보다 약간 작아 위험 증가 방향의 근거는 없었습니다.
- 주 분석 leave-one-out IVW 추정치(로그 OR)는 −0.083 ~ 0.064 범위로, 특정 변이 하나가 결과를 좌우하지 않았습니다.

### 5.3 역방향: 알츠하이머병 소인 → 얼굴 노화

| 분석 | 방법 | SNP | β (95% CI) | p |
|---|---|---|---|---|
| 전체 | IVW | 16 | −0.002 (−0.005–0.002) | 0.40 |
| | MR-Egger | 16 | −0.002 (−0.007–0.003) | 0.54 |
| | 가중 중앙값 | 16 | −0.002 (−0.004–0.000) | 0.11 |
| | 가중 최빈값 | 16 | −0.002 (−0.004–0.001) | 0.17 |
| APOE 제외 | IVW | 12 | −0.002 (−0.013–0.009) | 0.68 |
| | MR-Egger | 12 | 0.012 (−0.038–0.063) | 0.64 |
| | 가중 중앙값 | 12 | 0.005 (−0.005–0.014) | 0.35 |
| | 가중 최빈값 | 12 | 0.010 (−0.005–0.024) | 0.18 |

AD 소인이 얼굴 노화를 앞당긴다는 근거도 없었습니다. APOE 포함 여부와 관계없이 결과가 같았습니다.

### 5.4 민감도 분석

| 분석 | Cochran Q p | Egger 절편 p | Steiger 방향 |
|---|---|---|---|
| 얼굴 노화 → AD (Kunkle) | 0.001 | 0.79 | 올바름 |
| 얼굴 노화 → AD (Bellenguez) | < 0.001 | 0.45 | 올바름 |
| AD → 얼굴 노화 | < 0.001 | 0.98 | 올바름 |
| AD → 얼굴 노화 (APOE 제외) | < 0.001 | 0.57 | 올바름 |

- 모든 분석에서 이질성이 유의해, 고정효과가 아닌 다중 랜덤효과 IVW를 주 결과로 썼습니다.
- Egger 절편이 모두 유의하지 않아 방향성 다면발현의 근거는 없었습니다.
- Steiger 검정에서 모든 분석의 방향이 가정과 일치했습니다.

## 6. 해석과 한계

**해석**
- 유전적으로 예측된 피부 노화와 AD 사이에 **양방향 모두 인과 관계의 근거가 없었습니다.**
- 관찰연구의 연관은 흡연·자외선·사회경제적 지위 같은 공통 위험요인, 전반적 건강 상태, 또는 이미 시작된 인지저하가 자기 평가에 영향을 준 결과일 가능성이 있습니다.
- 이 결과는 "피부 노화가 치매를 일으키지 않는다"를 증명한 것이 아니라, **유전적으로 예측된 얼굴 노화 경향에 의한 큰 인과 효과는 없다**는 뜻입니다.

**한계**
- **신뢰구간이 넓습니다.** 노출이 3단계 설문 점수라 유전 변이가 설명하는 분산이 작아(Steiger r² ≈ 0.011), 작은 효과는 검출하지 못했을 수 있습니다.
- **자기 평가 노출**: 얼굴 노화 GWAS는 흡연·자외선·BMI·사회경제적 지위의 유전적 소인을 함께 담을 수 있습니다(수평적 다면발현).
- **이질성**: 모든 분석에서 Cochran's Q가 유의했습니다.
- **유럽계 GWAS**라 한국인에게 그대로 일반화하기 어렵습니다.
- **역방향 도구변수가 적습니다.** APOE 제외 후 12개입니다.

**다음 단계**
- 다변량 MR: 얼굴 노화 + 흡연 + BMI + 교육 수준을 함께 넣어 직접 효과 추정
- MR-PRESSO로 이상치 변이 제거 후 재분석
- 다른 피부 노출(아토피 피부염, 건선, 피부색·태닝 반응)로 확장
- 결과를 인지기능, 혈관성 치매, FinnGen 치매 GWAS로 넓혀 재현

## 7. 실행 방법

1. [OpenGWAS](https://api.opengwas.io/profile/)에서 API 토큰을 발급받습니다.
2. 토큰을 **코드에 직접 쓰지 말고** 환경변수로 설정합니다.
   ```bash
   export OPENGWAS_JWT="발급받은_토큰"
   ```
   Colab에서는 왼쪽 열쇠 아이콘(Secrets)에 `OPENGWAS_JWT`로 저장한 뒤 아래처럼 불러옵니다.
   ```python
   from google.colab import userdata
   import os
   os.environ["OPENGWAS_JWT"] = userdata.get("OPENGWAS_JWT")
   ```
3. 노트북의 `SYNTHETIC = False`를 확인하고 위에서부터 실행합니다.
   - `SYNTHETIC = True`로 두면 인터넷 없이 가상 자료로 파이프라인만 점검할 수 있습니다.
4. 결과는 `skin_ageing_AD_MR_results/` 폴더에 CSV와 그림으로 저장됩니다.

**필요 패키지**: `numpy`, `pandas`, `scipy`, `matplotlib`, `requests` (선택: `koreanize-matplotlib`)

### 파일 구성

| 파일 | 내용 |
|---|---|
| `skin_ageing_AD_MR.ipynb` | 분석 노트북 (Python) |
| `figures/mr_forest.png` | 정방향 MR 포레스트 플롯 |
| `figures/mr_scatter_main.png` | 얼굴 노화 → AD (Kunkle) 산점도 |

## 8. 참고문헌

- Xu X, et al. Facial aging, cognitive impairment, and dementia risk. *Alzheimers Res Ther* 2024;16:245.
- Kunkle BW, et al. Genetic meta-analysis of diagnosed Alzheimer's disease identifies new risk loci and implicates Aβ, tau, immunity and lipid processing. *Nat Genet* 2019;51:414–430.
- Bellenguez C, et al. New insights into the genetic etiology of Alzheimer's disease and related dementias. *Nat Genet* 2022;54:412–436.
- Hemani G, et al. The MR-Base platform supports systematic causal inference across the human phenome. *eLife* 2018;7:e34408.
- Bowden J, Davey Smith G, Burgess S. Mendelian randomization with invalid instruments: effect estimation and bias detection through Egger regression. *Int J Epidemiol* 2015;44:512–525.
- Bowden J, et al. Consistent estimation in Mendelian randomization with some invalid instruments using a weighted median estimator. *Genet Epidemiol* 2016;40:304–314.
- Hartwig FP, Davey Smith G, Bowden J. Robust inference in summary data Mendelian randomization via the zero modal pleiotropy assumption. *Int J Epidemiol* 2017;46:1985–1998.
- Hemani G, Tilling K, Davey Smith G. Orienting the causal relationship between imprecisely measured traits using GWAS summary data. *PLoS Genet* 2017;13:e1007081.
