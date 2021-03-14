# MIDASIT-Log

2021
===
### 1/2/21 ~ 28/2/21
1. Distributed hotfix

> * Distributed hotfix version 2.0 / 3.0 / 3.1 / 4.0

2. Applied the undo and redo function to the CIM program

> * Documented a list of features that require undo and redo(about 230)
> * Assigned person in charge by function
> * Shared on how to apply the framework functions and got feedback  

3. 질의응답 및 개발 서포트

> * IFCManager History적용 논의
>   + 기존 DBPhase 제거 후 MTransaction으로 변경
>   + DBCommit 실패 로직 추가하기로 결정
>   + MTransactionGuard는 일단 사용하지 않는 걸로 결정

> * Prop창 강제 종료 방식 협의
>   + NeutralPhase의 Gkey 제거를 통한 MainPanel Shutdown하는 방법으로 해결

> * Rebar Draw Undo 시 Prop창 UI 사라지는 버그 디버깅
> * Undo/Redo실행시 DB Update Signal을 통한 로직 검증 
> * DefineScene UndoRedo 로직 검증
> * TextFormat MergeTasks 적용
>   + DefineScene 버그 디버깅 후 원인 파악

> * 그 외 History 관련 개발 서포트
>   + Rollback 사용방법 & Rollback 상황 & 빌드에러 질의응답 
>   + NamedView MergeCommitList 적용 논의 / 정책 설명
>   + PreviewClear 와 Rollback 관계 파악 
>   + render DB undo/redo삭제 시 새 Phase 진입으로 인한 로직 에러 대응
>   + Template Revoke/Rollback적용 시점 논의
>   + EditDefPhase 구조에서 Task생성 위치 논의
>   + Label Redo할 경우 Assert 상황 논의
>   + Tree Task생성 시점 논의 & ini/Rollback 질의응답

4. 응용기능 적용 시 문제 상황 수정

> * 별도의 ini 파일 적용 
> * NeutralPhase Commit으로 인한 버그 수정
> * Dev 브랜치 Conflict 해결

5. 기존 코드에 신규 History 정책 반영

> * 새로운 Phase 부팅은 새로운 브라우저 진입으로 인식 -> Redo 안되도록 적용
> * Undo 발생시 NeutralPhase사라지는 버그 해결
> * Table 수정사항 실시간 반영되는 Phase의 Task 적용 방법 도출
> * Undo 발생시 NeutralPhase로 자동 변환되는 동작 개선
> * Entangle되있는 History 재검사 방지하는 코드 추가
> * 실시간 Table 반영이 필요한 Phase Undo/Redo 적용
> * Mode Undo 동작 시 나오는 경고창으로 인한 Redo동작 삭제 개선 완료
 
6. BugFix

> * SelectEx 기능 ESCKey 동작 추가
>   + ESCKey입력 시 FocusOut되도록 추가
   
7. 코드리뷰 26건 진행

> * History 관련 코드 22건
> * 일반 기능 개발 4건
>   + 현수교 케이블 모델링 Subpanel이슈
>   + Spiral 개발

8 TransactionGuard 문서화

> * 문서화 준비
>   + Phase Commit vs Transaction Commit 차이점 파악 
>   + DB Transaction 개념 파악 & 코드 이해
>   + DB Commit 로직 파악
>   

> * 도식화
>   + 그림으로 도식화

> * 예시코드작성
>   + TransactionGuard 내용 추가
>   + 예시 코드 작성
>   + 실 사용 예시 추가

> * 현재 잘못 사용되고 있는 문법 재공지 & 문서화


---
### 1/1/21 ~ 31/1/21
1. 상반기 계획수립

> * 상반기 계획수립 시간 산정 및 이슈 분리
> * 상반기 내부스터디를 위한 회의

2. Bug Fix

> * PlaneDefPhase 버그 수정

3. History Undo and Redo 기능 개발

