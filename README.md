# 요구사항 분석  
- MVC 패턴을 사용한다.  
- 상품을 관리할 수 있는 서비스 구현한다.  
---
## 상품 도메인 모델  
- 상품 ID
- 상품명
- 가격
- 수량
---
## 상품 관리 기능
- 상품 목록
- 상품 상세
- 상품 등록
- 상품 수정
---
## 서비스 제공 흐름
![image](https://github.com/kyungshik/item-service/assets/98220653/553ee8d6-69a3-4074-b3f8-b7ff6728beb6)
- 상품 목록 조회: 상품 목록 **컨트롤러**에 접근하여 상품 목록 **뷰**를 **렌더링** 한다.
- 상품 등록: 상품 등록 폼 **컨트롤러**에 접근하여 상품 등록 폼 **뷰**를 **렌더링** 한다. 뷰는 타임리프를 사용한다.
- 상품 저장: 상품 등록 폼에서 저장 버튼을 누르면 상품 저장 **컨트롤러**로 이동한다.
- 상품 상세: 상품 상세, 상품 저장 후 모두 같은 서비스를 재공하여 재사용성을 높인다. 내부 호출을 통해서 상품 저장 **컨트롤러**가 상품 상세 **뷰**를 렌더링 한다.
- 상품 수정: 상품 상세 뷰에서 상품 수성 버튼을 누르면 상품 수정 폼 컨트롤러로 이동한다. 수정 후 상품 상세로 **Redirect** 한다.

### 업무 분담
- 디자이너: 요구사항에 맞도록 디자인하고, 디자인 결과물을 웹 퍼블리셔에게 넘겨준다.
- 프론트엔드 개발자: React, Vue.js (HTML, CSS) 웹 클라이언트 기술 사용. HTML 을 동적으로 만드는 역할과 웹 화면이 흐름을 담당한다. 
- 백엔드 개발자: 디자이너, 웹 퍼블리셔를 통해서 HTML 화면이 나오기 전까지 시스템을 설계하고, 핵심 비즈니스 모델을 개발한다. 이후 HTML이 나오면 이 HTML을 뷰 템플릿으로 변환해서 동적으로 화면을 그린다. 웹 화면의 흐름을 제어한다.
- 절충안: 백엔드 개발자는 HTML 뷰 템플릿을 직접 개발하는 대신, HTTP API를 통해 웹 클라이언트가 필요로 하는 데이터와 기능을 제공할 수 있다.
---
