# 📖 Korea Public Library Book Finder MCP & API (그 책이 읽고 싶다 - 그책)

[![Live Web App](https://img.shields.io/badge/Live_App-thebook.wanttoread.workers.dev-2563eb?style=for-the-badge)](https://thebook.wanttoread.workers.dev)
[![MCP Ready](https://img.shields.io/badge/MCP-JSON--RPC_2.0-7e22ce?style=for-the-badge)](https://thebook.wanttoread.workers.dev/mcp)
[![OpenAPI 3.0](https://img.shields.io/badge/OpenAPI-3.0_Spec-10b981?style=for-the-badge)](https://thebook.wanttoread.workers.dev/openapi.json)

**Real-time book loan availability and public library search across 1,500+ public libraries in South Korea.**  
동네 도서관마다 앱을 켤 필요 없이, 전국 1,500개 이상 공공도서관의 실시간 도서 소장 및 대출 가능 여부를 1초 만에 조회하는 **웹앱(PWA) 및 AI 에이전트용 MCP / REST API** 서비스입니다.

---

## 🌐 1. Live Web App (웹 & 모바일 앱 바로가기)
누구나 무료로 즉시 도서관 대출 가능 여부를 검색할 수 있습니다.
* **공식 웹사이트 (PWA):** [https://thebook.wanttoread.workers.dev](https://thebook.wanttoread.workers.dev)

---

## 🤖 2. MCP (Model Context Protocol) 연동 안내
Claude, Cursor 및 다양한 AI 에이전트에서 한국 공공도서관 실시간 재고 조회 도구(`search_book_loan`)를 바로 사용할 수 있습니다.

* **Remote MCP Endpoint (JSON-RPC 2.0):**
  ```text
  https://thebook.wanttoread.workers.dev/mcp
OpenAPI 3.0 Specification (Custom GPTs / LangChain 등):
https://thebook.wanttoread.workers.dev/openapi.json
제공 도구 (Available Tool)
search_book_loan
title (string, required): 찾고자 하는 도서 제목 (예: "소년이 온다", "클린 코드")
region (string, optional): 검색할 지역명 (기본값: "서울 전체", 예: "서울 마포구", "서울 강남구", "경기 성남시", "부산 전체")
🔌 3. REST API 호출 예시 (JSON)
에이전트나 애플리케이션에서 HTTP GET 요청으로 즉시 JSON 데이터를 받아볼 수 있습니다.

Request
GET https://thebook.wanttoread.workers.dev/?title=소년이온다&region=서울 마포구&format=json
Response Example
{
  "is_live": true,
  "book": {
    "title": "소년이 온다 :한강 장편소설",
    "author": "한강 지음",
    "publisher": "창비",
    "isbn13": "9788936434120"
  },
  "region": "서울 마포구",
  "total_libraries": 15,
  "available_libraries": [
    {
      "name": "마포중앙도서관",
      "loan_available": true,
      "address": "서울특별시 마포구 성산로 128",
      "tel": "02-3153-5800",
      "operatingTime": "09:00~22:00",
      "closed": "매주 월요일",
      "homepage": "https://mplib.mapo.go.kr"
    }
  ]
}
✨ 주요 특징 (Key Features)
3단계 공공 API 원클릭 통합: 도서 ISBN 검색 ➔ 지역별 소장 도서관 조회 ➔ 도서관별 실시간 대출 가능 여부 병렬 확인을 단 1회의 호출로 처리합니다.
전국 주요 지역 지원: 서울 25개 전 자치구, 경기도 주요 시/구 및 전국 광역시·도 공공도서관을 지원합니다.
공식 홈페이지 및 도서 구매 연결: 각 도서관 공식 홈페이지 바로가기 및 대출 불가 시 온라인 서점(쿠팡, 교보문고, 예스24) 빠른 검색을 지원합니다.
