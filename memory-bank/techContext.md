# Technical Context

## Technology Stack

### Core Technologies
- **Drupal**: Version 11 (latest stable)
- **PHP**: Version managed by DDEV (likely 8.1+ for Drupal 11 compatibility)
- **Database**: MySQL/MariaDB (via DDEV)
- **Web Server**: Apache/Nginx (via DDEV)
- **Containerization**: DDEV for local development

### Development Dependencies
- **Composer**: v2.x for PHP dependency management
- **Drush**: v13.3+ for Drupal CLI operations
- **DDEV**: Latest stable for containerized development

### Quality Assurance Tools
- **PHPUnit**: v9 or v10.5+ for automated testing
- **PHPStan**: Latest with strict rules for static analysis
- **PHPCS**: With Drupal coding standards via drupal-coder-extension
- **PHPSpec/Prophecy**: v2.0+ for mocking in tests

## Development Setup

### Prerequisites
1. DDEV installed on development machine
2. Docker runtime for DDEV containers
3. Git for version control
4. Composer globally available (though DDEV provides containerized version)

### Environment Configuration Files
- `.ddev/config.yaml` - DDEV project configuration
- `composer.json` - PHP dependencies and custom scripts
- `.editorconfig` - Code formatting standards
- `.gitignore` - Version control exclusions
- `.gitattributes` - Git handling instructions

### Installation Process
```bash
# 1. Clone and enter project
git clone [repository] && cd drupal_sandbox

# 2. Start DDEV environment
ddev start

# 3. Install dependencies
ddev composer install

# 4. Clean Drupal installation
ddev composer clean-install
```

## Technical Constraints

### Version Requirements
- **Drupal Core**: ^11 (Drupal 11.x only)
- **PHP**: Compatible with Drupal 11 requirements (8.1+)
- **Composer**: ^2.2 minimum
- **Node.js**: Not currently used, but available via DDEV if needed

### Performance Considerations
- **Development Focus**: Optimized for development, not production performance
- **Container Resources**: Performance depends on Docker resources allocated
- **Database**: SQLite available for lightweight testing, MySQL for full testing

### Security Constraints
- **Local Only**: DDEV configuration for local development only
- **No Production Config**: Environment not suitable for production deployment
- **Development Modules**: Includes development-only modules (devel, developer_console)

## Dependencies

### Core Drupal Modules
- **admin_toolbar**: ^3.4 - Enhanced administration interface
- **core**: ^11 - Drupal core framework
- **core-composer-scaffold**: ^11 - File management system

### Development Tools
- **devel**: ^5.3 - Developer utilities and debugging
- **developer_console**: ^1.0@dev - Enhanced developer console
- **config_inspector**: ^2.1 - Configuration validation

### Quality Assurance
- **chi-teck/drupal-coder-extension**: ^1.2 - Extended Drupal coding standards
- **ergebnis/phpstan-rules**: ^1.0 - Additional PHPStan rules
- **phpstan/phpstan-deprecation-rules**: ^1.0 - Deprecation detection
- **phpstan/phpstan-strict-rules**: ^1.2 - Strict type checking

### Build Tools
- **cweagans/composer-patches**: ^1.7 - Patch management system
- **composer/installers**: ^2.2 - Package installation management

## Tool Usage Patterns

### Composer Scripts
Custom scripts defined for common development tasks:
- `composer si` - Site install with existing config
- `composer clean-install` - Complete clean installation
- `composer test [module]` - Run PHPUnit tests
- `composer phpcs [module]` - Check coding standards
- `composer phpstan [module]` - Static analysis
- `composer phpcbf [module]` - Auto-fix coding standards

### DDEV Commands
Standard DDEV workflow:
- `ddev start` - Start development environment
- `ddev ssh` - Access container shell
- `ddev composer [command]` - Run Composer in container
- `ddev drush [command]` - Run Drush commands
- `ddev logs` - View container logs

### Directory Conventions
- **Contrib modules**: `web/modules/contrib/`
- **Custom modules**: `web/modules/custom/`
- **Under development**: `web/modules/under_development/`
- **Configuration**: `config/sync/`
- **Patches**: `patches/`
- **Tests**: `web/sites/default/files/simpletest/`

## Integration Points

### Version Control
- Git repository with GitHub remote
- Configuration exported to version control
- Patches tracked in repository
- Vendor directory excluded from version control

### Configuration Management
- Drupal configuration in `config/sync/`
- Environment-specific settings in `settings.local.php`
- DDEV settings in `.ddev/` directory
- QA tool configurations in root directory

### Testing Integration
- PHPUnit configuration in `phpunit.xml`
- Test artifacts in `web/sites/simpletest/`
- Browser test output captured
- Tests run within DDEV container

This technical setup provides a robust, standardized development environment that follows Drupal best practices while maintaining consistency across different development machines.
