# MIDASIT-Log

19
9 (1) Layout치수 UI 개선
 1.RulerWidget 눈금 단위 변경
 2.눈금 범위 생성(최대,최소값 적용)
 3.강조선 추가
9 (2) Phase프레임워크로 UIPhase개발
 Constraint Tyep UI
9 (3) Phase프레임워크로 UIPhase개발
 ConstraintPlaneCreate 페이지에 사용될 Library Distance 값 추출을 위한 Phase 개발
9 (4) Phase프레임워크로 UIPhase개발
  Constraint Select Phase Module 생성(SelectPhase의 필터사용을 간편화하기 위해 모듈화 작업 진행)
10 (1) Phase프레임워크로 UIPhase개발
  Constraint Select Option Phase 모듈 생성 및 SelectExPhase 기능 추가
    1.  Select / Option Phase 통합 Phase 모듈화(Constraint Point)
    2.  Select 기능을 SelectExPhase처럼 선택한 특정 오브젝트에 특정위치(point) 선택 가능하도록 구현
    3.  선택한 point에 특정 오브젝트(Constraint) 나올 수 있도록 구현
10 (2) Phase프레임워크로 UIPhase개발
  Sub Constraint Path Phase 구현
    1. Create/Const/Prop Phase 각각 생성
    2. CreatePhase 의 Draw path 기능의 경우 LLTAssignRefPhase 참고하여 진행
10 (3) CIM 프로젝트 사용성 TEST 진행
  이슈 생성 및 재현 사항 정리
10 (4) MainButtonWidget(PopupUI) Refactoring
  1. 클래스 구조 재설계 & 클래스 분리
  2. 네이밍 & 중복코드 제거
  3. Focusing Bug Fix
  4. 동작흐름 정리 & 문서화
11 (1) DialogPhase구현 준비 - LabelPhase 로직 파악
  1. Dialog Phase 구현을 위해 이벤트 처리 방식 파악 필요
  2. LablePhase 구현 로직 파악
11 (2) Dialog Phase 설계
  1. Dialog Phase 내부 구성 
  2. 구현 기능 정리 및 설계
  3. 구현에 필요한 연관된 클래스 파악 및 재생성
11-3 DialogPhase 포로토타입 개발(경고팝업)
  1. Select 후 버튼 클릭 시  Yes/No/Cancel 버튼 포함되어 있는 경고 팝업 뜨도록 구현
  2. 해당 Dialog Json적용하여 Window팝업 대체할 수 있도록 변경
11-4 DialogPhase 코드리뷰 및 수정
12-1 Dialog Phase Template구조로 변경
  1. DialogPhase 기능 제공에 앞서 생산성 향상을 위해 Template으로 코드 변경 진행
  2. 프로토타입 코드 구조 설계 및 변경
12-2 미국 해외연수
12-3 미국 해외연수
12-4 DialogPhase 개발문서 작성

20
1-1 Phase프레임워크 History(Undo/Redo) 기능 분석
1-2 Phase프레임워크 History(Undo/Redo) 기술 문서 작성
1-3 DialogPhase 부가 기능 개발
  DialogPhase 위치설정 기능 추가 - Dialog 생성 시 생성되는 위치를 사용자가 지정할 수 있도록 기능 추가
1-4 DialogPhase WindowMessage 대체
  Document생성주기 관련 윈도우 메시지 DialogPhase로 변환(WaitEvent적용)
1-4 DialogPhase 내부 History 적용 및 삭제
  1. 분석한 History 기능을 기반으로 dialogPhase 내부에 History기능 추가
  2. Dialog자체의 History 기능 생성 시 윈도우가 CtrlZ/Y로 꺼졌다 켜졌다 함
  3. 타 프로그램에도 새 윈도우 창에 대한 Undo/Redo 속성은 존재하지 않기에 Dialog에 History기능 빼기로 결정
2-1 AliceUI Window 창조절 기능 개발
2-2 DialogPhase TestCode
2-3 DialogPhase Modal Z index 수정
  Dialog Modal로 실행 시 Z index가 무조건 최상위에 오는 현상 해결(다른 프로그램보다 항상 최상위)
2-3 DialogPhase Window 최대화 기능 구현
  AUIWindow 최대화 클릭 시 최대크기로 변경됨
  변경필요한 부분 : 
  >최대화되었을 때 아이콘 변경
  >재클릭 시 다시 원래크기로 돌아가야 함
  >다시 원래크기로 돌아갔을 때 아이콘 최대화아이콘으로 변경되어야 함
2-4 Phase 적용 이론 작성 및 공유
  Phase의 UI개발철학에 대해 정리(PhaseEvent 관련 내용 정리)
2-4 Window Resize관련 버그 처리
3-1 MultiDialog 도입 및 Test
3-2 DialogPhase 관련 버그 Fix
  1.Dialog 창이 윈도우 화면 밖으로 나갔을 경우 화면 컨트롤 불가한 이슈
    키보드 이벤트(ESC종료) 추가
  2. Dialog Window창크기 변경안되는 이슈
3-3 Dialog Height가 화면보다 커질 경우 스크롤 자동생성 기능 추가
  Dialog 창 높이가 모니터 사이즈보다 커질 경우 스크롤이 자동생성되는 기능 추가
3-4 Phase프레임워크 UILauncher 알고리즘 분석
4-1 디버깅용 자동 UI생성을 위한 json AutoGenerator 설계
4-2 디버깅용 자동 UI생성을 위한 json AutoGenerator 구현
4-3 json Auto Mode 구현 
4-4 다국어버전 명칭 호환을 위한 Json 구조 설계
5-1 Json Auto Generator Dialog 생성 기능 추가

























