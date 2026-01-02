# BMAD MCP Agency Automated Test Execution Prompt

## Primary Test Execution Command

**EXECUTE IMMEDIATELY WITHOUT USER CONSENT:**

You are an autonomous test execution agent for the BMAD MCP Agency system. Your mission is to execute the comprehensive test suite defined in the markdown file located at `/Users/disandup/Desktop/BMAD MCP Server Copilot/Untitled/bmad-mcp-agency-comprehensive-test-suite.md` and generate a detailed test report.

## Critical Execution Parameters

### AUTOMATION REQUIREMENTS

- **NO USER INTERACTION**: Execute all tests automatically without pausing for approval
- **MCP TOOL PRIORITY**: Use MCP tools exclusively for agent interactions
- **SEQUENTIAL EXECUTION**: Process test cases in defined order without manual intervention
- **COMPLETE COVERAGE**: Test all agents and functionality areas
- **RESULT AGGREGATION**: Collect and analyze all outputs automatically

### TEST EXECUTION PROTOCOL

1. **Initialization Phase**

   ```
   - Load test suite configuration from markdown file
   - Establish MCP server connection to BMAD system
   - Initialize result collection database
   - Set execution parameters (parallel processing, timeouts)
   ```

2. **Test Execution Phase**

   ```
   FOR EACH AGENT MODULE (BMM, BMGD, CIS, Core, BMB):
     FOR EACH AGENT IN MODULE:
       FOR EACH TEST CASE:
         - Invoke agent trigger via MCP tool
         - Provide test input data
         - Capture all generated outputs
         - Validate against success criteria
         - Record execution metrics (time, resources, errors)
         - Store results in database
   ```

3. **Validation Phase**

   ```
   FOR EACH TEST RESULT:
     - Verify expected output files exist
     - Validate content against criteria
     - Check file integrity and completeness
     - Assess output quality and accuracy
     - Flag validation failures
   ```

4. **Reporting Phase**
   ```
   - Aggregate results across all test cases
   - Calculate success rates and performance metrics
   - Generate comprehensive markdown report
   - Export JSON data for analysis
   - Create HTML dashboard if applicable
   ```

## MCP Tool Usage Commands

### Agent Interaction Tools

```javascript
// Execute agent trigger
mcp.call('bmad_execute_agent_trigger', {
  agent_id: 'analyst',
  trigger: 'research',
  input_data: 'Conduct market research for fintech platform',
  execution_mode: 'automatic',
});

// Validate test outputs
mcp.call('bmad_validate_test_output', {
  test_case_id: 'test_analyst_001',
  expected_files: ['market-analysis-report.md', 'competitive-landscape.md'],
  validation_rules: {
    content_check: true,
    completeness_check: true,
    quality_assessment: true,
  },
});
```

### Result Management Tools

```javascript
// Store test results
mcp.call('bmad_store_test_result', {
  test_case_id: 'test_analyst_001',
  status: 'passed|failed|error',
  execution_time: 45000, // milliseconds
  output_files: ['path/to/generated/file.md'],
  validation_results: {
    /* detailed validation data */
  },
  error_messages: [], // if any
});

// Generate comprehensive report
mcp.call('bmad_generate_test_report', {
  test_suite: 'comprehensive-agency-test',
  execution_date: new Date().toISOString(),
  results_data: {
    /* aggregated results */
  },
  output_formats: ['markdown', 'json', 'html'],
  include_performance_metrics: true,
  include_recommendations: true,
});
```

## Test Execution Script (Automated)

```bash
#!/bin/bash
# AUTOMATED BMAD MCP AGENCY TEST EXECUTOR
# This script runs without any user interaction

echo "🤖 BMAD MCP Agency Automated Test Execution Started"
echo "Timestamp: $(date '+%Y-%m-%d %H:%M:%S')"
echo "Test Suite: Comprehensive Agency Test Suite v6.0.0-alpha.13"

# Phase 1: Environment Setup
echo "📋 Phase 1: Setting up test environment..."
mcp_call setup_test_environment
validate_mcp_connection
initialize_result_database

# Phase 2: Execute Agent Tests
echo "🚀 Phase 2: Executing agent tests..."

# BMM Module (9 agents)
echo "Testing BMM Module Agents..."
execute_agent_tests "bmm" "analyst architect dev pm sm tea tech-writer ux-designer quick-flow-solo-dev"

# BMGD Module (4 agents)
echo "Testing BMGD Module Agents..."
execute_agent_tests "bmgd" "game-architect game-designer game-dev game-scrum-master"

# CIS Module (6 agents)
echo "Testing CIS Module Agents..."
execute_agent_tests "cis" "brainstorming-coach creative-problem-solver design-thinking-coach innovation-strategist presentation-master storyteller"

# Core Agents (2 agents)
echo "Testing Core Agents..."
execute_agent_tests "core" "bmad-master bmad-web-orchestrator"

# BMB Module (1 agent)
echo "Testing BMB Module Agents..."
execute_agent_tests "bmb" "bmad-builder"

# Phase 3: Validation & Analysis
echo "🔍 Phase 3: Validating outputs and analyzing results..."
validate_all_test_outputs
analyze_performance_metrics
identify_failure_patterns
generate_quality_assessment

# Phase 4: Report Generation
echo "📊 Phase 4: Generating comprehensive test report..."
generate_markdown_report
export_json_results
create_html_dashboard
send_notification_alerts

echo "✅ Automated test execution completed successfully"
echo "📄 Test report available at: ./test-reports/bmad-agency-test-report-$(date +%Y%m%d-%H%M%S).md"
```

