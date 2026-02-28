# Khung tư duy (framework) để A.I làm trợ lý cá nhân

Dưới đây là **khung tư duy dành riêng cho Golang Developer** sử dụng AI như công cụ hỗ trợ phát triển phần mềm (AI-assisted development), không phải tích hợp AI vào sản phẩm:

---

## 🧠 Framework: **A.I.D.E** (AI-assisted Development for Engineers)

```
┌─────────────────────────────────────────────────────────────┐
│                    A.I.D.E Framework                        │
├─────────────────────────────────────────────────────────────┤
│  A: Augmentation    → AI tăng cường, không thay thế         │
│  I: Integration     → Tích hợp AI vào workflow hiện tại     │
│  D: Discipline      → Kỷ luật code review & validation      │
│  E: Evolution       → Liên tục cải tiến prompt & workflow   │
└─────────────────────────────────────────────────────────────┘
```

---

## 📋 1. Mindset Foundation

### ✅ Nguyên tắc cốt lõi
| Mindset Sai | Mindset Đúng |
|-------------|--------------|
| "AI sẽ code thay mình" | "AI là pair programmer thông minh" |
| Copy-paste trực tiếp | Review → Understand → Adapt → Test |
| Prompt ngẫu nhiên | Prompt có cấu trúc, reproducible |
| AI làm mọi thứ | AI làm phần boilerplate, mình tập trung vào business logic |

### 🎯 Vai trò của Developer khi có AI
```
Developer = Architect + Reviewer + Integrator + Tester
AI = Code Generator + Documentation Writer + Bug Finder
```

---

## 🛠️ 2. AI Integration Points trong Golang Workflow

### 📁 **Project Setup & Scaffolding**
```bash
# Prompt mẫu:
"Generate a Go project structure for a REST API with:
- Go modules
- Dockerfile
- Makefile with test/build commands
- .gitignore
- config package
- Using Gin framework"
```

**Tools**: GitHub Copilot, Cursor, Claude 3.5

---

### 💻 **Boilerplate Code Generation**

| Use Case | Prompt Pattern |
|----------|----------------|
| Struct + JSON tags | "Generate Go struct for User with fields: ID, Name, Email, CreatedAt. Add JSON tags and validation tags." |
| HTTP handler | "Write Gin handler for POST /users that validates input and calls service layer" |
| Database model | "Generate GORM model for Order with relationships to User and Product" |
| Unit test | "Write table-driven tests for function CalculateDiscount(price float64, isVIP bool)" |

---

### 🧪 **Testing & Test Data**
```go
// Prompt:
"Generate table-driven tests for this function:
func ParseDuration(input string) (time.Duration, error)"

// Output: AI tạo test cases cho edge cases:
// - "1h30m", "0", invalid formats, boundary values
```

---

### 📝 **Documentation & Comments**
```go
// Prompt:
"Write godoc comment for this interface:
type PaymentProcessor interface {
    Process(amount int64) error
    Refund(txID string) error
}"
```

---

### 🐛 **Debugging & Code Explanation**
```
Prompt: "Explain this Go code and suggest improvements:
[...paste code...]"

Hoặc: "Why does this panic? [paste error + code]"
```

---

### 🔧 **Refactoring & Code Review**
```
Prompt: "Refactor this Go function to:
- Reduce cyclomatic complexity
- Follow Go best practices
- Add proper error handling
[code...]"
```

---

## 📝 3. Prompt Engineering Framework cho Golang

### 🎨 **Cấu trúc Prompt Hiệu Quả (CRISP)**

```
C - Context: "I'm building a Go microservice using Gin and GORM..."
R - Role: "Act as a senior Go developer with 10 years experience..."
I - Instructions: "Generate a middleware that logs request/response..."
S - Specifications:
    - Use context.Context properly
    - Follow Go idioms
    - Include error handling
    - Add comments
P - Pattern/Example: "Similar to this pattern: [paste example]"
```

### 💡 **Prompt Templates theo Use Case**

| Use Case | Template |
|----------|----------|
| Generate code | "Write idiomatic Go code for [task]. Follow these rules: [list]. Output only code." |
| Explain code | "Explain this Go code line by line. Highlight potential issues." |
| Fix bug | "This Go code has [error]. Fix it and explain the root cause." |
| Optimize | "Optimize this Go function for performance. Show before/after." |
| Review | "Review this Go code for: error handling, naming, Go best practices." |