> * History 변경 내용 정리 & 커밋(리뷰요청)
> * Mode Finish 이후 Undo처리
>   + Mode Finish 이후 경고메시지 추가에 대한 리뷰 및 검증
>   + ModeManager를 거치지 않는 모드진입에 대한 mergeTask 처리  
>   + 리뷰 반영 
>   + 테스트
> * History TestCode
> * History 코드 리팩토링
>   + History 네이밍 변경 이후 버그 처리
>   + Core에 있는 MakeTask함수 제거 
>   + mphase에 있던 MakeTask함수 사용불가하게 변경
>   + MakeTask함수명 MergeCommitListPerTask로 변경 
>   + phase가 아닌 History를 통해서만 호출하도록 적용
> * Revoke로 인한 무의미한 MakeTask 해결 방법 적용
> * History Revoke 대체 함수 구현(RollbackCommitList)
>   + 기존 Revoke함수 RollbackCommitList함수로 대체 작업
>   + 기존 MakeTask들어간 곳 다시 한 번 재검토

4. Hotfix 배포
> * 1.0 version

5. Phase 긴급 이슈 대응 
> * workstree와 dialog hotkey로 인한 버그 이슈


---



2020
===
### 1/12/20 ~ 31/12/20

1. 정식출시

> * 출시세미나

2. Test

> * Table UI 기반 Unit Test code 
> * History Test코드 보완
>   + Task 생성 전에 임시 Task로 쌓이는 동작에 대한 Undo 규칙 마련
>   + 초기에 Task지정을 하지 않았을 땐 즉, Task가 0개일 때는 Undo가 의도된 동작이 아니기 때문에 안되야 하는게 맞기 때문에 그쪽으로 코드 변경 후 테스트
>   + History TopTask Redo Test
>      - 마지막 TopTask까지 정상 Redo되도록 로직 변경 완료
>   + MPhase에 속해있는 Apply 내부 MakeTask 제거 테스트 
>      - FeatureSketch로 테스트 진행 
>      - 각 클래스에서 MakeTask할 경우 DrawPhase의 경우 내부에 있는 Commit으로 인해 TopTask 생성 -> undo 2번
>   + History TopTask Undo될 때 TopTask+마지막Task 모두 Undo되도록 TEST
>      - TopTask에 쌓이는 Commit기록을 제어하는 건 어려울거라 판단
>      - 둘이 같이 Undo되었을 때 문제될만할건 없는지 확인필요
>      - Phase의 History에서 Commit된 후에 Phase꺼진경우 History는 Expired되지만, Undo는 됨

3. bugfix

> * Phase 긴급이슈대응
>   + json script-show관련 동작 관련 대응 및 해결 방법 제안 
>   + ColorPicker json&panelUI 동작 안되는 상황 대응 및 해결 방법 제안(ColorPanelUI에 role분리)
> * Drawpanel Checked 상태가 2개가 되는 이슈
>   + Check/Uncheck되는 시점 & Notify위치 변경 완료
> * Test진행시 파일을 한번 생성 후 로컬에서 오픈하여 이용하는 로직에서 NeutralPhase가 뜨지 않는 현상 디버깅(UI Update로 인한 문제였음)

4. History 보완

