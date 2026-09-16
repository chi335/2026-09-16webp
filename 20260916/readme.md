# 📘 [HTML5] 시맨틱 태그 및 웹 폼(Web Form) 핵심 정리

> **HTML5 웹 프로그래밍 3장** 주요 개념 및 핵심 태그 완벽 정리

---

## 📌 목차
1. [HTML5 시맨틱 태그 (Semantic Tags)](#1-html5-시맨틱-태그-semantic-tags)
2. [HTML5에서 제거된 태그](#2-html5에서-제거된-태그)
3. [웹 폼 (Web Form) 및 전송 방식](#3-웹-폼-web-form-및-전송-방식)
4. [폼 입력 요소 (Form Controls)](#4-폼-입력-요소-form-controls)
5. [HTML에서의 색상 표현](#5-html에서의-색상-표현)

---

## 1. HTML5 시맨틱 태그 (Semantic Tags)

> **시맨틱 웹의 목적**: 검색엔진 최적화(SEO), 웹 접근성 향상, 소스 코드의 가독성 및 유지보수 편의성 확보.

### 1.1 주요 레이아웃 블록 태그

| 태그 | 설명 |
| :--- | :--- |
| `<header>` | 페이지나 섹션의 머리말 (제목, 로그인/회원가입 링크, 사이트 검색 등) |
| `<nav>` | 내비게이션 바 (주요 메뉴, 목차, 하이퍼링크 모음) |
| `<section>` | 문서 내 주제별 독립된 장/절(Chapter) 또는 영역 |
| `<article>` | 독립적으로 분리하여 배포/재사용 가능한 콘텐츠 (블로그 글, 뉴스 기사, 댓글 등) |
| `<aside>` | 본문과 연관성은 적으나 보조 정보로 제공되는 영역 (사이드바, 광고, 관련 링크) |
| `<footer>` | 페이지나 섹션의 꼬리말 (저작권 표시, 작성자 연락처, 이용약관 등) |
| `<figure>` / `<figcaption>` | 본문에 삽입하는 그림, 차트, 소스 코드 등의 미디어 블록과 그 설명(캡션) |
| `<details>` / `<summary>` | 클릭 시 상세 정보를 열고 접을 수 있는 동적 UI (Q&A 항목 등) |

### 1.2 인라인 시맨틱 태그

- `<mark>` : 중요 텍스트 하이라이트 (기본 노란색 배경 강조)
- `<time>` : 날짜나 시간 정보 지정 (예: `<time>09:00</time>`)
- `<meter>` : 범위가 정해진 값 중 현재 수치/비율 표시 (예: `<meter value="0.8" max="1.0">80%</meter>`)
- `<progress>` : 작업의 진행 상태/프로세스를 바 형태로 표시 (예: `<progress value="2" max="10"></progress>`)

---

## 2. HTML5에서 제거된 태그

HTML5에서는 **"문서의 구조(HTML)와 디자인(CSS)을 분리한다"**는 원칙에 따라 외형만 변경하던 태그들이 폐지되었습니다.

- **제거된 태그**: `<font>`, `<center>`, `<big>`, `<u>`, `<strike>`, `<tt>`, `<xmp>`, `<dir>`, `<frame>`, `<frameset>`, `<noframes>`
- ⚠️ **주의**: `<iframe>` 태그는 제거되지 않고 유지되었습니다.

---

## 3. 웹 폼 (Web Form) 및 전송 방식

사용자로부터 데이터를 입력받아 웹 서버로 전달하는 영역입니다.

### `<form>` 태그의 핵심 속성

1. **`name`**: 폼의 식별 이름 지정
2. **`action`**: 입력 데이터를 전달받아 처리할 웹 서버 프로그램 URL (JSP, PHP, ASP 등)
3. **`method`**: 서버로 데이터 전달 방식
   - **`GET`**: URL 끝에 데이터(`?id=abc&pw=123`)를 부착하여 전송. 보안성이 낮으나 검색 등에 사용.
   - **`POST`**: HTTP 요청 본문(Body)에 숨겨서 전송. 보안성이 높고 데이터 크기 제한이 없어 회원가입/로그인 시 사용.

---

## 4. 폼 입력 요소 (Form Controls)

### 4.1 텍스트 및 입력 보조 요소

- **`<input type="text">`**: 일반 단일 행 텍스트 입력
- **`<input type="password">`**: 비밀번호 입력 (입력 문자가 `*` 또는 `•`로 은폐)
- **`<textarea>`**: 여러 줄(다중 행) 텍스트 입력 (`rows`, `cols` 속성 사용)
- **`placeholder`**: 입력 폼에 미리 힌트 문구를 옅게 보여주는 속성 (예: `placeholder="id@host"`)
- **`<fieldset>` / `<legend>`**: 관련 입력 양식 요소들을 테두리 상자로 묶고 범례(제목) 표기

#### 💡 datalist (자동완성 추천 목록) 사용 예시
```html
<input type="text" list="countries">
<datalist id="countries">
  <option value="가나">
  <option value="스위스">
</datalist>
```

---

### 4.2 선택형 입력 요소

- **체크박스 (`<input type="checkbox">`)**: 다중 선택 가능
- **라디오 버튼 (`<input type="radio">`)**: 동일한 `name` 속성을 가진 항목 중 하나만 선택 가능
- **콤보 박스 (`<select>` + `<option>`)**: 드롭다운 목록 형태
  - `size`: 한 번에 보여줄 목록 개수
  - `multiple`: 다중 선택 허용
  - `selected` / `checked`: 기본 선택 상태 설정

---

### 4.3 `<label>` 태그 (캡션과 폼 요소 연결)

텍스트(캡션)를 클릭해도 폼 입력 요소가 자동으로 선택되도록 조작 편의성을 높입니다.

```html
<!-- 방법 1: 감싸기 -->
<label>사용자 ID : <input type="text"></label>

<!-- 방법 2: for - id 연결 -->
<label for="user_pass">비밀번호 : </label>
<input type="password" id="user_pass">
```

---

### 4.4 수치, 날짜 및 기타 입력 타입

| 구분 | 태그 / 속성 | 상세 설명 |
| :--- | :--- | :--- |
| **수치 입력** | `<input type="number">` | 스핀 버튼으로 숫자 입력 (`min`, `max`, `step`) |
| **슬라이드 바** | `<input type="range">` | 슬라이더 형태로 대략적인 수치 입력 |
| **날짜/시간** | `<input type="month\|week\|date\|time\|datetime-local">` | 전용 칼렌더 및 시간 셀렉터 제공 |
| **형식 검증** | `<input type="email\|url\|tel\|search">` | 데이터 제출 시 형식 자동 검증 |

---

### 4.5 버튼 요소

- `<input type="button|reset|submit|image">`
- `<button type="button|reset|submit">내용</button>`
  - 💡 `<button>` 태그 내부에는 텍스트뿐만 아니라 **이미지 등 다양한 요소 배치가 가능**합니다.

---

## 5. HTML에서의 색상 표현

1. **16진수 코드**: `#rrggbb` (R, G, B 각각 `00`~`FF` 범위)
2. **RGB 함수**: `rgb(r, g, b)` (0~255 사이 십진수 지정)
3. **색상 이름**: `red`, `blue`, `deepskyblue`, `gold` 등
4. **컬러 입력 폼**: `<input type="color" value="#00BFFF">` 사용 시 색상 선택 팔레트 팝업 출력
