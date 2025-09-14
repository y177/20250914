# 📊 다중 소스 데이터 추출 설정 (Multi-Source Data Extraction)

## 🎯 **데이터 소스 분류**

### **1️⃣ 의료진 전용 사이트**
```bash
# 대한의사협회 (KMA)
claude --debug --print "Playwright로 대한의사협회 공지사항, 교육자료, 정책 변화를 수집하고 Sequential로 중요도 분류해줘"

# 식품의약품안전처 (KFDA)
claude --print "Context7에서 식약처 사이트 구조를 분석하고, Playwright로 의약품 허가정보, 안전성 정보를 수집해줘"

# 건강보험심사평가원 (HIRA)
claude --debug --print "Sequential로 심평원의 급여기준 변화를 체계적으로 추적하는 크롤링 전략을 수립해줘"
```

### **2️⃣ 학술/연구 데이터**
```bash
# PubMed 의학 논문
claude --print "Playwright를 사용해서 특정 키워드 '비만 치료', '당뇨 관리'의 최신 논문을 PubMed에서 수집해줘"

# Google Scholar 인용 정보
claude --debug --print "Context7에서 학술 검색 최적화 방법을 찾고, Google Scholar에서 영향력 있는 논문을 수집해줘"

# 코크란 리뷰 (Cochrane Reviews)
claude --print "Sequential로 코크란 리뷰의 체계적 문헌고찰을 추적하는 크롤링 시스템을 구축해줘"
```

### **3️⃣ 뉴스 & 트렌드 데이터**
```bash
# 의료 전문 뉴스
claude --debug --print "Playwright로 메디컬타임즈, 청년의사, 데일리메디 등에서 최신 의료 뉴스를 수집해줘"

# 해외 의료 뉴스
claude --print "Context7에서 해외 의료 뉴스 사이트를 찾고, 중요한 글로벌 트렌드를 수집해줘"

# 소셜미디어 트렌드
claude --debug --print "Sequential로 의료진 대상 소셜미디어 트렌드를 분석하는 전략을 수립해줘"
```

### **4️⃣ 약물 & 치료 정보**
```bash
# 약물 데이터베이스
claude --print "Playwright를 사용해서 Drugs.com, WebMD에서 약물 상호작용 정보를 수집해줘"

# 임상 가이드라인
claude --debug --print "Context7에서 국제 임상 가이드라인 사이트를 찾고, 최신 치료 지침을 수집해줘"

# 의료기기 정보
claude --print "Sequential로 FDA, CE 마크 의료기기 승인 정보를 추적하는 시스템을 구축해줘"
```

## 🔄 **소스별 크롤링 전략**

### **🏥 정부/공공기관 사이트**
```bash
# 안정적 구조, 정기 업데이트
claude --debug --print "Context7에서 공공 사이트 크롤링 모범 사례를 찾고, 안정적인 스케줄링을 설정해줘"

# robots.txt 준수
claude --print "Sequential로 각 공공기관의 크롤링 정책을 분석하고 준수 방안을 수립해줘"
```

### **📚 학술 데이터베이스**
```bash
# API 우선, 웹크롤링 보조
claude --debug --print "Context7에서 PubMed API 사용법을 찾고, Playwright와 결합한 하이브리드 수집 전략을 구현해줘"

# 인용 관계 추적
claude --print "Sequential을 사용해서 논문 간 인용 관계를 체계적으로 추적하고 네트워크를 구축해줘"
```

### **📰 뉴스 사이트**
```bash
# 실시간 모니터링
claude --debug --print "Playwright로 RSS 피드와 웹페이지를 동시에 모니터링하는 실시간 뉴스 수집 시스템을 구축해줘"

# 중복 제거
claude --print "Sequential로 여러 뉴스 소스에서 중복된 내용을 식별하고 정리하는 알고리즘을 구현해줘"
```

### **💊 상업적 사이트**
```bash
# Rate Limiting 엄격 준수
claude --debug --print "Context7에서 상업적 사이트의 크롤링 에티켓을 찾고, 안전한 수집 전략을 수립해줘"

# 데이터 검증 강화
claude --print "Sequential로 상업적 사이트에서 수집한 데이터의 신뢰성을 검증하는 체계를 구축해줘"
```

## 📋 **데이터 추출 템플릿**

### **뉴스 데이터 템플릿**
```json
{
  "title": "기사 제목",
  "content": "본문 내용",
  "author": "작성자",
  "publish_date": "발행일",
  "source": "출처",
  "category": "분류",
  "tags": ["키워드1", "키워드2"],
  "url": "원문 URL",
  "importance_score": 0.8,
  "collected_at": "수집 시간"
}
```