---

## 🔄 4. Workflow Integration

### 📊 **Typical AI-Assisted Development Flow**

```
┌─────────────────┐
│   Define Task   │
└────────┬────────┘
         │
         ▼
┌─────────────────────────────────────┐
│  Prompt AI → Generate Code Snippet  │
│  (with specific context & rules)    │
└────────┬────────────────────────────┘
         │
         ▼
┌─────────────────────────────────────┐
│  Review & Understand Generated Code │
│  - Does it follow Go idioms?        │
│  - Proper error handling?           │
│  - Context cancellation?            │
└────────┬────────────────────────────┘
         │
         ▼
┌─────────────────────────────────────┐
│  Adapt & Integrate                  │
│  - Modify to fit project structure  │
│  - Add project-specific logic       │
└────────┬────────────────────────────┘
         │
         ▼
┌─────────────────────────────────────┐
│  Test Thoroughly                    │
│  - Unit tests                       │
│  - Integration tests                │
│  - Edge cases                       │
└────────┬────────────────────────────┘
         │
         ▼
┌─────────────────────────────────────┐
│  Commit with Clear Message          │
│  (Document AI assistance if needed) │
└─────────────────────────────────────┘
```

---

## ⚠️ 5. Discipline & Guardrails

### 🔒 **Code Review Checklist cho AI-Generated Code**

```markdown
## Golang AI Code Review Checklist

### ✅ Correctness
- [ ] Code compiles without errors
- [ ] Handles errors properly (no ignored errors)
- [ ] Context is passed correctly (context.Context)
- [ ] No nil pointer dereferences

### ✅ Go Idioms
- [ ] Follows Effective Go guidelines
- [ ] Proper naming (PascalCase, camelCase)
- [ ] Uses gofmt/golangci-lint compatible style
- [ ] Avoids unnecessary type assertions

### ✅ Concurrency Safety
- [ ] Goroutines have proper lifecycle management
- [ ] Channels are closed appropriately
- [ ] Mutex usage is correct (no deadlocks)
- [ ] Context cancellation is respected

### ✅ Security
- [ ] No hardcoded secrets
- [ ] SQL injection prevention (use parameterized queries)
- [ ] Input validation present
- [ ] No unsafe package unless justified

### ✅ Performance
- [ ] No unnecessary allocations in hot paths
- [ ] Proper use of sync.Pool if applicable
- [ ] Efficient data structures chosen

### ✅ Testing
- [ ] Unit tests cover main logic
- [ ] Edge cases tested
- [ ] Test names follow Go conventions
```

---

### 🛡️ **Common Pitfalls & How to Avoid**

| Pitfall | Solution |
|---------|----------|
| AI tạo code không compile | Always compile before integrating |
| Ignored errors (`_ = ...`) | Search for `_ =` and fix |
| No context timeout | Add `context.WithTimeout` manually |
| SQL injection risk | Use parameterized queries, review carefully |
| Memory leaks in goroutines | Review goroutine lifecycle |
| Non-idiomatic Go | Run `golangci-lint` after generation |

---

## 📦 6. Toolchain Integration

### 🎯 **Recommended Setup cho Golang + AI**

```yaml
# .vscode/settings.json
{
  "go.lintOnSave": "workspace",
  "go.vetOnSave": "workspace",
  "go.formatOnSave": true,
  "gopls": {
    "ui.semanticTokens": true,
    "ui.completion.usePlaceholders": true
  },
  "github.copilot.enable": {
    "go": true
  }
}
```

### 🛠️ **Tool Stack**

| Category | Tools |
|----------|-------|
| AI Assistant | GitHub Copilot, Cursor, Claude 3.5, Gemini 2.0 |
| Linter | golangci-lint, staticcheck, revive |
| Formatter | gofmt, goimports |
| Testing | gotestsum, ginkgo, testify |
| Docs | godoc, swaggo |

---

## 📈 7. Continuous Improvement Loop

### 📊 **Measure & Optimize**

```markdown
## AI Productivity Metrics (Weekly Review)

- ⏱️ Time saved on boilerplate code
- 🐛 Bugs introduced from AI code (track & learn)
- 📝 Prompt iteration count (improve prompt quality)
- ✅ Code acceptance rate (how often AI code needs major changes)

## Prompt Library Maintenance

Create a `prompts/` folder in your project:
├── api_handlers.md
├── database_models.md
├── unit_tests.md
├── docker_setup.md
└── README.md (usage guide)
```

