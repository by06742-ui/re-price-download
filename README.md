# 부동산 실거래가 산출기 — 다운로드 배포용 저장소

이 저장소는 **EXE 다운로드 전용 웹페이지**를 만들기 위한 것입니다.
소스를 올리면 GitHub Actions가 클라우드에서 Windows EXE를 자동 빌드하고,
GitHub Pages가 다운로드 버튼만 있는 페이지를 띄웁니다.

## 처음 설정 순서

### 1) 새 저장소 만들기
- github.com → 우측 위 **+ → New repository**
- 이름: `re-price-download` (index.html의 REPO 값과 동일하게)
- **Public** 선택 → **Create repository**

### 2) 이 폴더의 파일 전부 업로드
- 저장소에서 **Add file → Upload files**
- 이 폴더의 모든 파일/폴더를 드래그 (`.github` 폴더 포함)
- 맨 아래 **Commit changes** 클릭

### 3) index.html에서 내 정보 확인
- index.html 안 `USER`, `REPO` 두 줄이 본인 사용자명/저장소명과 같은지 확인
- 다르면 연필(Edit) 아이콘으로 고친 뒤 Commit

### 4) EXE 자동 빌드 확인
- 저장소 상단 **Actions** 탭 → "Build and Release EXE" 실행 확인 (2~3분)
- 끝나면 **Releases** 에 `RE_price.exe` 가 올라옵니다

### 5) GitHub Pages 켜기 (다운로드 페이지 주소 생성)
- 저장소 **Settings → Pages**
- Source: **Deploy from a branch** → Branch: **main / (root)** → **Save**
- 1~2분 뒤 `https://<사용자명>.github.io/re-price-download/` 주소가 생성됩니다

## 완성된 주소
- **다운로드 페이지:** `https://<사용자명>.github.io/re-price-download/`
- 방문자는 이 주소에서 버튼만 누르면 최신 EXE를 받습니다.

## 데이터를 갱신하고 싶을 때
- 새 데이터 파일(prices.json, *.npz 등)을 저장소에 덮어쓰기 → Commit
- Actions가 자동으로 새 EXE를 빌드해 Releases를 갱신합니다 (페이지 수정 불필요)
