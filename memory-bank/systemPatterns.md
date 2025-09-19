# System Patterns

## System Architecture

### Overall Structure
The system follows Drupal's recommended-project architecture pattern:
```
drupal_sandbox/
├── web/                    # Web root (Drupal core + modules/themes)
├── vendor/                 # Composer dependencies
├── config/sync/           # Configuration management
├── .ddev/                 # DDEV containerization config
└── composer.json          # Dependency & script management
```

### Key Technical Decisions

#### Containerization Strategy
- **DDEV-Based Development**: All development happens within DDEV containers
- **Consistent Environment**: Same PHP, database, and web server versions across all machines
- **Isolation**: Project dependencies don't conflict with host system

#### Dependency Management
- **Composer-First**: All PHP dependencies managed via Composer
- **Drupal Packaging**: Uses `packages.drupal.org/8` repository for Drupal-specific packages
- **Patch Management**: `cweagans/composer-patches` handles contrib module modifications
- **Scaffold System**: `drupal/core-composer-scaffold` manages file placement

#### Code Organization
- **Clear Separation**: Distinct paths for core, contrib, custom, and vendor code
- **Module-Centric**: Optimized for module development workflows
- **Configuration as Code**: All configuration exported to version control

## Design Patterns in Use

### Development Workflow Pattern
1. **Container First**: `ddev start` creates isolated environment
2. **Composer Install**: Dependencies resolved and installed
3. **Clean Install**: Fresh Drupal installation with minimal configuration
4. **Module Placement**: Code goes in appropriate directory structure
5. **QA Integration**: Built-in testing and analysis tools

### Quality Assurance Pattern
- **Automated Testing**: PHPUnit integration with custom test scripts
- **Static Analysis**: PHPStan with strict rules and deprecation checking
- **Code Standards**: PHPCS with Drupal coding standards
- **Continuous Feedback**: Composer scripts provide immediate QA feedback

### Configuration Management Pattern
- **Export-First**: Configuration changes exported to `config/sync/`
- **Version Controlled**: All configuration tracked in Git
- **Import-Ready**: Fresh installations can import existing configuration
- **Environment Agnostic**: Same configuration works across environments

## Component Relationships

### Core Dependencies
```
Drupal Core 11
├── Admin Toolbar (UI enhancement)
├── Drush (CLI management)
└── Core Scaffold (file management)
```

### Development Dependencies
```
Development Layer
├── Devel (debugging tools)
├── Developer Console (enhanced debugging)
├── Config Inspector (configuration validation)
└── PHPUnit (testing framework)
```

### QA Tool Chain
```
Quality Assurance
├── PHPStan (static analysis)
│   ├── Strict Rules
│   ├── Deprecation Rules
│   └── Ergebnis Rules
├── PHPCS (coding standards)
└── PHPUnit (functional testing)
```

## Critical Implementation Paths

### Environment Setup Flow
1. `ddev start` → Container initialization
2. `ddev composer install` → Dependency resolution
3. `ddev composer clean-install` → Fresh Drupal installation
4. Module development ready

### Module Development Flow
1. Create/place module in `web/modules/contrib/` or `web/modules/custom/`
2. Use `composer test [module]` for automated testing
3. Use `composer phpstan [module]` for static analysis
4. Use `composer phpcs [module]` for coding standards
5. Fix issues and repeat

### Configuration Workflow
1. Make configuration changes in Drupal UI
2. Export configuration: `drush config:export`
3. Commit configuration files to Git
4. Import on other environments: `drush config:import`

## File Structure Patterns

### Module Placement Strategy
- `web/core/` - Drupal core (managed by Composer)
- `web/modules/contrib/` - Community contributed modules
- `web/modules/custom/` - Project-specific custom modules
- `web/modules/under_development/` - Active development modules

### Configuration Structure
- `config/sync/` - Exported Drupal configuration
- All `.yml` files version controlled
- Environment-specific configurations handled via settings files

### Testing Structure
- `web/sites/default/files/simpletest/` - Test artifacts
- `web/sites/simpletest/browser_output/` - Browser test output
- Tests run within DDEV container environment

This architecture ensures consistency, maintainability, and follows Drupal community best practices while optimizing for module development workflows.