---

## 💡 Quick Reference: Top Prompts cho Golang

### 1. Generate REST Handler
```
Write a Gin handler for PUT /api/v1/users/:id that:
- Validates user ID from path
- Parses JSON body into UpdateUserRequest struct
- Calls userService.Update()
- Returns proper HTTP status codes
- Uses context with timeout
```

### 2. Generate GORM Model
```
Create a GORM model for Product with:
- ID, Name, Price, Stock, CategoryID
- Soft delete
- Timestamps
- Relationship to Category
- JSON tags and validation tags
```

### 3. Generate Unit Test
```
Write table-driven tests for function:
func CalculateTotal(items []Item, taxRate float64) float64
Include test cases for: empty slice, single item, multiple items, edge cases
```

### 4. Debug Help
```
This Go code panics with "concurrent map read and map write":
[paste code]
Explain why and provide fixed version with sync.RWMutex
```

---

## 🎯 Tóm tắt: A.I.D.E Framework

| Letter | Focus | Key Practice |
|--------|-------|--------------|
| **A** | Augmentation | AI là assistant, không phải replacement |
| **I** | Integration | Tích hợp AI vào workflow hiện tại có chủ đích |
| **D** | Discipline | Review kỹ, test đầy đủ, không blind trust |
| **E** | Evolution | Liên tục cải tiến prompt và đo lường hiệu quả |

---

**Bottom line**: AI không biến bạn thành "prompt engineer" – nó giải phóng bạn khỏi boilerplate để tập trung vào **architecture, design decisions, và business logic phức tạp** mà chỉ có con người mới làm tốt được.

# Framework Sử Dụng AI Hỗ Trợ Development với Golang

## 1. **Code Generation & Boilerplate**

### Khi nào sử dụng AI:
- **Scaffolding dự án mới**: Tạo cấu trúc thư mục, main.go, go.mod
- **CRUD operations**: Generate handlers, models, repositories
- **Interface implementations**: Tự động implement interfaces
- **Test boilerplate**: Tạo test cases cơ bản

### Prompt patterns hiệu quả:

```
❌ Không tốt: "Viết code Go cho tôi"

✅ Tốt: "Tạo Go HTTP handler với:
- Nhận JSON request có fields: name (string), age (int)
- Validate age > 0
- Return 201 nếu thành công, 400 nếu invalid
- Sử dụng chi-square router
- Include error handling theo Go conventions"
```

### Best practices:
- Cung cấp context về project structure
- Yêu cầu code theo Go idioms (error handling, naming conventions)
- Chỉ rõ dependencies đang dùng (gin, echo, chi...)
- Review và refactor code AI generate, không copy-paste mù quáng

---

## 2. **Debugging & Troubleshooting**

### AI là trợ lý debug tuyệt vời:

**Workflow hiệu quả:**
```
1. Paste error message/stack trace
2. Paste đoạn code liên quan (không paste toàn bộ file)
3. Mô tả expected behavior vs actual behavior
4. Hỏi AI phân tích root cause
```

**Ví dụ prompt:**
```
Tôi gặp panic này:
[paste stack trace]

Code của tôi:
[paste relevant snippet]

Đang cố gắng: [mô tả intent]
Expected: [kết quả mong muốn]
Actual: [kết quả thực tế]

Phân tích root cause và suggest fix?
```

### Lợi ích:
- AI nhìn ra pattern errors nhanh (nil pointer, race conditions)
- Giải thích error messages khó hiểu
- Suggest debugging strategies
- Point out anti-patterns trong Go

---

## 3. **Code Review & Refactoring**

### Sử dụng AI như senior developer:

**Các điểm review:**
- Go idioms và conventions
- Error handling patterns
- Concurrency issues (goroutines, channels)
- Memory leaks, resource cleanup
- Performance bottlenecks
- Security vulnerabilities

**Prompt template:**
```
Review đoạn Go code này:
[paste code]

Tập trung vào:
1. Go best practices và idioms
2. Potential bugs (race conditions, nil pointers)
3. Performance issues
4. Code readability
5. Suggest refactoring nếu cần
```

### Refactoring scenarios:
- **Extract methods**: Code quá dài → AI gợi ý tách functions
- **Interface abstraction**: Tight coupling → AI suggest interfaces
- **Error handling**: Improve error patterns
- **Simplification**: Giảm complexity, remove redundant code