> * RootHistory의 TopTask가 쌓여있을 떄의 문제 상황 해결 & Test코드 강화
>   + 문제상황 : RootHistory에 Task가 쌓이기 전에 EmptyStep만 있을 경우에 Undo를 하게 되면 차마 Entangle이 일어나기 전이라서, Child들의 TopTask의 Undo가 일어나지 않는 문제(추후 MakeTask가 퍼지면 매우 문제될 것으로 판단되서 고치기 시작함)
>   + 해결방법 : RootHistory의 TopTask가 Undo되는 것이라면 Root Undo전에 Child들의 TopTask부터 Undo하도록 코드 추가
> * 지난번 Merge된 History 코드에 대한 재검토 진행 후 조건 추가
>   + 기존에는 Undo와 Redo를 하면 무조건 해당 플래그가 false가 되어 기존에 있던 TopTask가 보존되지 않고 Task가 무조건 생성되어 문제
>   + 따라서 제거하였었지만, TopTask에 대한 Undo가 정확하게 이루어진다면(현재 수정중인 코드) 해당 플래그를 Undo/Redo내부 조건에 따라 적절히 넣어줘야 하므로 추가
> * Revoke/DB Transaction 관련 이슈 논의
>   + 잘못된 Commit으로 인한 Revoke오류 -> Commit을 Rollback으로 변경
> * History Undo 이후 NeutralPhase 뜨지 않는 오류 발견
>   + Undo후에 Neutral에 대한 처리가 기존에 없었음 : 추가함
> * History의 Doc초기 설정 중 예전 코드로 인해 초기 값 맞지 않는 부분 수정
>   + Neutral이 뜬 이후에 Phase를 Reset해주는데 그 전에 Doc Open할 때 초기 값을 잡아놔서 History 시작 Task가 1로 되있었음(이러면 가장 처음 쌓은 Task에 대한 Undo/Redo가 불가능해짐)
> * 객체 삭제에 대한 Undo/Redo가 Delete의 Task로 인한 것이 아닌 Neutral의 Select 때문이란 것 발견(Select할 때마다 Task 쌓임)
>   + Delete쪽에서 Task쌓을 수 있도록 조치
>   + Select에 있던 MakeTask삭제
> * ShutDown할 때 만드는 Task에 대한 Test 진행 후 삭제
>   + ShutDown 하면서 Task를 만들면 사용자가 원하는 Undo동작이 아닌 무의미한 Undo동작이 한 번 더 추가됨
>   + ShutDown을 Undo한다고 해서 Phase가 살아나는 것이 아니고, Booting에 대한 Task를 Undo해야 살아나는 것이기 때문에 제거

5. hotfix

> * hotfix 세팅 & 테스트

6. mphase의 MakeTask와 History의 MakeTasek 호출 통합

> * mphase의 MakeTask호출은 문제 x
> * History의 MakeTask를 외부에서 직접호출하는 건 현재로직에선 문제의 소지가 있음 
> * 지금 로직은 MakeTask_Root를 통해 Entangle되어있는 각각의 History를 모두 MakeTask해주는 형태
> * 일반 기능에서 MakeTask만 호출하면 Entangle되있는 History가 꼬여버릴 수 있음
> * MakeTask_Root로 Entangle을 모두 Task해주는 부분까지 완료
> * 해당 로직을 적용하지 않은 일반 기능 단에서 호출 중인 MakeTask 부분 커버 안된 상태
> * 이제 각 Task별로 반드시 TaskName 작성하는걸로 규칙 변경

7. History 개선

> * SetTransactionBase -> LimitUndoTargetToCurrentTask
>    + Mode 나올 땐 Target을 다시 0으로 리셋해주면 되지만, 그러면 Mode안에서 진행 된 Task들에 대한 처리를 어떻게 해줄 것인가가 남아있음
>    + Mode에 있는 Task는 하나로 처리할건지, 하나하나 TaskName을 보여주며 처리해야 할지
>    + Revoke를 위한 Task들도 Mode안에 많기 때문에 그대로 Undo했을 경우에 대한 테스트가 필요
> * TaskName에 대한 표시방법 고민중 
>    + TaskName을 반환해 줄 방안 이것저것 해보는 중
> * Mode Finish될 경우 Undo Target 기존대로 변경
>    + Mode를 들어갔다 나온 경우 Undo가 다시 잘 되도록 변경함 
>    + 이 때, Redo하는 상황에 문제가 생김
>    + Redo할 경우 Mode에 다시 진입한 것처럼 데이터가 바뀌고 UI에는 변화가 없기 때문에 해당 Mode로 다시 진입하는 것이 불가능해진다(이미 진입한 것처럼 데이터가 Redo되어서)
>    + Redo가 안되게 해야할지 고민 

8. 팀장님과 History관련 방향성 논의 