### **논문 데이터 템플릿**
```json
{
  "title": "논문 제목",
  "authors": ["저자1", "저자2"],
  "abstract": "초록",
  "journal": "저널명",
  "publish_date": "발행일",
  "pmid": "PubMed ID",
  "doi": "DOI",
  "keywords": ["키워드1", "키워드2"],
  "citation_count": 25,
  "impact_factor": 4.5,
  "study_type": "RCT",
  "collected_at": "수집 시간"
}
```

### **약물 정보 템플릿**
```json
{
  "drug_name": "약물명",
  "active_ingredient": "주성분",
  "indication": "적응증",
  "dosage": "용법용량",
  "contraindication": "금기사항",
  "side_effects": ["부작용1", "부작용2"],
  "drug_interaction": ["상호작용 약물"],
  "approval_date": "허가일",
  "manufacturer": "제조사",
  "price": "가격 정보",
  "collected_at": "수집 시간"
}
```

## 🔧 **소스별 추출 설정**

### **CSS 셀렉터 매핑**
```bash
# 대한의사협회 (KMA)
claude --debug --print "Playwright로 KMA 사이트 구조 분석: .notice-list .title, .content-body, .date-info 셀렉터 검증"

# 식약처 (KFDA)
claude --print "Context7에서 정부 사이트 표준 구조를 확인하고, Sequential로 안정적인 셀렉터 패턴 구축"

# 의료 뉴스 통합 셀렉터
claude --debug --print "Sequential로 메디컬타임즈, 청년의사, 데일리메디의 공통 HTML 구조 분석 후 범용 셀렉터 개발"
```

### **데이터 정규화 규칙**
```bash
# 한국형 날짜 처리 (YYYY.MM.DD, YYYY-MM-DD, MM/DD 등)
claude --debug --print "Context7에서 한국 사이트별 날짜 형식을 조사하고, Sequential로 ISO 8601 표준 변환 규칙 수립"

# 의료 전문용어 정제
claude --print "Playwright로 수집한 의료 텍스트에서 HTML 태그, 광고 제거 + 의료 용어 표준화 필터 구현"

# 한글 텍스트 최적화
claude --debug --print "Sequential로 한글 텍스트 정제: 불완전 문장 제거, 특수문자 정규화, 공백 표준화"
```

## 🗂️ **데이터 분류 체계**

### **중요도별 스마트 분류**
```bash
# 🚨 긴급 (즉시 알림) - AI 키워드 감지
claude --debug --print "Sequential로 '리콜', '부작용', '사망', '금지', '긴급' 키워드 + 패턴 매칭 알고리즘 구현"

# ⚠️ 중요 (일일 검토) - 의료진 관심사 기반
claude --print "Context7에서 의료진 필수 정보(수가 변경, 가이드라인 업데이트, 신약 정보) 기준 확립"

# ℹ️ 참고 (주간 정리) - 일반 의료 정보
claude --debug --print "Playwright 수집 데이터를 ML 기반으로 주제 클러스터링: 치료법, 연구, 정책, 교육"
```

### **의료 전문분야별 AI 분류**
```bash
# 🏥 진료과별 자동 태깅
claude --print "Sequential로 내과(순환기, 소화기), 외과(일반외과, 정형외과), 소아과 키워드 사전 구축"

# 🩺 질환별 ICD-10 매핑
claude --debug --print "Context7에서 WHO ICD-10 분류체계 확인 후, Sequential로 자동 질환 코딩 시스템 구축"

# 💊 치료 영역별 분류
claude --print "Sequential을 사용해서 진단-치료-예방-재활 단계별 정보 분류 및 태깅 자동화"
```

## ⏰ **실시간 모니터링 설정**

### **스마트 변화 감지 시스템**
```bash
# 🔍 웹페이지 변화 감지 (해시 기반)
claude --debug --print "Playwright로 핵심 콘텐츠 영역을 해시값으로 추적, 변화 시 즉시 알림 + 변경 내용 diff 분석"

# 🎯 의료진 맞춤형 키워드 알림
claude --print "Sequential로 개인화된 관심 키워드(전문분야, 병원, 연구 주제) 기반 실시간 알림 시스템 구축"

# 📊 트렌드 변화 감지
claude --debug --print "Context7에서 의료 트렌드 분석 방법을 찾고, 급상승 키워드/주제 자동 탐지 시스템 구현"
```

### **데이터 품질 자동 모니터링**
```bash
# ✅ 실시간 데이터 무결성 검증
claude --debug --print "Context7에서 의료 데이터 검증 표준을 확인하고, 필수 필드/형식 자동 검증 시스템 구축"

# 🚨 크롤링 실패 스마트 복구
claude --print "Sequential로 실패 패턴 분석: 네트워크 오류, 구조 변경, 차단 등 원인별 자동 복구 전략 실행"

# 📈 수집 성능 모니터링
claude --debug --print "Playwright 성능 메트릭 추적: 응답시간, 성공률, 데이터 품질 점수를 실시간 대시보드로 표시"
```