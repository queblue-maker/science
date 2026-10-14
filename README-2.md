# 세특 탐구 설계실

과학 과목·단원과 희망 진로를 골라 탐구 주제, 세특 심화 키워드, 세특 문장 초안을 찾아보는 웹페이지입니다.
서버나 빌드 과정 없이 `index.html` 한 파일로 동작합니다.

## 폴더 구성

| 파일 | 역할 |
|---|---|
| `index.html` | 웹페이지 본체 (데이터·디자인·기능 모두 포함) |
| `vercel.json` | Vercel 설정 (깔끔한 주소, 기본 보안 헤더, 수정 즉시 반영) |
| `.gitignore` | GitHub에 올리지 않을 파일 목록 |
| `README.md` | 이 안내서 |

---

## 1단계. GitHub에 올리기 (웹 브라우저만으로 가능)

1. https://github.com 에 로그인합니다. 계정이 없으면 Sign up으로 만듭니다.
2. 오른쪽 위 **+** → **New repository** 를 누릅니다.
3. 설정
   - Repository name: `seteuk-lab` (원하는 영문 이름)
   - **Public** 선택 (Vercel 무료 배포는 Private도 가능하지만 Public이 가장 간단합니다)
   - 나머지는 체크하지 않고 **Create repository**
4. 만들어진 화면에서 **uploading an existing file** 링크를 누릅니다.
5. 압축을 푼 폴더 안의 파일 4개(`index.html`, `vercel.json`, `.gitignore`, `README.md`)를 끌어다 놓습니다.
   - `.gitignore`가 보이지 않으면 숨김 파일 표시를 켜거나 빼고 올려도 됩니다.
   - 폴더째가 아니라 **파일들**을 올려야 합니다. `index.html`이 저장소 맨 위에 있어야 해요.
6. 아래 **Commit changes** 를 누릅니다.

## 2단계. Vercel로 배포하기

1. https://vercel.com 에서 **Continue with GitHub** 로 가입·로그인합니다. (Hobby 무료 플랜 선택)
2. **Add New…** → **Project** 를 누릅니다.
3. GitHub 저장소 목록에서 `seteuk-lab` 옆 **Import** 를 누릅니다.
   - 목록에 없으면 **Adjust GitHub App Permissions** 에서 해당 저장소 접근을 허용합니다.
4. 설정 화면
   - Framework Preset: **Other**
   - Root Directory: `./` 그대로
   - Build Command, Output Directory: 비워 둠
5. **Deploy** 를 누르면 1분 안에 `https://seteuk-lab.vercel.app` 같은 주소가 생깁니다.
6. 이 주소를 학생들에게 공유하면 됩니다. (QR 코드로 만들어 게시하면 편리합니다)

### 주소 이름 바꾸기 (선택)
Vercel 프로젝트 → **Settings** → **Domains** 에서 `○○고-과학탐구.vercel.app` 처럼 사용 가능한 이름으로 바꿀 수 있습니다. (영문·숫자·하이픈만 가능)

---

## 수정하고 다시 배포하기

GitHub에서 `index.html`을 고치면 Vercel이 **자동으로 다시 배포**합니다.

1. GitHub 저장소에서 `index.html` 클릭 → 연필 아이콘(Edit)
2. 내용 수정 → **Commit changes**
3. 1분 정도 뒤 학생용 주소에 반영됩니다.

### 주제 추가하는 법
`index.html` 안에서 `const S = [` 를 찾으면 과목별 단원과 주제가 있습니다. 주제 한 줄의 형식은 다음과 같습니다.

```js
['주제 제목', '진로코드 진로코드', '방법', 난이도, '키워드1,키워드2,키워드3', '후속 탐구'],
```

- 진로코드: `med`(의약보건) `bio`(바이오) `mech`(기계) `elec`(전자·반도체) `cs`(컴퓨터·AI) `chem`(화공·신소재) `energy`(에너지·환경) `civil`(건축·토목) `space`(항공우주) `earth`(지구·해양·대기) `agri`(농생명·식품) `edu`(교육) `social`(경영·법·정책) `design`(디자인) `sport`(체육)
- 방법: `실험` `데이터` `문헌` `모델링` `설계` `조사` 중 하나
- 난이도: `1`(기초) 또는 `2`(심화)
- 쉼표와 따옴표를 빠뜨리면 페이지가 비어 보입니다. 수정 후 화면이 하얗게 나오면 마지막으로 고친 줄의 쉼표·따옴표를 확인하세요.

---

## 학생 배포 시 참고

- **로그인·개인정보 수집이 없습니다.** '담은 주제'는 각 학생 기기의 브라우저에만 저장되고 서버로 전송되지 않습니다.
- 페이지에 있는 **세특 문장 초안**은 교사용 예시입니다. 학생에게는 "탐구 계획을 세울 때 참고하는 예시이며, 실제 기록은 수업 활동을 바탕으로 선생님이 작성한다"고 안내해 주세요.
- 인터넷 연결이 없으면 글꼴만 기본 글꼴로 바뀌고 기능은 그대로 동작합니다.
