# Django Multiple User Types Example

이 프로젝트는 [sibtc/django-multiple-user-types-example](https://github.com/sibtc/django-multiple-user-types-example)을 기반으로 하여, 학생과 교사라는 두 가지 사용자 유형을 지원하는 Django 애플리케이션입니다. 로컬 및 클라우드 서버에서 실행되도록 커스터마이징되었으며, 현재 [http://223.130.130.225:8000](http://223.130.130.225:8000)에서 작동 중입니다.

## 주요 기능
- **학생 기능**:
  - 퀴즈 목록 보기 (`/students/`)
  - 관심사 설정 (`/students/interests/`)
  - 퀴즈 응시 (`/students/quiz/<id>/`)
- **교사 기능**:
  - 퀴즈 생성 및 관리 (`/teachers/`, `/teachers/quiz/add/`)
  - 질문 추가 및 수정 (`/teachers/quiz/<id>/question/add/`)
  - 퀴즈 결과 확인 (`/teachers/quiz/<id>/results/`)
- **인증**:
  - 로그인/로그아웃 (`/accounts/login/`, `/accounts/logout/`)
  - 학생 및 교사 회원가입 (`/accounts/signup/student/`, `/accounts/signup/teacher/`)

## 기술 스택
- **백엔드**: Django 2.0.1
- **의존성**: `django-crispy-forms==1.7.0`, `pytz==2017.3`
- **서버**: Python 3.6, SQLite
- **배포**: CentOS 8 클라우드 서버

## 설치 및 실행 (로컬)

### prerequisites
- Python 3.6 이상
- Git

### 단계
1. **저장소 클론**:
   ```
   git clone https://github.com/AndrewLee90/my-django-multi-user.git
   cd my-django-multi-user
가상환경 설정:

python3 -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
의존성 설치:

pip install -r requirements.txt
마이그레이션 적용:

python3 manage.py migrate
서버 실행:

python3 manage.py runserver
브라우저에서 http://127.0.0.1:8000/ 접속.
클라우드 서버 배포 (CentOS 8)
준비
서버 IP: 223.130.130.225
방화벽: firewalld 활성화 및 포트 8000 열기
단계
서버 접속:

ssh student@223.130.130.225
Python 3.6 설치 확인:

python3.6 --version  # 없으면 yum install python36
프로젝트 클론:

git clone https://github.com/AndrewLee90/my-django-multi-user.git
cd my-django-multi-user
가상환경 및 의존성:

python3.6 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
설정 수정:
django_school/settings.py:

ALLOWED_HOSTS = ['223.130.130.225', '127.0.0.1']
마이그레이션:

python3.6 manage.py migrate
방화벽 설정:

sudo systemctl start firewalld
sudo firewall-cmd --add-port=8000/tcp --permanent
sudo firewall-cmd --reload
서버 실행:

python3.6 manage.py runserver 0.0.0.0:8000
http://223.130.130.225:8000/ 접속.
주요 URL
/: 홈페이지
/students/: 학생 퀴즈 목록
/teachers/: 교사 퀴즈 관리
/accounts/login/: 로그인
/admin/: 관리자 페이지 (슈퍼유저 필요)
문제 해결
404 오류:
URL 확인: /catalog/는 없음, /로 접속.
캐시 지우기: 브라우저 설정에서 캐시 삭제.
접속 안 됨:
방화벽 확인: sudo firewall-cmd --list-ports.
서버 상태: netstat -tuln | grep 8000.
기여
버그 리포트나 개선 제안은 이슈에 남겨주세요.

라이선스
MIT License (원본 프로젝트 기반).

text

Collapse

Wrap

Copy

---

### 적용 방법
1. **로컬에서 편집**:
   - `README.md` 파일을 열고 위 내용을 붙여넣기.
   - 필요 시 세부 사항 수정 (예: 서버 IP, 사용자명).
   ```bash
   nano README.md
깃허브에 푸시:

git add README.md
git commit -m "Add project summary to README"
git push origin main
깃허브 확인:
https://github.com/AndrewLee90/my-django-multi-user에서 README.md 렌더링 확인.
커스터마이징 제안
프로젝트 설명: 당신이 추가한 기능(예: 전화번호 필드)이 있다면 "주요 기능"에 추가.
스크린샷: 홈페이지나 퀴즈 페이지 캡처를 추가.

