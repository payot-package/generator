# kiosk-password

TypeScript 기반 npm 패키지 프로젝트입니다.

## 설치

```bash
npm install kiosk-password
```

## 사용법

```typescript
import { hello } from 'kiosk-password';

console.log(hello()); // Hello, world!
```

## 테스트

```bash
npm test
```
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:payot-package/generator.git
git push -u origin main
````mdc

## 여러 GitHub 계정에서 SSH로 push하는 방법

### 1. 계정별 SSH 키 생성
```bash
# 예시: 새로운 키 생성 (이메일은 해당 계정의 이메일로)
ssh-keygen -t ed25519 -C "your-email@example.com"
# 경로 예시: ~/.ssh/id_ed25519_github_account2
```

### 2. SSH 공개키를 해당 GitHub 계정에 등록
- GitHub > Settings > SSH and GPG keys > New SSH key
- 위에서 생성한 공개키(~/.ssh/id_ed25519_github_account2.pub) 내용을 등록

### 3. SSH config 파일 설정
`~/.ssh/config` 파일에 아래와 같이 추가:
```bash
Host github-account2
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_github_account2
```

### 4. 원격 저장소 주소를 config의 Host로 변경
```bash
git remote set-url origin git@github-account2:payot-package/generator.git
```

이제 해당 저장소는 두 번째 계정의 SSH 키로 인증되어 push됩니다.

### 5. SSH 연결 테스트
```bash
ssh -T git@github-account2
```

---