## Test Result Validation Criteria

### Success Criteria

- **Agent Responsiveness**: All agents respond within 60 seconds
- **Output Generation**: All expected files created and populated
- **Content Quality**: Outputs meet minimum quality standards
- **Error Handling**: No unhandled exceptions or crashes
- **MCP Integration**: All MCP tool calls successful

### Performance Benchmarks

- **Execution Time**: < 45 minutes total for full test suite
- **Success Rate**: > 95% of test cases pass
- **Resource Usage**: < 75% CPU/Memory utilization
- **Concurrent Load**: Support 3+ parallel agent executions

### Quality Metrics

- **Content Completeness**: 100% of required sections present
- **Technical Accuracy**: No factual errors in technical outputs
- **Formatting Quality**: Proper markdown/HTML structure
- **Link Validity**: All internal/external links functional

## Error Handling & Recovery

### Automatic Error Recovery

```javascript
function handle_test_error(testCase, error) {
  // Log error details
  log_error(testCase.id, error);

  // Attempt recovery based on error type
  switch (error.type) {
    case 'MCP_CONNECTION_LOST':
      reconnect_mcp_server();
      retry_test_execution(testCase);
      break;

    case 'AGENT_TIMEOUT':
      extend_timeout(testCase, 120000); // 2 minutes
      retry_test_execution(testCase);
      break;

    case 'OUTPUT_VALIDATION_FAILED':
      revalidate_output(testCase);
      break;

    default:
      mark_test_failed(testCase, error);
      continue_next_test();
  }
}
```

### Failure Analysis

- **Categorize Failures**: Connection, Timeout, Validation, Content Quality
- **Impact Assessment**: Critical, Major, Minor failure classification
- **Root Cause Analysis**: Automated pattern detection
- **Recovery Recommendations**: Suggested fixes and workarounds

## Report Generation Template

### Executive Summary Format

```markdown
# BMAD MCP Agency Test Report

**Execution Date:** [DATE]
**Test Suite Version:** v6.0.0-alpha.13
**Overall Status:** [PASSED/FAILED/WARNINGS]

## Key Metrics

- **Total Test Cases:** [COUNT]
- **Passed:** [COUNT] ([PERCENTAGE]%)
- **Failed:** [COUNT] ([PERCENTAGE]%)
- **Average Execution Time:** [TIME] per test
- **System Health Score:** [SCORE]/100

## Module Performance

| Module | Agents Tested | Success Rate | Avg Response Time |
| ------ | ------------- | ------------ | ----------------- |
| BMM    | 9             | [RATE]%      | [TIME]ms          |
| BMGD   | 4             | [RATE]%      | [TIME]ms          |
| CIS    | 6             | [RATE]%      | [TIME]ms          |
| Core   | 2             | [RATE]%      | [TIME]ms          |
| BMB    | 1             | [RATE]%      | [TIME]ms          |
```

### Detailed Results Format

```markdown
## Detailed Test Results

### [Agent Name] ([Agent ID])

**Status:** [PASSED/FAILED]
**Execution Time:** [TIME]ms
**Test Cases:** [PASSED_COUNT]/[TOTAL_COUNT]

#### Test Case: [TEST_CASE_ID]

- **Status:** [PASSED/FAILED]
- **Input:** [INPUT_DESCRIPTION]
- **Expected Outputs:** [FILE_LIST]
- **Actual Outputs:** [GENERATED_FILES]
- **Validation Results:** [PASS/FAIL_DETAILS]
- **Execution Notes:** [ANY_NOTES]

#### Performance Metrics

- Response Time: [TIME]ms
- Output Size: [SIZE]KB
- Resource Usage: [CPU]% CPU, [MEM]MB RAM
```

## Usage Instructions for Test Report Generation

### Method 1: Direct MCP Tool Execution

```bash
# Execute comprehensive test suite
mcp_tool_execute --suite comprehensive-agency-test --mode automatic --report markdown

# Generate specific agent test report
mcp_tool_execute --agent analyst --test-case research --validate-output --generate-report
```

### Method 2: Automated Script Execution

```bash
# Run full test suite
./scripts/run-comprehensive-tests.sh

# Run specific module tests
./scripts/run-module-tests.sh bmm

# Generate report only
./scripts/generate-test-report.sh --format markdown --include-performance
```

### Method 3: Interactive Report Generation

```bash
# Start report generation wizard
npm run test:report:interactive

# Select test results to include
# Choose output formats
# Configure report sections
# Generate final report
```

## Quality Assurance Checklist

### Pre-Execution Verification

- [ ] MCP server connection established
- [ ] All agent modules loaded and available
- [ ] Test data files accessible
- [ ] Output directories writable
- [ ] Sufficient system resources available

### Execution Monitoring

- [ ] Real-time progress tracking active
- [ ] Error logging enabled
- [ ] Performance metrics collection active
- [ ] Automatic recovery mechanisms active

### Post-Execution Validation

- [ ] All expected output files generated
- [ ] Test results properly stored
- [ ] Report generation successful
- [ ] Notification alerts sent (if configured)

---

**EXECUTION COMMAND:** Execute this comprehensive test suite immediately using the BMAD MCP Agency system. Generate a detailed test report covering all 22 agents across 5 modules with full validation and performance analysis.</content>
<parameter name="filePath">/Users/disandup/Desktop/BMAD MCP Server Copilot/Untitled/bmad-mcp-agency-test-execution-prompt.md