---

## 4. **Testing Strategy**

### AI giúp viết tests nhanh hơn:

**Table-driven tests:**
```
Prompt: "Viết table-driven test cho function này:
[paste function]

Bao gồm:
- Happy path cases
- Edge cases (empty input, nil, zero values)
- Error cases
- Sử dụng testify/assert"
```

**Mock generation:**
```
Prompt: "Tạo mock implementation cho interface này:
[paste interface]

Sử dụng testify/mock hoặc gomock"
```

**Coverage gaps:**
- Paste coverage report
- Hỏi AI gợi ý test cases còn thiếu

### Test types:
- Unit tests với AI-generated cases
- Integration tests scaffolding
- Benchmark tests cho performance-critical code

---

## 5. **Architecture & Design Patterns**

### Tư vấn thiết kế:

**Scenario planning:**
```
Prompt: "Tôi đang xây dựng [mô tả system]:
- [list requirements]
- [list constraints: scale, performance...]
- Tech stack: Go, PostgreSQL, Redis

Gợi ý:
1. Architecture pattern phù hợp (clean arch, hexagonal, layered)
2. Cấu trúc thư mục
3. Package organization
4. Trade-offs của mỗi approach"
```

**Pattern implementation:**
- Repository pattern với Go
- Dependency injection patterns
- Middleware chains
- Circuit breaker, retry logic
- Worker pools, fan-out/fan-in

### Design decisions:
- Monolith vs microservices
- Sync vs async processing
- Database choices
- Caching strategies

---

## 6. **Performance Optimization**

### AI phân tích performance:

**Profiling analysis:**
```
Prompt: "Phân tích pprof output này:
[paste profile data]

Code của section hot path:
[paste code]

Suggest optimizations"
```

**Common optimizations AI giúp:**
- Goroutine leaks detection
- Inefficient allocations (pointer vs value)
- String concatenation → strings.Builder
- Map pre-allocation
- Reduce interface conversions
- Optimize SQL queries

**Benchmark interpretation:**
```
Paste benchmark results, hỏi AI:
- So sánh approaches
- Explain performance differences
- Suggest improvements
```

---

## 7. **Documentation & Comments**

### Auto-generate docs:

**Function documentation:**
```
Prompt: "Viết godoc comments cho function này:
[paste function signature và code]

Bao gồm:
- Mô tả chức năng
- Parameters
- Return values
- Example usage
- Panic conditions nếu có"
```

**README generation:**
- Project overview
- Installation instructions
- Usage examples
- API documentation

**Code comments:**
- Explain complex logic
- Document why, not what
- Warning về gotchas

---

## 8. **Learning & Knowledge Base**

### AI như personal tutor:

**Học Go concepts:**
```
"Giải thích [Go concept] với:
- Định nghĩa clear
- Khi nào sử dụng
- Code example thực tế
- Common pitfalls
- Best practices"
```

**Compare approaches:**
```
"So sánh [approach A] vs [approach B] trong Go:
- Use cases
- Pros/cons
- Performance implications
- Code examples cho mỗi approach"
```

**Keep up-to-date:**
- Hỏi về Go version mới features
- Best practices evolution
- Library recommendations

---

## 9. **Dependency Management**

### AI giúp chọn libraries:

**Tìm package phù hợp:**
```
Prompt: "Tôi cần [functionality] trong Go project:
- Requirements: [list]
- Constraints: [performance, size, maintenance...]

Recommend packages với:
- Comparison
- Pros/cons
- Code example
- Community support level"
```

**Upgrade assistance:**
- Breaking changes analysis
- Migration guides
- Compatibility checks

---

## 10. **Productivity Workflows**

### Developer workflow với AI:

#### **Morning routine:**
```
1. Review PRs với AI assistance
2. Plan tasks → hỏi AI về approach
3. Setup dev environment → AI generate configs
```

#### **Coding session:**
```
1. Write function signature → AI complete implementation
2. Stuck? → Rubber duck với AI
3. Need utility function? → AI generate
4. Refactor? → AI suggest improvements
```

#### **Before commit:**
```
1. AI review code changes
2. Generate/update tests
3. Update documentation
4. Check for common mistakes
```

#### **Debugging session:**
```
1. Error? → Paste to AI immediately
2. AI suggest causes + fixes
3. Implement fix
4. AI help write regression test
```

---

