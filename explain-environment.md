# Claude Code 환경(Environment) 설명

## Claude Code 환경이란?

Claude Code의 **환경(Environment)**은 웹에서 Claude Code를 사용할 때 코드가 실행되는 **격리된 가상 머신(VM)**입니다. 각 세션은 자체 격리된 VM에서 실행됩니다.

## 기본 클라우드 환경 (anthropic cloud)

Anthropic이 관리하는 표준 VM으로, 다음이 미리 설치되어 있습니다:

- **언어**: Python, Node.js, Ruby, Go, Rust, Java, C++ 등
- **패키지 매니저**: npm, pip, yarn, poetry 등
- **데이터베이스**: PostgreSQL 16, Redis 7.0
- **도구**: Git, Docker, 빌드 도구, 테스트 프레임워크, 린터 등
- **네트워크**: 기본적으로 허용된 도메인(GitHub, npm, PyPI 등)만 접근 가능

## 새 환경 만들기

커스텀 환경을 생성하여 다음을 설정할 수 있습니다:

1. **환경 이름**: 사용자 정의 이름
2. **네트워크 접근 수준**: 제한적 / 전체 인터넷 / 인터넷 없음
3. **환경 변수**: `.env` 형식의 커스텀 키-값 쌍 (API 키 등)

## 보안 특징

- 세션 간 **완전한 격리**
- 모든 트래픽은 **보안 프록시**를 통과
- Git 자격 증명과 서명 키는 **샌드박스 내부에 노출되지 않음**
- GitHub 인증은 프록시를 통한 **범위 지정된 자격 증명** 사용
