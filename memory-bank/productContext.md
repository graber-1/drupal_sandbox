# Product Context

## Why This Project Exists

### Primary Problem
Drupal module developers need a consistent, reliable local development environment that mirrors the complexity of real-world Drupal installations while providing robust testing capabilities. Without standardized tooling, developers face:

- Inconsistent local setups leading to "works on my machine" issues
- Time-consuming environment configuration for each new module project
- Difficulty running comprehensive quality assurance checks
- Lack of standardized testing workflows

### Solution Approach
This Drupal sandbox provides a pre-configured, containerized development environment that eliminates setup friction and ensures consistency across different development machines and team members.

## How It Should Work

### Developer Experience Goals
1. **Instant Setup**: `ddev start` and `ddev composer clean-install` should create a fully functional Drupal 11 environment
2. **Seamless Testing**: Built-in commands for running PHPUnit, PHPStan, and PHPCS without configuration overhead
3. **Module-Focused**: Directory structure and workflows optimized specifically for module development
4. **Quality First**: Integrated QA tools that enforce Drupal coding standards and best practices

### Core User Workflows

#### New Module Development
1. Developer clones the sandbox
2. Runs setup commands to get working Drupal installation
3. Creates new module in `web/modules/contrib/` or `web/modules/custom/`
4. Uses built-in QA tools to ensure code quality
5. Tests module functionality in clean Drupal environment

#### Module Testing & QA
1. Developer places existing module in contrib directory
2. Runs automated test suite via composer scripts
3. Executes static analysis and coding standards checks
4. Validates module works correctly with Drupal 11

### Target Users
- **Primary**: Drupal module maintainers and contributors
- **Secondary**: Drupal developers learning module development
- **Tertiary**: QA teams testing Drupal modules

## Expected Outcomes

### User Benefits
- **Reduced Setup Time**: From hours to minutes for new development environments
- **Higher Code Quality**: Integrated QA tools catch issues early
- **Consistent Results**: Same environment across all development machines
- **Learning Platform**: Clear examples of best practices and proper tooling

### Technical Benefits
- **Standardization**: Consistent PHP, Drupal, and tool versions
- **Automation**: Scripted installation and testing processes
- **Isolation**: Containerized environment prevents conflicts
- **Reproducibility**: Identical setups for debugging and collaboration

## Success Metrics
- Time to functional environment: < 5 minutes
- Zero manual configuration for basic module development
- All QA tools work without additional setup
- Clean test results for modules that follow Drupal standards

This sandbox succeeds when module developers can focus on writing quality code rather than fighting with environment setup and tooling configuration.
