# 로컬 프로젝트 MCP 서버 설치 가이드

**목표**: C:\Users\82103\projects 디렉토리에 로컬 MCP 서버 환경 구축
**요청 서버**: Context7 (--c7), Sequential (--seq), Playwright (--playwright) + 추가 권장 서버  
**설치 위치**: C:\Users\82103\projects\.claude\
**작성일**: 2025년 9월 14일

---

## 📋 설치 개요

### 🎯 설치할 MCP 서버들

#### 🔴 **필수 서버** (사용자 요청)
1. **context7** (`--c7`) - 라이브러리 문서화 및 패턴 검색
2. **sequential-thinking** (`--seq`) - 복잡한 순차적 사고 및 분석  
3. **playwright** (`--playwright`) - 브라우저 자동화 및 E2E 테스트

#### 🟡 **강력 권장 서버** (현재 PC에서 정상 작동 중)
4. **github-official** - GitHub API 통합
5. **desktop-automation** - 데스크톱 자동화
6. **notion-official** - Notion API 통합
7. **obsidian-mcp** - Obsidian 연동 (구글 드라이브 동기화)

---

## 🚀 1단계: 사전 준비 (기본 환경 설정)

### ✅ **1.1 Node.js 설치**
```bash
# 1. https://nodejs.org 에서 LTS 버전 다운로드 및 설치
# 2. PowerShell에서 확인
node --version
npm --version
```

### ✅ **1.2 Git 설치** (GitHub 서버용)
```bash
# 1. https://git-scm.com 에서 다운로드 및 설치
# 2. PowerShell에서 확인
git --version
```

### ✅ **1.3 Python 설치** (선택사항 - 일부 서버용)
```bash
# 1. https://python.org 에서 3.9+ 버전 설치
# 2. PowerShell에서 확인
python --version
```

---

## 🔧 2단계: Claude Code 설치

### ✅ **2.1 Claude Code 다운로드**
1. **공식 사이트**: https://claude.ai/code
2. **Windows 버전** 다운로드 및 설치
3. **첫 실행** 후 로그인

### ✅ **2.2 로컬 프로젝트 설정 디렉토리 생성**
```bash
# 로컬 프로젝트 설정 파일 위치 (수동 생성)
C:\Users\82103\projects\.claude\settings.json

# 디렉토리 생성
mkdir "C:\Users\82103\projects\.claude"
```

---

## 🎨 3단계: 핵심 MCP 서버 설치

### ✅ **3.1 Context7 설치** (`--c7`)
```bash
# PowerShell에서 실행
npx -y @upstash/context7-mcp
```

### ✅ **3.2 Sequential Thinking 설치** (`--seq`)
```bash
# PowerShell에서 실행
npx @modelcontextprotocol/server-sequential-thinking
```

### ✅ **3.3 Playwright 설치** (`--playwright`)
```bash
# PowerShell에서 실행
npx -y @playwright/mcp@latest

# Playwright 브라우저 설치 (필요시)
npx playwright install
```

---

## 🌟 4단계: 추가 권장 서버 설치

### ✅ **4.1 GitHub Official**
```bash
npx -y @modelcontextprotocol/server-github
```

### ✅ **4.2 Desktop Automation**
```bash
npx -y @wonderwhy-er/desktop-commander
```

### ✅ **4.3 Notion Official**
```bash
npx -y @makenotion/notion-mcp-server
```

### ✅ **4.4 Obsidian MCP**
```bash
npx -y obsidian-mcp-server
```

---

## ⚙️ 5단계: 설정 파일 구성

### ✅ **5.1 로컬 settings.json 파일 생성**
`C:\Users\82103\projects\.claude\settings.json` 파일에 다음 내용 추가:

