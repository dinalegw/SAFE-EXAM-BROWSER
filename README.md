# SAFE-EXAM-BROWSER

> A secure, proctored online examination platform that ensures academic integrity through automated monitoring and cheating detection.

## ?? Overview

SAFE-EXAM-BROWSER is a web-based assessment platform designed for educational institutions to conduct exams online without human proctors. The system actively monitors student behavior during exams and flags potential cheating attempts, ensuring fairness and maintaining academic standards.

## ? Key Features

### ?? Academic Integrity Monitoring
- **Tab/Window Switching Detection** � Alerts when students navigate away from the exam tab
- **Screen Sharing Detection** � Identifies if the exam window is being shared via remote desktop tools
- **Clipboard Monitoring** � Detects and prevents copy-paste actions during exams
- **Multi-Tab Prevention** � Restricts opening additional browser tabs or windows
- **Fullscreen Enforcement** � Requires exams to be taken in fullscreen mode

### ????? Teacher/Instructor Dashboard
- **Exam Creation** � Build quizzes, tests, and assessments with various question types
- **Question Bank** � Reusable question library with categorization and tagging
- **Student Management** � Enroll students and assign exams
- **Live Monitoring** � Real-time view of student progress and flagged activities
- **Analytics & Reports** � Detailed performance metrics and integrity scores

### ????? Student Experience
- **Clean Interface** � Distraction-free exam environment
- **Question Navigation** � Move between questions, mark for review
- **Timer Display** � Clear countdown for time-limited exams
- **Answer Autosave** � Periodic saving to prevent data loss
- **Flag Summary** � View all flagged incidents post-exam

### ??? Security & Privacy
- **Browser Lockdown** � Limited browser functionality during exams
- **No Human Proctoring** � Fully automated monitoring reduces bias and cost
- **Encrypted Sessions** � Secure data transmission and storage
- **GDPR Compliant** � Student data handled with privacy in mind

## ?? Getting Started

### Prerequisites
- Node.js 18+ / Python 3.10+ (depending on backend choice)
- Modern web browser (Chrome, Firefox, Edge)
- HTTPS-enabled environment (required for monitoring APIs)

### Installation

1. **Clone the repository**
   `ash
   git clone https://github.com/yourusername/SAFE-EXAM-BROWSER.git
   cd SAFE-EXAM-BROWSER
   `

2. **Install dependencies**
   `ash
   # Backend
   cd backend
   npm install  # or pip install -r requirements.txt

   # Frontend
   cd ../frontend
   npm install
   `

3. **Configure environment**
   `ash
   cp .env.example .env
   # Edit .env with your database credentials, JWT secrets, etc.
   `

4. **Run the application**
   `ash
   # Development mode
   npm run dev
   `

5. **Open in browser**
   `
   http://localhost:3000
   `

### Docker Setup (Alternative)
`ash
docker-compose up -d
`

## ??? Project Structure

`
SAFE-EXAM-BROWSER/
+-- backend/           # Server-side logic and APIs
�   +-- controllers/   # Request handlers
�   +-- models/        # Database schemas
�   +-- routes/        # API endpoints
�   +-- services/      # Business logic (proctoring engine)
+-- frontend/          # Client-side application
�   +-- public/        # Static assets
�   +-- src/
�   �   +-- components/# UI components
�   �   +-- pages/     # Page views
�   �   +-- hooks/     # Custom React hooks
�   �   +-- utils/     # Helper functions
+-- shared/            # Types and constants used by both ends
+-- docs/              # Additional documentation
+-- tests/             # Test suites
`

## ?? How It Works

1. **Setup** � Teachers create exams and assign them to students
2. **Launch** � Students receive a link to begin the exam
3. **Monitor** � The system tracks:
   - Visibility changes (tab switches, window minimize)
   - Clipboard operations (copy/cut/paste)
   - Screen capture attempts
   - Fullscreen status
   - Mouse/keyboard activity patterns
4. **Flag** � Suspicious activities are logged and flagged for instructor review
5. **Review** � Instructors examine flagged incidents and finalize grades

## ?? Configuration

### Exam Settings
- Time limits (per question or overall)
- Allowed devices (desktop only, no mobile)
- Browser requirements (Chromium-based)
- Cheating sensitivity thresholds
- Post-exam report generation

### Monitoring Granularity
- **Strict** � Any deviation terminates the exam
- **Moderate** � Violations are logged; exam continues
- **Lenient** � Only critical breaches trigger flags

## ?? Cheating Detection Mechanisms

| Behavior | Detection Method | Action |
|----------|-----------------|--------|
| Tab switching | Page Visibility API | Flag + log timestamp |
| Window minimize | Window blur events | Flag + optional terminate |
| Copy/Paste | Clipboard event listeners | Flag + block clipboard |
| Screen sharing | Screen Capture API checks | Immediate termination |
| Right-click context menu | Event override | Disabled |
| External apps (ALT+TAB) | Keyboard shortcuts blocked | Prevention |
| Multiple monitors | Screen enumeration | Warn/block |

## ?? Documentation

Detailed documentation available in the /docs folder:
- API.md � REST and WebSocket API reference
- DEPLOYMENT.md � Production deployment guide
- SECURITY.md � Security architecture and best practices
- TROUBLESHOOTING.md � Common issues and solutions

## ?? Contributing

We welcome contributions from developers, educators, and security researchers.

1. Fork the repository
2. Create a feature branch (git checkout -b feature/amazing-feature)
3. Commit your changes (git commit -m 'Add amazing feature')
4. Push to the branch (git push origin feature/amazing-feature)
5. Open a Pull Request

Please read CONTRIBUTING.md for detailed guidelines.

## ?? Testing

`ash
# Run all tests
npm test

# Backend unit tests
cd backend && npm test

# Frontend component tests
cd frontend && npm test

# E2E tests
npm run test:e2e
`

## ?? License

This project is licensed under the MIT License � see the [LICENSE](LICENSE) file for details.

## ?? Acknowledgements

- Built for educators, by educators
- Inspired by the need for flexible, trustworthy online assessment
- Special thanks to the open-source community for the incredible tools

## ?? Support

For questions, bug reports, or feature requests, please [open an issue](https://github.com/yourusername/SAFE-EXAM-BROWSER/issues).

---

**Maintain academic integrity, one exam at a time.** ??
