# display-flex 포트폴리오 고도화 계획

기존 `display-flex` Next.js 프로젝트를 실제 백엔드가 있는 포트폴리오 사이트로 고도화하는 것이 목표입니다. **Prisma와 SQLite**를 사용하여 데이터베이스를 구축하고, **Next.js Server Actions**를 사용하여 백엔드 로직을 구현할 예정입니다.

## 작업 목록

- [ ] 프로젝트 설정 및 구성
    - [ ] Prisma 설치 및 SQLite 초기화 <!-- id: 0 -->
    - [ ] 데이터베이스 스키마 정의 (Project, Post, Contact) <!-- id: 1 -->
    - [ ] 마이그레이션 실행 <!-- id: 2 -->
    - [ ] 시드(Seed) 데이터 기능 (포트폴리오용 더미 데이터) <!-- id: 3 -->
- [ ] 백엔드 구현 (Server Actions)
    - [ ] `src/actions/project.ts` 생성 (프로젝트 CRUD) <!-- id: 4 -->
    - [ ] `src/actions/post.ts` 생성 (게시글 CRUD) <!-- id: 5 -->
    - [ ] `src/actions/contact.ts` 생성 (문의 제출 처리) <!-- id: 6 -->
- [ ] 프론트엔드 구현 - 공개 페이지
    - [ ] `src/app/projects/page.tsx` 생성/업데이트 <!-- id: 7 -->
    - [ ] `src/app/blog/page.tsx` 생성/업데이트 <!-- id: 8 -->
    - [ ] `src/app/contact/page.tsx` 생성/업데이트 <!-- id: 9 -->
    - [ ] 메인 홈페이지 `src/app/page.tsx` 업데이트 (최신 항목 표시) <!-- id: 10 -->
- [ ] 프론트엔드 구현 - 관리자 (간단 버전)
    - [ ] 관리용 `src/app/admin/page.tsx` 생성 <!-- id: 11 -->
    - [ ] 프로젝트/게시글 추가 폼 생성 <!-- id: 12 -->
- [ ] 검증
    - [ ] 데이터베이스 연결 확인 <!-- id: 13 -->
    - [ ] UI를 통한 데이터 생성/조회 확인 <!-- id: 14 -->

## 구현 상세

### 데이터베이스 계층 (Prisma + SQLite)
#### `prisma/schema.prisma`
- `Project` 모델: 제목, 설명, 이미지, 링크, 태그
- `Post` 모델: 제목, 내용, 작성일
- `ContactSubmission` 모델: 이름, 이메일, 메시지

### 백엔드 (Server Actions)
- `getProjects()`, `createProject()`
- `getPosts()`, `createPost()`
- `submitContactForm()`

### 프론트엔드 구성
- **메인 페이지**: 최신 프로젝트/블로그 글 노출
- **프로젝트 목록 페이지**: 그리드 뷰
- **블로그 목록 페이지**: 리스트 뷰
- **문의 페이지**: 폼 제출 기능
- **관리자 페이지**: 콘텐츠 추가 (간단한 비밀번호 보호 또는 로컬 전용)