## 11. **Effective Prompting Strategies**

### Nguyên tắc vàng:

#### **Be Specific:**
```
❌ "Fix this code"
✅ "This code has nil pointer panic at line 45. 
   Expected behavior: handle nil user gracefully.
   Current: crashes.
   Fix theo Go error handling conventions."
```

#### **Provide Context:**
```
Include:
- Go version
- Dependencies đang dùng
- Project structure nếu relevant
- Constraints (performance, memory, compatibility)
```

#### **Iterative refinement:**
```
Round 1: Ask for general approach
Round 2: Ask for detailed implementation
Round 3: Ask for optimizations
Round 4: Ask for tests
```

#### **Request explanation:**
```
"Giải thích why this approach instead of [alternative]"
"Trade-offs của solution này?"
"Potential issues tôi cần aware?"
```

---

## 12. **AI Tools Ecosystem**

### Công cụ nên biết:

#### **Code Assistants:**
- **GitHub Copilot**: Inline suggestions, auto-complete
- **Cursor**: AI-powered IDE
- **ChatGPT/Claude**: Complex reasoning, architecture
- **Cody**: Code-aware assistant

#### **Specialized tools:**
- **AI code review**: SonarQube + AI
- **AI testing**: Test case generation
- **AI docs**: Auto-generate from code

#### **Integration workflow:**
```
Copilot: Quick autocomplete trong editor
     ↓
Claude: Complex logic, architecture decisions
     ↓
Copilot: Implement với assistance
     ↓
Claude: Final review và optimization
```

---

## 13. **Pitfalls & Anti-patterns**

### Tránh những sai lầm này:

#### **❌ Copy-paste mù quáng:**
- AI code có thể outdated
- Không phù hợp với codebase
- Security issues

#### **✅ Instead:**
- Understand code trước khi dùng
- Adapt vào project style
- Review security implications

#### **❌ Over-reliance:**
- Mất skill tự debug
- Không hiểu fundamentals

#### **✅ Instead:**
- Dùng AI để learn, không phải replace thinking
- Verify AI suggestions
- Build mental models

#### **❌ Prompt quá vague:**
- Results không đúng ý
- Lãng phí thời gian iterate

#### **✅ Instead:**
- Specific, detailed prompts
- Include constraints
- Provide examples

---

## 14. **Security Considerations**

### Cẩn thận với sensitive info:

#### **Không share:**
- API keys, credentials
- Proprietary business logic
- Customer data
- Internal architecture details

#### **Safe practices:**
- Anonymize code trước khi paste
- Use placeholder values
- Remove company-specific context
- Review AI suggestions cho security issues

#### **Security review với AI:**
```
Prompt: "Review code này cho security vulnerabilities:
[paste sanitized code]

Focus on:
- SQL injection
- XSS
- Authentication/authorization
- Input validation
- Resource exhaustion"
```

---

## 15. **Continuous Improvement**

### Học từ interactions:

#### **Keep a prompt library:**
```
Save prompts hoạt động tốt:
- Debugging patterns
- Code generation templates
- Review checklists
- Architecture questions
```

#### **Measure impact:**
```
Track:
- Time saved per task
- Code quality improvements
- Bugs caught by AI review
- Learning velocity
```

#### **Adapt workflow:**
```
Weekly review:
- Prompts nào effective?
- Tasks nào AI giúp nhiều nhất?
- Where AI struggles?
- Adjust workflow accordingly
```

---

## Tóm Tắt: AI Development Loop

```
┌─────────────────────────────────────┐
│  1. PLAN: Discuss approach với AI   │
│  2. CODE: AI assist implementation  │
│  3. TEST: AI generate test cases    │
│  4. DEBUG: AI help troubleshoot     │
│  5. REVIEW: AI code review          │
│  6. REFACTOR: AI suggest improvements│
│  7. DOCUMENT: AI generate docs      │
│  8. DEPLOY: AI check deployment     │
└─────────────────────────────────────┘
         ↓ Repeat & Improve ↓
```

---

**Key Mindset:** AI là **co-pilot**, không phải **auto-pilot**. Bạn vẫn là developer đưa ra quyết định cuối cùng. AI giúp bạn code nhanh hơn, học nhanh hơn, và tránh được common mistakes - nhưng understanding và judgment vẫn là của bạn.

Bạn đang dùng AI tool nào và muốn tối ưu workflow phần nào cụ thể?