> * MakeTask, SetTransactionBase라는 함수명이 모호할 수 있어서 새로운 네이밍으로 변경하기
> * ModeManager에서의 History설정 문제 -> 좀 더 고민
> * History관련 우선 순위 논의
   1) Revoke될 때 한번에 와장창 되는 버그(재현방법만 알면 고치는데 도움이 될듯 ㅠㅠ)
   2) SetTransactionBase의 기능에 맞춰서 함수명 변경 및 현재 ModeManager쪽에 들어간 사용 위치 재검증
   3) MakeTask의 사용법을 알 수 있는 함수명으로 변경 
   4) MakeTask에서 만들어내는 Task의 분류가 필요할 듯 
   5) Revoke말고 Task를 진짜로 Grouping해서 쓸 수 있는 방안에 대해 고민



---
### 1/11/20 ~ 30/11/20

1. History 현재 알고리즘 재파악

> * History Entangle 디버깅

2. History 실제 문제 상황 파악

> * 객체가 Delete된 이후 Undo를 하면 바로 복원되지 않고 2번에 걸쳐야 복원
>   + CIMDeleteObject클래스에 있던 예전 코드들을 지운 뒤 단순히 Transaction 프로세스를 방어해주는 코드로 변경하여 바로 Undo를 하면 객체가 생성되도록 수정 
>   + 잘못사용한 MakeTask문제
> * PointViewUI사용하는 기능에서 같은 문제 발생
>   + 잘못사용한 MakeTask문제로 제거

3. History 관련 코드(MakeTask호출) 전수조사 & History 내부 Data 테스트

> * SetValue(Data변화)에 따른 History 내부 Data Test
> * History Commit, MakeTask호출 시점에 따른 InnerTask의 변화 Test

4. History TestCode 보완

> * TopTask만 있는 상태에서 Undo/Redo했을 때 History변화를 중점으로 Test
> * PanelUI History Test 완료 -> Commit/MakeTask 잘 넣어주니 Undo/Redo 매우 잘됨
> * Undo했을 때 Phase가 꺼지는 경우와 안꺼지는 경우 차이점 파악(LayoutEdit기능으로 확인)
>   + AppearEvent 이후에 Commit을 할 경우 Undo하면서 Phase가 꺼짐
>   + 처음에 안꺼지다가 ShutDown한 이후엔 Undo로 꺼져버림
>   + Shutdown될 때 MakeTask를 하고있어서 생기는문제
>   + Boot Step이 Undo되면서 Shutdown이 불리는것
>   + Boot와 Shutdown시점을 Undo/Redo로 기억해야 하는가에 대한 의문.. 없애는게 좋을 듯하다(버그유발)
>   + Appear될 때 UI요소의 개수대로 DB쪽에 Commit이 되고 있어서 의미없는 Undo/Redo가 실행된다  
>   + 어떤식으로 제거해야될지 고민
> * History Boot/Shutdown 시점에 Task 제거 후 테스트 진행
>   + 이것이 원인이 되어 Phase가 꺼지는 현상(의도된 동작같아보이지만)은 없앨 수 있음
>   + but 매우 위험할 수 있는 버그가 있는 듯하여 (패널은 떠있고 Phase만 사라진다던지) 좀 더 테스트가 필요
>   + Appear/Disappear시점에 Commit을 해주고 있는데(예전코드), 왜해줘야됐었는지 디버깅

5. hotfix 배포 준비

> * hoxfix 용 Desktop App 아이콘 변경
> hotfix / Install TEST

6. BugFix

> * Dialog Position 조건 강화
> * Dialog ContentPhase Ok버튼 클릭시 자동으로 Shutdown되도록 수정
> * DWG에서 파일탐색기 취소 버튼 클릭 시 Neutral로 포커스 가도록 로직 변경
> * GeomPhase(Draw) Enable상태값 변경오류 해결
> * PanelUI UnitChange함수 호출로 인한 버그 상황 방지
> * Dialog Size조절 안되도록 수정
> * Dialog 글씨 잘림 현상 수정

---
### 1/10/20 ~ 31/10/20

1. 신규기능 추가 & 버그 Fix