```json
{
  "toolsTimeoutSeconds": 180,
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"]
    },
    "sequential-thinking": {
      "command": "npx",
      "args": ["@modelcontextprotocol/server-sequential-thinking"]
    },
    "playwright": {
      "command": "npx",
      "args": ["-y", "@playwright/mcp@latest"]
    },
    "github-official": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "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"
      }
    },
    "desktop-automation": {
      "command": "npx",
      "args": ["-y", "@wonderwhy-er/desktop-commander"]
    },
    "notion-official": {
      "command": "npx",
      "args": ["-y", "@makenotion/notion-mcp-server"],
      "env": {
        "NOTION_TOKEN": "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"
      }
    },
    "obsidian-mcp": {
      "command": "npx",
      "args": ["-y", "obsidian-mcp-server"],
      "env": {
        "OBSIDIAN_API_KEY": "b2c601c5cd1a6afc83900cf11fddb5cc6116409129d9786e8df8816fc3c8cb0b",
        "OBSIDIAN_BASE_URL": "https://127.0.0.1:27124",
        "OBSIDIAN_VERIFY_SSL": "false",
        "OBSIDIAN_ENABLE_CACHE": "true"
      }
    }
  },
  "mcpClient": {
    "enabled": true,
    "debug": true,
    "triggerKeywords": {
      "use context7": ["context7"]
    }
  }
}
```

---

## 🔑 6단계: API 키 및 환경 설정

### ✅ **6.1 GitHub API 키** (이미 설정됨)
- **키**: `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`
- **용도**: GitHub 저장소 관리, 이슈/PR 자동화

### ✅ **6.2 Notion API 키** (이미 설정됨)
- **키**: `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`
- **용도**: Notion 데이터베이스 및 페이지 관리

### ✅ **6.3 Obsidian 설정** (조건부)
**Obsidian이 설치되어 있고 구글 드라이브 동기화 사용 시:**

1. **Obsidian 설치**: https://obsidian.md
2. **구글 드라이브** 설치 및 동기화 설정
3. **볼트 열기**: `G:\내 드라이브\Obsidian Vault\` (구글 드라이브 동기화 폴더)
4. **Local REST API 플러그인** 설치:
   - Settings → Community plugins → Browse
   - "Local REST API" 검색 및 설치
   - 플러그인 활성화
5. **API 키 설정**:
   - 포트: 27124
   - HTTPS 사용
   - API 키: `b2c601c5cd1a6afc83900cf11fddb5cc6116409129d9786e8df8816fc3c8cb0b`

---

## ✅ 7단계: 테스트 및 검증

### ✅ **7.1 Claude Code 재시작**
1. Claude Code 완전 종료
2. 재실행
3. MCP 서버 연결 상태 확인

### ✅ **7.2 로컬 프로젝트에서 연결 테스트 (디버그 모드)**
```bash
# 프로젝트 디렉토리로 이동
cd "C:\Users\82103\projects"

# 각 서버별 테스트 명령어 (디버그 모드)
claude --mcp-debug --c7 "React 최신 패턴 알려줘"
claude --mcp-debug --seq "복잡한 문제 분석해줘"  
claude --mcp-debug --playwright "브라우저 테스트 실행해줘"
claude --mcp-debug --github "현재 저장소 상태 확인해줘"
claude --mcp-debug --notion "테스트 페이지 생성해줘"
claude --mcp-debug --obsidian "노트 검색해줘" (Obsidian 설치 시)

# 스트림 JSON 출력 테스트
claude --mcp-debug --output-format stream-json --c7 "테스트 실행"
```

### ✅ **7.3 성공 확인 지표**
- ✅ **모든 MCP 서버**: 연결 상태 "Connected"
- ✅ **플래그 작동**: `--c7`, `--seq`, `--playwright` 정상 동작
- ✅ **API 연동**: GitHub, Notion, Obsidian (설치 시) 정상 응답

---

## 📁 로컬 프로젝트 설정 가이드

### ✅ **방법 1: 로컬 설정 생성** (권장)

#### **1.1 현재 프로젝트에 설정 파일 생성**
```bash
# 로컬 프로젝트 설정 디렉토리
C:\Users\82103\projects\.claude\

# 설정 파일 생성
# 이미 생성됨: C:\Users\82103\projects\.claude\settings.json
```

#### **1.2 Claude Code 실행 시 로컬 설정 우선 사용**
```bash
# 프로젝트 디렉토리에서 Claude Code 실행
cd "C:\Users\82103\projects"
claude --mcp-debug

