# 🕸️ 동적 데이터 크롤링 Sub-Agent (DataCrawler)

## 🎯 **전문 분야**
- 동적 웹사이트 데이터 수집
- JavaScript 렌더링 기반 크롤링
- 실시간 데이터 모니터링
- 멀티소스 데이터 통합
- 스케줄링 기반 자동 크롤링

## 🔧 **활용 MCP 서버**
- **Playwright**: 브라우저 자동화 & JavaScript 렌더링
- **Sequential**: 체계적 크롤링 전략 수립
- **Context7**: 웹 크롤링 모범 사례 검색
- **Desktop**: 로컬 데이터 저장 및 파일 관리
- **Notion**: 수집 데이터 구조화 및 대시보드

## 📋 **주요 기능**

### **🌐 동적 웹 크롤링**
```bash
# SPA(Single Page Application) 크롤링
claude --debug --print "Playwright로 React/Vue 기반 웹사이트에서 AJAX 데이터를 수집하고, Sequential로 체계적으로 분석해줘"

# 무한 스크롤 페이지 크롤링
claude --print "Playwright를 사용해서 무한 스크롤 페이지의 모든 데이터를 자동으로 수집해줘"

# 팝업/모달 처리 크롤링
claude --debug --print "Playwright로 팝업과 모달이 있는 웹사이트에서 데이터를 안전하게 수집해줘"
```

### **🎯 의료진 특화 크롤링**
```bash
# 의료 뉴스 수집
claude --print "Playwright로 주요 의료 뉴스 사이트에서 최신 소식을 수집하고, Sequential로 중요도에 따라 분류해줘"

# 약물 정보 업데이트
claude --debug --print "Context7에서 의약품 정보 사이트 크롤링 방법을 찾고, Playwright로 최신 약물 정보를 수집해줘"

# 학술 논문 메타데이터 수집
claude --print "Playwright를 사용해서 PubMed, Google Scholar에서 특정 주제의 논문 정보를 수집해줘"
```

### **📊 데이터 시각화 & 모니터링**
```bash
# 실시간 대시보드 생성
claude --debug --print "Playwright로 웹 데이터를 수집하고, Notion에 실시간 대시보드를 생성해줘"

# 트렌드 분석
claude --print "Sequential을 사용해서 수집된 데이터의 시간별 트렌드를 분석하고 패턴을 찾아줘"

# 데이터 품질 모니터링
claude --debug --print "Playwright로 수집한 데이터의 품질을 체크하고, 이상치를 탐지해줘"
```

## 🚀 **크롤링 전략 & 기법**

### **🔄 적응형 크롤링**
```bash
# 웹사이트 구조 변화 감지
claude --print "Sequential로 타겟 웹사이트의 구조 변화를 감지하고, 크롤링 전략을 자동 조정해줘"

# 동적 셀렉터 관리
claude --debug --print "Context7에서 안정적인 CSS 셀렉터 전략을 찾고, Playwright로 적용해줘"

# 로딩 시간 최적화
claude --print "Playwright의 네트워크 설정을 최적화해서 크롤링 속도를 향상시켜줘"
```

### **🛡️ 안전한 크롤링**
```bash
# Rate Limiting & 예의 바른 크롤링
claude --debug --print "Context7에서 크롤링 에티켓을 검색하고, Sequential로 안전한 크롤링 계획을 수립해줘"

# IP 차단 방지
claude --print "Playwright의 User-Agent와 헤더를 랜덤화해서 차단을 방지하는 크롤링을 설정해줘"

# 에러 처리 및 재시도
claude --debug --print "Sequential로 크롤링 실패 상황을 분석하고 자동 복구 전략을 구현해줘"
```

## 📅 **자동화 크롤링 스케줄**

### **실시간 모니터링 (매 10분)**
```bash
# 중요 사이트 변화 감지
claude --print "Playwright로 지정된 웹사이트들의 변화를 10분마다 모니터링하고 변경사항을 알려줘"
```

### **일일 데이터 수집 (매일 오전 6시)**
```bash
# 의료 뉴스 일일 수집
claude --debug --print "Sequential로 의료 뉴스 사이트 목록을 관리하고, Playwright로 일일 뉴스를 수집해서 Notion에 정리해줘"

# 약가 정보 업데이트
claude --print "Playwright를 사용해서 건강보험심사평가원에서 약가 변동 정보를 수집해줘"
```

### **주간 종합 분석 (매주 일요일)**
```bash
# 주간 트렌드 보고서
claude --debug --print "Sequential로 한 주간 수집된 데이터를 분석하고, 트렌드 보고서를 Notion에 생성해줘"

# 크롤링 성과 분석
claude --print "Desktop에 저장된 크롤링 로그를 분석하고, 성공률과 개선점을 도출해줘"
```

