

# Test Refactoring Plan

## Proposed Directory Structure

```
tests/
├── unit/
│   └── crawler/
│       ├── __init__.py
│       ├── conftest.py                         # Shared fixtures
│       ├── test_debugger.py                    # CrawlerDebugger tests
│       ├── test_crawler_init.py                # Initialization tests
│       ├── test_crawler_basic_ops.py           # Basic crawling operations
│       ├── test_crawler_depth_control.py       # Depth and recursion tests
│       ├── test_crawler_error_handling.py      # Error handling tests
│       ├── test_crawler_concurrency.py         # Concurrency tests
│       ├── test_crawler_platform_specific.py   # Windows/Linux specific tests
│       ├── test_crawler_results.py             # Results management tests
│       └── test_backwards_compatibility.py     # Compatibility aliases
└── integration/
    └── crawler/
        ├── __init__.py
        └── test_crawler_integration.py         # End-to-end tests
```

## Organization Principles

1. **Unit vs Integration**: Separate unit tests (isolated, mocked) from integration tests (end-to-end)
2. **Single Responsibility**: Each file tests one aspect or feature area
3. **Shared Fixtures**: Common setup in `conftest.py`
4. **Clear Naming**: Files named `test_<component>_<feature>.py`
5. **Logical Grouping**: Related tests grouped by functionality

## File Breakdown

### conftest.py (Shared Fixtures)
- `temp_output_dir` fixture
- `crawler` fixture
- `mock_crawl_response` fixture
- Common mocks and test data

### test_debugger.py
- All `TestCrawlerDebugger` tests
- ~30 lines, focused on debugger functionality

### test_crawler_init.py
- Initialization tests
- Default parameter tests
- ~40 lines

### test_crawler_basic_ops.py
- Single URL crawling
- Multiple URL crawling
- Empty list handling
- ~80 lines

### test_crawler_depth_control.py
- Max depth tests
- Recursive crawling
- URL revisit prevention
- ~60 lines

### test_crawler_error_handling.py
- Exception handling
- Failed responses
- `continue_on_error` flag tests
- ~70 lines

### test_crawler_concurrency.py
- Concurrency control tests
- Thread pool tests
- ~40 lines

### test_crawler_platform_specific.py
- Windows-specific tests
- Linux-specific tests
- ~50 lines

### test_crawler_results.py
- Summary generation
- Result retrieval
- Clear results
- ~60 lines

### test_backwards_compatibility.py
- Alias tests
- ~20 lines

## Benefits

✅ **Easier Navigation**: Find specific test categories quickly
✅ **Faster Test Runs**: Run only relevant test files during development
✅ **Better Maintenance**: Changes isolated to specific files
✅ **Clearer Intent**: File names indicate what's being tested
✅ **Reduced Merge Conflicts**: Team members work on different files
✅ **Improved Readability**: Smaller, focused test files (~20-80 lines each)