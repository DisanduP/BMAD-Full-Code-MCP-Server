# BMAD MCP Agency Testing Suite

This directory contains comprehensive testing tools for the BMAD MCP-based agency system.

## Files Overview

### 📋 Test Suite Definition

- **`bmad-mcp-agency-comprehensive-test-suite.md`** - Complete test suite covering all 22 agents across 5 modules
- **`bmad-mcp-agency-test-execution-prompt.md`** - Automated execution prompts for AI agents

### 🚀 Test Execution

- **`scripts/run-comprehensive-tests.sh`** - Automated test runner script

## Quick Start

### 1. Setup Environment

```bash
# Navigate to project root
cd /Users/disandup/Desktop/BMAD\ MCP\ Server\ Copilot/Untitled

# Ensure MCP server is built and configured
cd mcp-server
npm install
npm run build
```

### 2. Configure VS Code MCP Settings

Add to your VS Code `settings.json`:

```json
{
  "mcp.servers": {
    "bmad": {
      "command": "node",
      "args": ["/Users/disandup/Desktop/BMAD MCP Server Copilot/Untitled/mcp-server/build/index.js"],
      "env": {}
    }
  }
}
```

### 3. Execute Comprehensive Test Suite

```bash
# Run all tests automatically
./scripts/run-comprehensive-tests.sh

# The script will:
# - Initialize test environment
# - Execute tests for all 22 agents
# - Generate comprehensive report
# - Provide execution summary
```

### 4. Review Test Results

```bash
# Check the generated report
ls -la test-reports/
cat test-reports/bmad-agency-test-report-$(date +%Y%m%d)*.md
```

## Test Coverage

### Modules Tested

- **BMM (Business Management Method)**: 9 agents
  - Analyst, Architect, Developer, Product Manager, Scrum Master, etc.
- **BMGD (Game Development)**: 4 agents
  - Game Architect, Game Designer, Game Developer, Game Scrum Master
- **CIS (Creative Innovation Studio)**: 6 agents
  - Innovation Strategist, Creative Problem Solver, Brainstorming Coach, etc.
- **Core Agents**: 2 agents
  - BMad Master, BMad Web Orchestrator
- **BMB (Builder)**: 1 agent
  - BMad Builder

### Test Types

- **Functionality Tests**: Core agent capabilities
- **Integration Tests**: Cross-agent workflows
- **Performance Tests**: Response times and resource usage
- **Quality Tests**: Output validation and completeness

## Automated Execution Features

### Zero-Interaction Mode

- Tests run completely automatically
- No user prompts or confirmations required
- MCP tools used exclusively for agent interaction

### Comprehensive Reporting

- **Markdown Reports**: Human-readable test results
- **JSON Export**: Machine-readable data for analysis
- **Performance Metrics**: Execution times and resource usage
- **Quality Assessment**: Output validation results

### Error Handling

- Automatic retry for transient failures
- Detailed error logging and categorization
- Recovery recommendations in reports

## Using the Test Execution Prompt

### For AI Agent Integration

Use the content from `bmad-mcp-agency-test-execution-prompt.md` as a prompt for AI agents to:

1. **Execute Tests Automatically**: Run the full test suite without human intervention
2. **Generate Reports**: Create comprehensive test reports
3. **Validate Results**: Assess system health and performance
4. **Provide Recommendations**: Suggest improvements based on findings

### Example Usage with Claude/GPT

```
Execute the BMAD MCP Agency comprehensive test suite using this prompt as your guide.
Follow all automation requirements and generate a detailed test report.
```

## Customization

### Adding New Tests

1. Edit `bmad-mcp-agency-comprehensive-test-suite.md`
2. Add new test cases following the existing format
3. Update the test runner script if needed

### Modifying Test Parameters

- Edit timeout values in the script
- Adjust parallel execution limits
- Configure reporting formats

## Troubleshooting

### Common Issues

- **MCP Server Not Running**: Ensure MCP server is started before running tests
- **Permission Errors**: Make sure scripts are executable (`chmod +x`)
- **Path Issues**: Verify all file paths in configuration

### Debug Mode

```bash
# Run with verbose logging
DEBUG=1 ./scripts/run-comprehensive-tests.sh
```

## Performance Benchmarks

- **Expected Execution Time**: 15-30 minutes for full suite
- **Success Rate Target**: >95% pass rate
- **Resource Usage**: <75% CPU/Memory during execution

## Contributing

When adding new agents or test cases:

1. Update the comprehensive test suite markdown
2. Modify the test runner script accordingly
3. Test the changes locally
4. Update this README with any new procedures

---

**Version:** v6.0.0-alpha.13
**Last Updated:** January 1, 2026
**Test Coverage:** 22 agents, 50+ test cases</content>
<parameter name="filePath">/Users/disandup/Desktop/BMAD MCP Server Copilot/Untitled/BMAD-TESTING-README.md