> * Apply 실패시 ShutDown Cancel 로직 추가
> * Mode진입 후 NeutralPhase사라지는 현상 해결
> * table appending 도중, TablePanelUI가 Update 되어 현재 작업 중인 row가 삭제되는 버그 해결
> * Draw Widget 색상 변경 오류 수정

2. 베타버전 출시 전 Bug Fix

> * Json Focus Setting Bug Fix
>   + MPhasePanel에서 Launcher를 통해 Launched된 Phase와 panel의 Path를 이용하여 Focus될 Phase를 구하는 방식으로 전면 수정
> * json에서 같은 Phase에 2번 추가해줘서 생긴 문제 해결
> * Point/Vector Focus에 따른 Commit발생 관련 로직 통일
> * PointViewUI Mouse Click Delay Bug Fix
> * Dialog ESCKeyDown이용하여 Close 할 때 발생하는 버그 Fix
>   + ESCKey입력에 따른 동작 수행 비동기 Event방식으로 변경
> * Point TakeRequest에 따른 버튼 UIUnit 지정 기능 추가
> * ModeCancel 시 Mode변환이 제대로 이뤄지지않는 버그 해결
> * NeutralSelect Object 삭제 후 Undo했을 때 선택된 객체가 View에서 Clear되지 않는 문제 해결
> * BaseArcDefPhase Tangent Focus 오류 해결
> * ArcDefPhase의 3point 옵션 선택시 기존 preview전부 clear되는 현상 해결
> * DrawPlane Change시 VectorViewUI CoordinateSystemUI Reset으로 인한 버그 해결


---
### 1/9/20 ~ 30/9/20

1. 각종 Bug Fix

> * DrawPhase CenterPoint기능 오류 해결
> * DrawPhase에서 Focus정상동작으로 인한 기존 기능 비정상동작 해결
> * edit widget 동작 개선
>   + Lincense 창에서 Doc이 열리기 전에 Edit에 대한 이벤트 처리 추가
> * OptionPhase SelectOption코드에 Disable된 Option Assert해주는 코드 추가
> * TendonEditor ESC기능 Bug Fix
> * MTable OnKillFocus & 유효하지 않은 Data반환 문제 해결

2. 새 Focus정책에 맞도록 기능 추가 및 기존 코드 수정

> * Plane By Offset 이상동작 해결
>   + Focus정책 실행후 기존 Focus대로 짜여있던 코드에서 문제가 발생하여 생긴 오류
> * Focus 전환시 intercept해가는 코드 제거
>   + 예전에 Focus전환이 잘 이루어지지 않아서 생긴 코드로 추측
> * SelectPhase에 쓰이는 ButtonWidget 재클릭 시 FocusOut되도록 기능 추가

3. 신규기능 추가 & 버그 Fix

> * json에서 직접 처음 Focus가 들어갈 Panel에 대해지정하는 기능 추가
> * Validator 적용을 위해 AsyncUpdate 적용 및 테스트
> * Validator 적용 코드리뷰 & 서포트
> * Polyline Spline Draw Preview 미동작 버그 해결
> * DrawPhase InterceptDefine함수 관련 기능 복구

4. Focus Test & Focus 예외처리 추가

> * TakeRequest 호출을 통한 Focus 세팅 검증
> * 중복 TakeRequest 호출에 따른 Focus 세팅 검증
> * GroupPhase의 TakeRequest 호출에 따른 Focus 세팅 검증
> * 실제 화면에 UI가 생성될때 Focus의 흐름과 Tab KeyboardEvent로 인해 발생되는 Focus 로직 검증
> * MainPanel Widget에 MouseEvent로 인해 발생되는 Focus 로직 검증
> * Prop창 Focus 예외처리
>   + 객체 삭제로 인한 Prop창 종료시 NeutralPhase가 제대로 나오지 않는 현상 해결
>   +  PropManager에서 StartMainPhase호출 시 Focus가 Reset되지 않는 예외함수 구현
> * BaseLineDef Phase의 Focus가 제대로 안가는 문제 해결