## 🎯 **타겟 사이트별 크롤링 전략**

### **의료진 전용 사이트**
```bash
# 대한의사협회 공지사항
claude --debug --print "Playwright로 대한의사협회 웹사이트에서 중요 공지사항을 수집하고 분류해줘"

# 식약처 안전성 정보
claude --print "Context7에서 식약처 사이트 구조를 분석하고, Playwright로 의약품 안전성 정보를 수집해줘"

# 건강보험심사평가원 정책 변화
claude --debug --print "Sequential로 심평원 정책 변화를 체계적으로 추적하는 크롤링 전략을 수립해줘"
```

### **학술/연구 사이트**
```bash
# PubMed 논문 메타데이터
claude --print "Playwright를 사용해서 특정 키워드의 최신 논문 정보를 PubMed에서 수집해줘"

# 의학 저널 TOC 모니터링
claude --debug --print "Sequential로 주요 의학 저널의 목차를 정기적으로 모니터링하는 시스템을 구축해줘"

# 임상시험 정보 수집
claude --print "Context7에서 임상시험 데이터베이스 크롤링 방법을 찾고, 관련 정보를 수집해줘"
```

## 📊 **데이터 처리 파이프라인**

### **🔍 데이터 전처리**
```bash
# HTML 파싱 및 정제
claude --debug --print "Playwright로 수집한 HTML 데이터를 정제하고, Sequential로 구조화해줘"

# 중복 제거 및 정규화
claude --print "Sequential을 사용해서 수집된 데이터에서 중복을 제거하고 표준화해줘"

# 데이터 검증
claude --debug --print "Context7에서 데이터 품질 체크 방법을 찾고, 수집된 데이터의 무결성을 검증해줘"
```

### **💾 데이터 저장 전략**
```bash
# 구조화된 저장
claude --print "Desktop을 사용해서 수집된 데이터를 JSON/CSV 형태로 체계적으로 저장해줘"

# Notion 데이터베이스 연동
claude --debug --print "수집된 데이터를 Notion 데이터베이스에 자동으로 입력하고 태그 분류해줢"

# 백업 및 버전 관리
claude --print "Sequential로 데이터 백업 전략을 수립하고, Desktop으로 자동 백업을 설정해줘"
```

## 🚨 **예외 상황 처리**

### **네트워크 문제**
```bash
# 연결 실패 대응
claude --debug --print "Playwright의 연결 실패 시 자동 재시도 및 대체 경로를 설정해줘"

# 타임아웃 처리
claude --print "Sequential로 타임아웃 상황별 대응 전략을 수립하고 적용해줘"
```

### **사이트 변경 대응**
```bash
# 구조 변경 감지
claude --debug --print "Context7에서 웹사이트 변경 감지 기법을 찾고, 자동 적응 시스템을 구축해줘"

# 셀렉터 업데이트
claude --print "Sequential을 사용해서 CSS 셀렉터 변경을 감지하고 자동 업데이트해줘"
```

## 📈 **성능 지표 및 모니터링**

### **크롤링 성과**
- **데이터 수집 성공률**: >95%
- **평균 응답 시간**: <3초
- **일일 수집량**: 설정 목표의 100%
- **데이터 품질 점수**: >90%

### **시스템 효율성**
- **메모리 사용량**: <500MB
- **CPU 사용률**: <30%
- **네트워크 대역폭**: 효율적 사용
- **스토리지 증가율**: 일일 <100MB

### **정기 보고서**
```bash
# 일일 크롤링 리포트
claude --debug --print "Sequential로 일일 크롤링 성과를 분석하고 요약 보고서를 생성해줘"

# 주간 데이터 품질 분석
claude --print "수집된 데이터의 품질을 분석하고, 개선이 필요한 영역을 식별해줘"

# 월간 트렌드 분석
claude --debug --print "Notion에 저장된 한 달간의 데이터를 분석하고 인사이트를 도출해줘"
```

## 🔧 **고급 크롤링 기능**

### **머신러닝 기반 최적화**
```bash
# 패턴 학습
claude --print "Sequential로 과거 크롤링 데이터를 분석하고 최적의 크롤링 패턴을 학습해줘"

# 예측 기반 스케줄링
claude --debug --print "Context7에서 예측 기반 크롤링 기법을 찾고, 효율적인 스케줄을 생성해줘"
```

### **다중 소스 통합**
```bash
# 크로스 플랫폼 데이터 수집
claude --print "Playwright로 여러 플랫폼에서 동시에 데이터를 수집하고 통합해줘"

# API + 웹크롤링 하이브리드
claude --debug --print "Sequential로 API와 웹크롤링을 결합한 최적의 데이터 수집 전략을 수립해줘"
```