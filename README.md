# 이 포크에 대하여

이 GitHub 리포지토리에는 원본 PLAbDab 데이터베이스에 등록된 항체의 전체 서열 정보가 CSV 파일로 포함되어 있습니다. 원본 데이터베이스에는 VH와 VL 서열만 포함되어 있었지만, 저는 Fc 또는 힌지 영역과 관련된 서열에 관심이 있어 웹 스크레이핑을 통해 해당 서열들을 얻었습니다. 하지만 일부 항목은 찾을 수 없어 비워두었습니다. 이 자료가 비슷한 관심사를 가진 다른 분들께 유용하기를 바랍니다.

---

<div align="center">    
 
# 특허 및 문헌 항체 데이터베이스 (PLAbDab): 기능적으로 다양하고 문헌에 기록된 항체 서열 및 구조의 진화하는 참조 세트

---
    
저자
Brennan Abanades $^{1,\dagger}$, Tobias H. Olsen $^{1,\dagger}$, Matthew I. J. Raybould $^{1}$ Broncio Aguilar-Sanjuan $^{1}$, Wing Ki Wong $^{2}$, Guy Georges $^{2}$, Alexander Bujotzek $^{2}$, and Charlotte M. Deane $^{1,*}$

$^{1}$ 옥스포드 단백질 정보학 그룹, 통계학과, 옥스포드 대학교, 옥스포드, 영국
$^{2}$ 거대 분자 연구, 로슈 제약 연구 및 초기 개발, 로슈 혁신 센터 뮌헨, 펜츠베르크, 독일
$^{\dagger}$ 이 저자들은 이 연구에 동등하게 기여했으며 공동 제1 저자입니다.
$^{*}$ 교신 저자
</div>



## 초록
항체는 적응 면역 체계의 핵심 단백질이며, 이들의 연구 및 치료제, 진단제, 또는 시약으로의 전환에 관한 방대한 학술 문헌과 특허가 존재합니다. 이러한 문서들은 종종 그들이 설명하는 항체 세트의 광범위한 기능적 특성을 포함하고 있습니다. 그러나 예를 들어 관심 있는 쿼리 항체의 특성에 대한 통찰력을 제공하기 위해 이러한 이기종 보고서를 활용하는 것은 현재로서는 어려운 일입니다. 왜냐하면 이 광범위한 자료를 서열이나 구조로 검색할 수 있는 중앙 저장소가 없기 때문입니다.

여기에서 우리는 150,000개 이상의 쌍을 이루는 항체 서열과 3D 구조 모델을 포함하는 자체 업데이트 저장소인 PLAbDab(특허 및 문헌 항체 데이터베이스)을 제시하며, 이 중 65,000개 이상은 고유합니다. 데이터베이스의 각 항목에는 문헌 출처의 제목과 저자도 포함됩니다. 여기에서는 PLAbDab의 항체를 추출, 필터링, 쌍으로 연결하고 모델링하는 데 사용된 방법을 설명하고, 서열, 구조 또는 키워드로 PLAbDab을 검색하는 방법을 보여줍니다.

PLAbDab의 용도는 유사한 항목의 잠재적인 항원 정보로 쿼리 항체를 주석 처리하고, 기존 항체의 구조 모델을 분석하여 특성을 개선할 수 있는 수정을 식별하고, 특정 항원에 결합하는 것으로 알려진 항체 서열/구조의 맞춤형 데이터 세트를 편집하는 것을 포함합니다. PLAbDab은 Github(https://github.com/brennanaba/PLAbDab)를 통해 무료로 제공되며 검색 가능한 웹 서버(https://opig.stats.ox.ac.uk/webapps/plabdab/)로도 제공됩니다.

## 사용법

PLAbDab 파이썬 패키지를 사용하려면 먼저 데이터베이스 사본을 다운로드해야 합니다. 이것은 <a href="https://opig.stats.ox.ac.uk/webapps/plabdab/static/downloads/plabdab_data.tar.gz">여기</a>에서 얻을 수 있습니다. 파일은 압축된 형식으로 제공됩니다. 압축을 푼 후 다음과 같이 PLAbDab 버전을 해당 디렉토리로 지정할 수 있습니다.

```python
from PLAbDab import PLAbDab

plabdab = PLAbDab(data_directory, n_jobs = 10)
```

이 'plabdab' 객체는 검색을 수행하는 데 사용할 수 있습니다. PLAbDab은 각 검색에 대해 pandas 데이터프레임을 출력합니다. API 사용 방법에 대한 자세한 내용은 노트북을 확인하십시오.

## 설치

PLAbDab은 구조 검색을 수행하기 위해 <a href="https://github.com/brennanaba/ImmuneBuilder">ImmuneBuilder</a>가 필요합니다. 설치하려면 <a href="https://github.com/brennanaba/ImmuneBuilder">ImmuneBuilder 리포지토리</a>의 지침을 따르십시오.

ImmuneBuilder와 모든 종속성이 설치되면 PLAbDab 디렉토리에서 다음 명령을 실행하여 PLAbDab을 설치할 수 있습니다.

```bash
$ pip install .
```

## 이 저작물 인용하기

이 패키지의 코드와 데이터는 <a href="https://www.biorxiv.org/content/10.1101/2023.07.15.549143v1">다음 논문</a>을 기반으로 합니다. 사용하는 경우 다음을 인용하십시오.

```tex
@article{abanades2023patent,
  title={The Patent and Literature Antibody Database (PLAbDab): an evolving reference set of functionally diverse, literature-annotated antibody sequences and structures},
  author={Abanades, Brennan and Olsen, Tobias Hegelund and Raybould, Matthew IJ and Aguilar-Sanjuan, Broncio and Wong, Wing Ki and Georges, Guy and Bujotzek, Alexander and Deane, Charlotte M},
  journal={bioRxiv},
  pages={2023--07},
  year={2023},
  publisher={Cold Spring Harbor Laboratory}
}
```