# Claude Code는 현재 디렉토리의 .claude/settings.json을 우선 사용
```

### ✅ **방법 2: 수동 설정** (단계별)

#### **2.1 빈 settings.json 생성**
프로젝트의 `C:\Users\82103\projects\.claude\settings.json` 파일 생성 (이미 완료)

#### **2.2 핵심 설정 입력** (요청된 서버만)
```json
{
  "toolsTimeoutSeconds": 180,
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"]
    },
    "sequential-thinking": {
      "command": "npx",
      "args": ["@modelcontextprotocol/server-sequential-thinking"]
    },
    "playwright": {
      "command": "npx",
      "args": ["-y", "@playwright/mcp@latest"]
    }
  },
  "mcpClient": {
    "enabled": true,
    "debug": true
  }
}
```

#### **2.3 추가 서버 설정** (권장)
위 기본 설정에 다음 서버들 추가:
```json
{
  "github-official": {
    "command": "npx",
    "args": ["-y", "@modelcontextprotocol/server-github"],
    "env": {
      "GITHUB_PERSONAL_ACCESS_TOKEN": "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"
    }
  },
  "desktop-automation": {
    "command": "npx",
    "args": ["-y", "@wonderwhy-er/desktop-commander"]
  },
  "notion-official": {
    "command": "npx",
    "args": ["-y", "@makenotion/notion-mcp-server"],
    "env": {
      "NOTION_TOKEN": "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"
    }
  }
}
```

### 🔑 **API 키 사용 가이드**

#### **✅ 동일 사용 가능한 API 키들**
- **GitHub**: `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`
  - 개인 토큰이므로 여러 기기에서 동시 사용 가능
- **Notion**: `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`
  - Workspace 통합이므로 여러 기기에서 동시 사용 가능

#### **⚠️ 주의가 필요한 API 키들**
- **Obsidian**: `b2c601c5cd1a6afc83900cf11fddb5cc6116409129d9786e8df8816fc3c8cb0b`
  - 새 노트북에서 Obsidian 설치 후 **새 API 키 생성 권장**
  - 또는 동일한 구글 드라이브 계정으로 동기화하면 동일 키 사용 가능

### 🛡️ **보안 고려사항**

#### **권장 보안 조치**
1. **API 키 분리**: 민감한 서비스는 노트북용 별도 키 생성
2. **권한 제한**: GitHub 토큰은 필요한 권한만 부여
3. **정기 갱신**: API 키 주기적 업데이트

#### **백업 전략**
```bash
# 1. 설정 파일 백업
copy "C:\Users\[사용자명]\.claude\settings.json" "클라우드폴더\claude_backup_YYYYMMDD.json"

# 2. API 키 별도 저장 (암호화된 파일)
# 패스워드 매니저나 안전한 클라우드 저장소 활용
```

---

## 🚨 문제 해결 가이드

### ❌ **Node.js 관련 오류**
```bash
# Node.js 버전 확인 및 업데이트
node --version  # 18.0+ 권장
npm install -g npm@latest
```

### ❌ **MCP 서버 연결 실패**
```bash
# 캐시 정리 후 재설치
npm cache clean --force
npx -y @upstash/context7-mcp  # 각 서버별 재설치
```

### ❌ **Obsidian 연결 실패**
1. **플러그인 재설치**: Local REST API 플러그인 제거 후 재설치
2. **포트 확인**: 27124 포트 사용 중인지 확인
3. **API 키 재생성**: Obsidian에서 새 API 키 생성

### ❌ **권한 오류**
```bash
# PowerShell 관리자 권한으로 실행
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### ❌ **설정 파일 형식 오류**
```bash
# JSON 형식 검증 사이트에서 확인
# https://jsonlint.com/

# 또는 PowerShell에서 검증
Get-Content "C:\Users\[사용자명]\.claude\settings.json" | ConvertFrom-Json
```

