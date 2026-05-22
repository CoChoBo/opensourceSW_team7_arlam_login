# opensourceSW_team7_arlam_login

`opensourceSW_team7` 팀 프로젝트를 진행하면서,
**소비기한 알림 + 로그인 기능(JWT 인증)**을 붙이던 중간 개발 버전을 정리한 저장소입니다.

## 프로젝트 맥락
- 과목: 오픈소스SW 팀 프로젝트
- 주제: 냉장고 식재료 관리 서비스 (Save My Fridge)
- 목적: 식재료 소비기한 관리, 레시피 추천, 음식물 쓰레기 감소

## 이 버전에서 구현/확인한 핵심 기능
- 로그인/회원가입 기능 추가
  - FastAPI `auth` 라우터 + JWT 발급/검증
  - 프론트 `login.tsx`, `register.tsx` 연동
- 사용자 인증 기반 데이터 접근
  - 인증 토큰(`Authorization: Bearer ...`) 기반 재료 조회/삭제
- 소비기한 알림 기능 추가
  - 식재료 카테고리 기준 예상 소비기한 계산
  - 임박 재료 안내 UI(알림 모달) 연결
- 기존 기능 유지
  - 식재료 관리, 레시피/가이드 관련 화면 및 API 연동

## 포트폴리오용 개인 기여 (최다온)
- 아이디어 제안 및 기능 설계 보조
- 화면(UX) 흐름 설계 참여
- 백엔드 보조 개발
  - 식품 날짜가 하루 단위로 갱신/감소되도록 처리하는 로직 구현 및 연동
- 발표자료 제작 및 발표 진행

## 기술 스택
- Backend: FastAPI, SQLAlchemy, SQLite, JWT
- Frontend: Expo(React Native), TypeScript
- AI/기타: YOLO, Gemini API(프로젝트 전체 맥락)

## 주요 경로
- Backend
  - `backend/app/router/auth.py`
  - `backend/app/services/jwt_service.py`
  - `backend/app/services/auth_service.py`
  - `backend/app/services/expiry_service.py`
- Frontend
  - `frontend/app/login.tsx`
  - `frontend/app/register.tsx`
  - `frontend/app/expiry.tsx`
  - `frontend/components/ExpiryAlertModal.tsx`

## 실행 방법
### Backend
```bash
cd backend
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
uvicorn app.main:app --reload
```

### Frontend
```bash
cd frontend
npm install
npx expo start
```

## 참고
- 이 저장소는 최종 완성본이라기보다, 팀 프로젝트 진행 중 기능 통합 과정을 기록한 버전입니다.
- 최종 결과는 `opensourceSW_team7` 저장소와 함께 보는 것을 권장합니다.