---
### 1/8/20 ~ 31/8/20

1. 각종 Bug 디버깅 & Refactoring

> * Parameter Dialog Table 세팅시 무한루프 빠지는 오류
> * Concreate Append중복된 문제 해결
> * Phase Title 대소문자 적용 규칙 문제 해결
> * Select 중 enter 키 입력시 동작 오류 해결

2. Focus 규칙 재정의 및 코드 재설계 후 재구현

> * 기존 Focus 규칙 문서화
>   + 상황별 Focus 순서 및 로직 주요 개념 정리
> * TakeRequest 호출 규칙 재정의
> * Focus Interface 통합 Refactoring
> * Focus관련 비정상동작 Fix
> * Point, VectorPhase TakeRequest호출 시 Edit창대신 버튼에 포커스가도록 조정
> * ViewUI에서 ESC클릭 시 무조건 NeutralPhase로 가는 동작 제거
> * CalendarPanelUI Focus 되었을 때 열리고 닫히는 기능추가

3. UI관련 코어 로직 리팩토링

> * UISlot
> * Panel / PaneluUI
> * UIPlugIn

4. Table Bug Fix

> * 동적 Table 생성 안됐던 버그 해결
> * 동적 Table 생성 후 화면에 바로 Update 안되는 버그 디버깅 
> * TablePhase Clear Logic 추가
> * Table의 단위 변환 버그 해결


---
### 1/7/20 ~ 30/7/20

1. License윈도우 화면 DialogPhase이용하여 띄울 수 있도록 구현

> * Phase Entangle Case 정의
> * DrawPanelUI 무조건 SetChecked되는 방식 변경
>   + DrawPanel은 항상 UI가 On되어있어, 2개의 UI가 On되는 버그 해결
> * AutoMode Dialog 경로 설정 Bug Fix

2. Focus관련 Bug Fix

> * 모든 PanelUI Focus 규칙 적용
> * MPanel 조건 수정 / DrawPhase Clear할 때 Focus되는 코드 제거
> * FeatureSweepPhase 종료시 호출되는 TakeRequest 제거

3. 각종 버그 Fix & 추가기능 구현

> * 객체 Select 후 Delete 바로 안되는 버그 해결
> * AutoMode Template 갑자기 멈추는 현상 해결
> * TendonEditor의 2DViewUITargeter가 제대로 매칭되지 않아서 UI생성이 안되었던 버그 해결
>   + SetPhasePath를 실제 Path에 맞게 수정
>   + Targeter를 생성할 때마다 UILauncher도 생성해주도록 새로운 Custom2DViewUILauncher 생성
> * Dialog Update시 크기가 줄어드는 현상 해결
> * SubPanelUI의 초기 사이즈 설정 기능 추가
> * Dialog ESC로 종료되는 기능 추가

4. Focus 관련 코드 개선 & 리팩토링 시작

> * PanelUI&Widget Focus 기존코드 개선 & 리팩토링
>   + 각 PanelUI에 산발적으로 구현되어 있는 코드 개선 및 리팩토링
>   + Widget에 대한 Focusing을 MPanelUI에서 통합적으로 관리할 수 있도록 개선
>   + WidgetFocusIn 함수 실행 시 widget상태 검증 코드 추가
>   + UIManager 리팩토링
> * AUIWnd의 키보드이벤트 입력 시 내부 WidgetManager로 받도록 규칙 생성 및 구현


---
### 1/6/20 ~ 30/6/20

1. Dialog 추가 구현

> * Dialog 스크롤 없애는 기능
> * Rebar DialogPhase 도입
> * DialogPublisher RT

2. AutoMode BugFix

> * AutoMode에서 Dynamic Launcher Path설정 시 부모 경로가 아닌 본인 경로만으로 Phase매칭하려고 해서 매칭이 안됐던 버그 해결
> * AutoMode에서 Append실시간 반영시 Json이 반대로 생성되는 이슈
> * ViewUI의 Parent가 아닌 자식으로 생성해야 하나 따로 판별기준이 없어 해당 부모의 경로 유무로 판단하여 고침 

