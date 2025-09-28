---
name: compliance-keyword-scanner
status: backlog
created: 2025-09-28T15:26:04Z
updated: 2025-09-28T15:28:01Z
progress: 0%
prd: .claude/prds/compliance-keyword-scanner.md
github: https://github.com/bluejazz822/compliance-keyword-scanner/issues/1
---

# Epic: compliance-keyword-scanner

## Overview

Build a web-based compliance monitoring system that automatically discovers website sitemaps and performs comprehensive keyword searches across all pages. The system uses a Node.js backend with background job processing, a React frontend for user interaction, and PostgreSQL for data persistence. Key technical focus on efficient web crawling, pattern matching, and report generation for on-premise deployment.

## Architecture Decisions

- **Backend Framework**: Node.js with Express for rapid development and excellent crawling library ecosystem
- **Frontend**: React with modern hooks for responsive UI and real-time progress updates
- **Database**: PostgreSQL for robust relational data storage and efficient querying of scan results
- **Queue System**: Redis with Bull.js for reliable background job processing and concurrent scan management
- **Web Crawling**: Playwright for reliable HTML content extraction (handles modern websites better than basic HTTP requests)
- **Pattern Matching**: Native JavaScript regex engine for keyword searches with custom context extraction
- **Report Generation**: Puppeteer for PDF generation from HTML templates
- **Deployment**: Docker containers for consistent on-premise deployment

## Technical Approach

### Frontend Components
- **Scan Configuration Form**: Domain input, keyword/regex pattern entry, scan options
- **Progress Dashboard**: Real-time scan status, progress bars, queue position
- **Results Viewer**: Filterable table with keyword matches, context snippets, page URLs
- **Report Generator**: PDF download interface with customization options

### Backend Services
- **Scan Management API**: CRUD operations for scan configurations and status
- **Crawler Service**: Sitemap discovery, URL extraction, page content fetching
- **Search Engine**: Multi-pattern keyword matching with context extraction
- **Report Service**: PDF generation, result export, historical data access
- **Queue Manager**: Background job scheduling, progress tracking, error handling

### Infrastructure
- **Database Schema**: Scans, pages, matches, reports tables with proper indexing
- **File Storage**: Local filesystem for sitemap.xml files and generated PDFs
- **Monitoring**: Application logs, job queue metrics, scan performance tracking
- **Resource Management**: Configurable limits on concurrent scans and memory usage

## Implementation Strategy

**Development Approach**: Build MVP with core functionality first, then add advanced features iteratively
**Risk Mitigation**: Implement robust error handling for network issues and malformed websites
**Testing Strategy**: Unit tests for pattern matching, integration tests for crawling, end-to-end tests for complete workflows

## Task Breakdown Preview

High-level task categories that will be created:
- [ ] **Database & Models**: PostgreSQL schema, Sequelize models, seed data
- [ ] **Web Crawler Engine**: Sitemap discovery, page extraction, content fetching
- [ ] **Keyword Search Engine**: Pattern matching, context extraction, result ranking
- [ ] **Background Job System**: Redis queue, worker processes, progress tracking
- [ ] **REST API Backend**: Express routes, validation, error handling
- [ ] **React Frontend**: Components, state management, real-time updates
- [ ] **Report Generation**: PDF templates, export functionality
- [ ] **Deployment & Configuration**: Docker setup, environment config, documentation

## Dependencies

**External Dependencies**:
- Network connectivity for website crawling
- On-premise infrastructure with adequate CPU/memory for concurrent scans
- PostgreSQL and Redis instances

**Internal Dependencies**:
- DevOps team for server setup and deployment pipeline
- Security team approval for web crawling activities
- Compliance team input on keyword patterns and reporting requirements

**Technical Prerequisites**:
- Node.js runtime environment
- Docker for containerized deployment
- SSL certificates for secure on-premise hosting

## Success Criteria (Technical)

**Performance Benchmarks**:
- Scan 1000 pages within 30 minutes
- Support 10 concurrent domain scans
- Generate PDF reports within 5 minutes
- 99% keyword matching accuracy

**Quality Gates**:
- 95% test coverage for core search functionality
- Zero memory leaks during extended crawling sessions
- Graceful degradation when target sites are unreachable
- Comprehensive error logging and recovery mechanisms

**Acceptance Criteria**:
- Complete sitemap generation for 95% of tested domains
- Support exact, partial, and regex pattern matching
- Background processing with real-time progress updates
- PDF reports with contextual keyword highlights

## Estimated Effort

**Overall Timeline**: 8-10 weeks for full implementation
**Resource Requirements**: 2-3 full-stack developers, 1 DevOps engineer
**Critical Path Items**:
1. Web crawler engine (3 weeks)
2. Keyword search implementation (2 weeks)
3. Frontend development (2-3 weeks)
4. Integration and testing (2 weeks)

**Phase Distribution**:
- Phase 1 (MVP): 6 weeks - Core scanning and basic reporting
- Phase 2: 2 weeks - Advanced patterns and PDF generation
- Phase 3: 2 weeks - Performance optimization and deployment

## Tasks Created
- [ ] #2 - Project Setup and Database Schema (parallel: true)
- [ ] #3 - Web Crawler Engine Core (parallel: true)
- [ ] #4 - Keyword Search Engine (parallel: true)
- [ ] #5 - Background Job System (parallel: true)
- [ ] #6 - REST API Backend (parallel: true)
- [ ] #7 - Report Generation Service (parallel: true)
- [ ] #48 - React Frontend Application (parallel: true)
- [ ] #49 - Testing and Quality Assurance (parallel: false)
- [ ] #50 - Deployment and Documentation (parallel: true)

Total tasks: 9
Parallel tasks: 8
Sequential tasks: 1
Estimated total effort: 192-234 hours