# 🌊 Cloud-Native Data Analysis with Zarr

이 저장소는 차세대 다차원 배열 데이터 포맷인 **Zarr**의 기초부터 클라우드 데이터 로딩, 지도시각화 및 포맷 변환까지의 실습 과정을 담고 있습니다.

## 🚀 개요 (Introduction)
Zarr는 대규모 다차원 배열을 청크(Chunk) 단위로 압축하여 저장하는 클라우드 최적화 데이터 포맷입니다. OGC(Open Geospatial Consortium) 커뮤니티 표준으로 채택되었으며, 특히 기상, 해양, 지구 관측 분야에서 HDF5나 NetCDF를 대체하는 강력한 도구로 활용되고 있습니다.

## ✨ 핵심 장점 (Key Features)
- **Cloud-Native**: 전체 파일 다운로드 없이 HTTP Range Request를 통해 필요한 부분만 읽기 가능.
- **Parallelism**: 여러 프로세스에서 독립적인 청크에 동시 접근 및 쓰기 지원.
- **Flexibility**: 로컬 파일 시스템, S3, Google Cloud Storage 등 다양한 스토리지 지원.
- **Scalability**: 수 테라바이트(TB) 급의 데이터를 메모리 부담 없이 처리.

## 📂 프로젝트 구조 (Structure)
- `zarr_example.ipynb`: Zarr 생성, 로딩, 시각화 전체 과정을 담은 주피터 노트북.
- `example.zarr/`: 실습을 통해 생성된 로컬 Zarr 데이터 구조 예시.
  - `zarr.json`: 전체 데이터셋의 메타데이터 정보.
  - `data/zarr.json`: 배열의 형태 및 청크 설정 정보.
  - `data/c0/0...`: 실제 압축된 데이터 청크 파일들.
- `ds_kor2.nc`: Zarr 변환 실습을 위한 원본 NetCDF 샘플 데이터.

## 🛠 설치 및 환경 설정 (Installation)
노트북 실행을 위해 아래의 패키지들이 필요합니다. (Python 3.11+ 권장)

```bash
# 핵심 라이브러리 및 지도시각화 도구
pip install zarr numpy xarray geoviews cartopy hvplot jupyter_bokeh

# 원격 클라우드 데이터 접속을 위한 추가 의존성
pip install "zarr[remote]" "fsspec[http]" requests aiohttp