3. EditPanel 개선

> * EditPanel 편집시 단위 안나오도록 조정
> * VectorPanel & PointPanel Tab기능 추가
> * Enable아닌 EditPanel의 단위 안없어지도록 수정
> * EditPanel외에 MainPanel의 다른Panel Tab버튼으로 이동가능하도록 기능추가
> * EditPanel 편집 시 일정 범위 이상 넘어가면 지수로 안바뀌도록 변경(Edit완료후에 바뀌도록)
> * Mouse로 Focus하면 단위가 제대로 안없어졌던 문제 해결
> * EditPanel의 부분클릭 후 Remove가 제대로 안되던 현상 해결
> * Edit의 Rotate DrawPanel UnCheck동작 제대로 안됐던 버그 해결

4. AutoMode 추가 구현 & BugFix

> * AutoMode CuttingBoxPhase, RectangeArrayPhase 기능추가
> * AutoMode일 때 Boolean페이즈가 토글형태로 icon적용없이 버튼만 나오는 버그 Fix
> * AutoMode일 때 Table이  나왔다 안나왔다 하는 이슈 해결
> * Release환경에서 AutoMode사용할 수 있는 방안 도입
> * AutoMode_Select/DBKey 구분되어 생성되도록 변경


---
### 1/5/20 ~ 31/5/20

1. Json Auto Generator Dialog 생성 기능 추가
2. MDKUILauncher Loader Begin Function코드 리팩토링
> * loader실행 시 작동해야하는 기능별로 함수를 분리하여 데이터 이동을 수월하게 변경
3. Dialog Publihser 개발
> * 여러가지 콘텐츠 조합하여 Dialog에 append할 수 있도록 로직 변경 
> * 리본메뉴에서 Dialog 바로 사용가능할 수 있도록 DialogPublisher 기능 추가
4. ClippingPhase AutoMode로 생성할 수 있도록 구현


---
### 1/4/20 ~ 30/4/20

1. 디버깅용 자동 UI생성을 위한 json AutoGenerator 설계
2. 디버깅용 자동 UI생성을 위한 json AutoGenerator 구현
3. json Auto Mode 구현 
4. 다국어버전 명칭 호환을 위한 Json 구조 설계

---
### 1/3/20 ~ 31/3/20

1. MultiDialog 도입 및 Test
2. DialogPhase 관련 버그 Fix
> * Dialog 창이 윈도우 화면 밖으로 나갔을 경우 화면 컨트롤 불가한 이슈
>   + 키보드 이벤트(ESC종료) 추가
> * Dialog Window창크기 변경안되는 이슈
>   + Dialog 창 높이가 모니터 사이즈보다 커질 경우 스크롤이 자동생성되는 기능 추가
3. Phase프레임워크 UILauncher 알고리즘 분석


---
### 1/2/20 ~ 29/2/20

1. AliceUI Window 창조절 기능 개발
2. DialogPhase TestCode
3. DialogPhase Modal Z index 수정
> * Dialog Modal로 실행 시 Z index가 무조건 최상위에 오는 현상 해결(다른 프로그램보다 항상 최상위)
4. DialogPhase Window 최대화 기능 구현
> * AUIWindow 최대화 클릭 시 최대크기로 변경되는 기능
> 최대화되었을 때 아이콘 변경
> 재클릭 시 다시 원래크기로 돌아가는 기능
> 다시 원래크기로 돌아갔을 때 아이콘 최대화아이콘으로 변경
5. Phase 적용 이론 작성 및 공유
> * Phase의 UI개발철학에 대해 정리(PhaseEvent 관련 내용 정리)
6. Window Resize관련 버그 처리


---
### 1/1/20 ~ 31/1/20