### ❌ **구글 드라이브 동기화 문제**
```bash
# 1. 구글 드라이브 재시작
taskkill /f /im GoogleDriveFS.exe
# Google Drive 앱 재실행

# 2. 볼트 경로 확인
# Obsidian에서 "다른 볼트 열기" → G:\내 드라이브\Obsidian Vault 선택
```

---

## 🔍 완전한 설치 검증 가이드

### ✅ **1단계: 기본 환경 검증**
```powershell
# 필수 도구 버전 확인
Write-Host "=== 기본 환경 검증 ===" -ForegroundColor Green
node --version
npm --version
git --version
python --version  # 선택사항

# Claude Code 실행 여부 확인
Get-Process | Where-Object {$_.ProcessName -like "*Claude*"}
```

### ✅ **2단계: MCP 서버 설치 검증**
```powershell
Write-Host "=== MCP 서버 설치 검증 ===" -ForegroundColor Green

# 핵심 서버 설치 확인
npx -y @upstash/context7-mcp --version 2>$null
if ($LASTEXITCODE -eq 0) { Write-Host "✅ Context7 설치됨" } else { Write-Host "❌ Context7 설치 필요" }

npx @modelcontextprotocol/server-sequential-thinking --version 2>$null  
if ($LASTEXITCODE -eq 0) { Write-Host "✅ Sequential 설치됨" } else { Write-Host "❌ Sequential 설치 필요" }

npx -y @playwright/mcp@latest --version 2>$null
if ($LASTEXITCODE -eq 0) { Write-Host "✅ Playwright 설치됨" } else { Write-Host "❌ Playwright 설치 필요" }
```

### ✅ **3단계: 설정 파일 검증**
```powershell
Write-Host "=== 설정 파일 검증 ===" -ForegroundColor Green

$settingsPath = "$env:USERPROFILE\.claude\settings.json"
if (Test-Path $settingsPath) {
    Write-Host "✅ settings.json 파일 존재"
    
    # JSON 형식 검증
    try {
        $settings = Get-Content $settingsPath | ConvertFrom-Json
        Write-Host "✅ JSON 형식 유효"
        
        # 필수 서버 설정 확인
        if ($settings.mcpServers."context7") { Write-Host "✅ Context7 설정됨" }
        if ($settings.mcpServers."sequential-thinking") { Write-Host "✅ Sequential 설정됨" }
        if ($settings.mcpServers."playwright") { Write-Host "✅ Playwright 설정됨" }
        
    } catch {
        Write-Host "❌ JSON 형식 오류: $($_.Exception.Message)" -ForegroundColor Red
    }
} else {
    Write-Host "❌ settings.json 파일 없음" -ForegroundColor Red
}
```

### ✅ **4단계: 연결 상태 검증**
```powershell
Write-Host "=== Claude Code 연결 검증 ===" -ForegroundColor Green

# Claude Code 프로세스 확인
$claudeProcess = Get-Process | Where-Object {$_.ProcessName -like "*Claude*"}
if ($claudeProcess) {
    Write-Host "✅ Claude Code 실행 중 (PID: $($claudeProcess.Id))"
} else {
    Write-Host "❌ Claude Code 실행되지 않음" -ForegroundColor Red
}

Write-Host "=== 수동 테스트 명령어 ===" -ForegroundColor Yellow
Write-Host "Claude Code에서 다음 명령어들을 테스트하세요:"
Write-Host "claude --c7 'React 최신 패턴 알려줘'"
Write-Host "claude --seq '복잡한 문제 분석해줘'"
Write-Host "claude --playwright '브라우저 테스트 실행해줘'"
```

