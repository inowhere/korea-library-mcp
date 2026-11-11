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