1. Phase프레임워크 History(Undo/Redo) 기능 분석
> * Phase프레임워크 History(Undo/Redo) 기술 문서 작성
2. DialogPhase 부가 기능 개발
> * DialogPhase 위치설정 기능 추가 - Dialog 생성 시 생성되는 위치를 사용자가 지정할 수 있도록 기능 추가
3. DialogPhase WindowMessage 대체
> * Document생성주기 관련 윈도우 메시지 DialogPhase로 변환(WaitEvent적용)
4. DialogPhase 내부 History 적용 및 삭제
> * 분석한 History 기능을 기반으로 dialogPhase 내부에 History기능 추가
> * Dialog자체의 History 기능 생성 시 윈도우가 CtrlZ/Y로 꺼졌다 켜졌다 함
> * 타 프로그램에도 새 윈도우 창에 대한 Undo/Redo 속성은 존재하지 않기에 Dialog에 History기능 빼기로 결정


---



2019
===
### 7/12/19 ~ 31/12/19
1. Selected as an 'Overseas advanced technology training experience group' hosted by a South-Korean government agency(MSIT)
> * 7/12/19 ~ 16/12/19
> * Purpose of experience
>    + Visiting leading companies with advanced digital content technology
>    + Experiencing new technology and building a global network with local experts
>    + Evaluating the global market for expansion strategy of Korea IT and maximizing its competitiveness
> * Visited companies
>    + Google 
>    + RiotGames
>    + Digital Domain
>    + USC Lightstage
>    + The Mill
>    + MetaStage
>    + AmazeVR
> * _More details will be summarized in a separate document._

2. Documented window popup UI creation function
> * Framework manual documentation
> * Technical documentation


---
### 1/11/19 ~ 6/12/19

1. Developed function to create windows popup ui in own framework(named 'Phase')
> * Learned how to handle asynchronous UI in own framework
> * Documented function list
> * Structure design
> * Developed prototype (Development of warning message popup using the framework's PopupUI function)
>    + Developed so that a pop-up window containing yes/no/cancel buttons appears when the test button is clicked
>    + Applied UI design using json
> * Refactored code after review
>    + Changed some function to templates


---
### 1/10/19 ~ 31/10/19

1. Developed UI function using own framework(named 'Phase')
 
> * function : Constraint Point( This function selects the type of Constraint Point) 
>    + Developed a module that integrates the select function and the optional function
>    + Implemented the ability to select a specific location on the selected object
>    + Implemented specific constraints to appear in the selected location
>    + Link : [Constraint Point-Manual](https://cim-learning.refined.site/space/manualCIM/1414830/Constraint+Point+(Assembly+Unit))

2. Developed UI function using own framework(named 'Phase')

> * function : Constraint Path( This function selects the type of Constraint Path) 
>    + Developed a sub constraint path function UI
>    + Link : [Constraint Path-Manual](https://cim-learning.refined.site/space/manualCIM/1480076/Constraint+Path+(Assembly+Unit))

3. Unit Test

4. Refactored main popup UI

> * Redesigned class structure and class separation
> * Renamed functions and variables in code
> * Removed duplicate code

5. Fixed an error in main popup function

> * Fixed an error that some sub-lists could not be opened in the nested list UI
>    + Main cause : 
> * Documented the cause of the error and the workflow
> * Link : [Main Popup UI](https://cim-learning.refined.site/space/manualCIM/297402540/%EB%B6%88%EB%9F%AC%EC%98%A4%EA%B8%B0+%2F+%EB%82%B4%EB%B3%B4%EB%82%B4%EA%B8%B0)


---
### 1/9/19 ~ 30/9/19

1. Improved layout function ruler widget UI
 
> * Changed RulerWidget scale unit
> * Created scale range (maximum and minimum values applied)
> * Added grid highlight line</blockquote></deatils>


2. Developed UI function using own framework(named 'Phase')
 
> * function : Constraint Type( This function selects the type of Constraint ) 
>    + Developed UI for extracting Library Distance values
>    + Modularization to simplify the use of filters in the selection function
>    + Link : [Constraint-Manual](https://cim-learning.refined.site/space/manualCIM/1344817/Constraint)


---  