### ✅ **5단계: Obsidian 연동 검증** (선택사항)
```powershell
Write-Host "=== Obsidian 연동 검증 ===" -ForegroundColor Green

# Obsidian 프로세스 확인
$obsidianProcess = Get-Process | Where-Object {$_.ProcessName -like "*Obsidian*"}
if ($obsidianProcess) {
    Write-Host "✅ Obsidian 실행 중"
} else {
    Write-Host "⚠️ Obsidian 실행되지 않음" -ForegroundColor Yellow
}

# 구글 드라이브 동기화 확인
$driveProcess = Get-Process | Where-Object {$_.ProcessName -like "*GoogleDriveFS*"}
if ($driveProcess) {
    Write-Host "✅ Google Drive 동기화 중"
} else {
    Write-Host "⚠️ Google Drive 동기화 안됨" -ForegroundColor Yellow
}

# 볼트 폴더 확인
if (Test-Path "G:\내 드라이브\Obsidian Vault") {
    Write-Host "✅ Obsidian Vault 폴더 존재 (G: 드라이브)"
} elseif (Test-Path "C:\Users\$env:USERNAME\Google Drive\내 드라이브\Obsidian Vault") {
    Write-Host "✅ Obsidian Vault 폴더 존재 (C: 드라이브)"
} else {
    Write-Host "⚠️ Obsidian Vault 폴더 찾을 수 없음" -ForegroundColor Yellow
}
```

### 📊 **성능 모니터링**
```powershell
Write-Host "=== 성능 모니터링 ===" -ForegroundColor Green

# 메모리 사용량 확인
$claudeMemory = (Get-Process | Where-Object {$_.ProcessName -like "*Claude*"} | Measure-Object WorkingSet -Sum).Sum / 1MB
Write-Host "Claude Code 메모리 사용량: $([math]::Round($claudeMemory, 2)) MB"

# 네트워크 연결 확인 (Obsidian API)
try {
    $response = Invoke-WebRequest -Uri "https://localhost:27124/" -Headers @{"Authorization"="Bearer b2c601c5cd1a6afc83900cf11fddb5cc6116409129d9786e8df8816fc3c8cb0b"} -SkipCertificateCheck -TimeoutSec 5
    Write-Host "✅ Obsidian API 연결 성공"
} catch {
    Write-Host "⚠️ Obsidian API 연결 실패 (정상 - Obsidian 미설치시)" -ForegroundColor Yellow
}
```

### 🎯 **최종 완료 체크리스트**
```powershell
Write-Host "=== 최종 완료 체크리스트 ===" -ForegroundColor Green
Write-Host "수동으로 확인하세요:"
Write-Host "[ ] Claude Code 정상 실행"
Write-Host "[ ] --c7 플래그 작동 (context7)"
Write-Host "[ ] --seq 플래그 작동 (sequential)"  
Write-Host "[ ] --playwright 플래그 작동"
Write-Host "[ ] GitHub 연동 작동 (선택)"
Write-Host "[ ] Notion 연동 작동 (선택)"
Write-Host "[ ] Obsidian 연동 작동 (선택)"
Write-Host "[ ] 모든 MCP 서버 Connected 상태"
```

---

## 🎯 추가 최적화 (선택사항)

### 🔄 **자동 업데이트 스크립트**
```powershell
# update_mcp_servers.ps1
npx -y @upstash/context7-mcp@latest
npx @modelcontextprotocol/server-sequential-thinking@latest  
npx -y @playwright/mcp@latest
npx -y @modelcontextprotocol/server-github@latest
npx -y @wonderwhy-er/desktop-commander@latest
npx -y @makenotion/notion-mcp-server@latest
npx -y obsidian-mcp-server@latest
```

### 📊 **성능 모니터링**
```bash
# Claude Code 로그 확인
# Windows: %APPDATA%\Claude Code\logs\
```

---

## 📝 체크리스트

### 🔴 **필수 설치 (사용자 요청)**
- [ ] Context7 (`--c7`)
- [ ] Sequential Thinking (`--seq`)  
- [ ] Playwright (`--playwright`)

### 🟡 **권장 설치**
- [ ] GitHub Official
- [ ] Desktop Automation
- [ ] Notion Official
- [ ] Obsidian MCP (선택)

### ⚙️ **설정 및 테스트**
- [ ] settings.json 구성
- [ ] API 키 설정
- [ ] 연결 테스트 완료
- [ ] 플래그 동작 확인

---

**완료 시 현재 PC와 동일한 Claude Code + MCP 서버 환경이 집 노트북에 구축됩니다!** 🎉

**예상 설치 시간**: 30-60분 (Obsidian 포함 시 +30분)