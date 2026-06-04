# 해탈한 코드의 숲 🌿

소프트웨어 엔지니어링과 평화로운 일상이 만나는 아늑한 블로그입니다.

**배포 링크:** https://zoo0blog-40oeio5ot-wouldu012-s-projects.vercel.app/

---

## 스크린샷

| 홈 | 포스트 상세 |
|:--:|:--:|
| ![홈](design/home.png) | ![상세](design/detail.png) |

| 로그인 / 회원가입 | 방명록 |
|:--:|:--:|
| ![인증](design/auth.png) | ![방명록](design/guestbook.png) |

---

## 기술 스택

| 분류 | 기술 |
|------|------|
| 프레임워크 | Next.js 16 (App Router) |
| 언어 | TypeScript |
| 스타일링 | Tailwind CSS v4 |
| 백엔드 / DB | Supabase (PostgreSQL) |
| 인증 | Supabase Auth |
| 배포 | Vercel |

---

## 주요 기능

- **포스트 목록** — 카테고리 필터링 및 페이지네이션 지원
- **포스트 상세** — HTML 컨텐츠 렌더링, 작성자 정보, 읽기 시간 표시, 좋아요 버튼
- **댓글** — 포스트별 댓글 작성 UI
- **로그인 / 회원가입** — Supabase Auth 기반 이메일 인증

---

## 로컬 실행

### 1. 의존성 설치

```bash
npm install
```

### 2. 환경 변수 설정

프로젝트 루트에 `.env.local` 파일을 생성하고 Supabase 프로젝트 정보를 입력하세요.

```env
NEXT_PUBLIC_SUPABASE_URL=your-supabase-url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-supabase-anon-key
```

### 3. 개발 서버 실행

```bash
npm run dev
```

브라우저에서 [http://localhost:3000](http://localhost:3000)을 열면 확인할 수 있습니다.

---

## 데이터베이스 구조

### `posts` 테이블

| 컬럼 | 타입 | 설명 |
|------|------|------|
| `id` | uuid | 기본 키 |
| `title` | text | 포스트 제목 |
| `excerpt` | text | 요약 문구 |
| `content` | text | HTML 본문 |
| `image_url` | text | 썸네일 이미지 URL |
| `categories` | text[] | 카테고리 태그 배열 |
| `author_name` | text | 작성자 이름 |
| `author_avatar_url` | text | 작성자 프로필 이미지 URL |
| `read_time` | integer | 예상 읽기 시간 (분) |
| `created_at` | timestamptz | 작성 일시 |

---

## 프로젝트 구조

```
├── app/
│   ├── page.tsx              # 홈 (포스트 목록)
│   ├── login/                # 로그인 / 회원가입
│   └── posts/[id]/           # 포스트 상세
├── components/
│   ├── Navbar.tsx
│   ├── Hero.tsx
│   ├── HomePageClient.tsx    # 카테고리 필터 + 페이지네이션
│   ├── PostCard.tsx
│   └── Footer.tsx
├── supabase/
│   ├── migrations/           # DB 마이그레이션
│   └── seed.sql              # 초기 데이터
└── utils/supabase/           # Supabase 클라이언트 유틸
```
