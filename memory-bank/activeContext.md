# Active Context

## Current Work Focus
Module development in the `web/modules/under_development/` directory. Working with PHP to create custom Drupal modules that utilize APIs from Drupal core (`web/core/`) and contributed modules (`web/modules/contrib/`). The memory bank system is now established to support ongoing development work.

## Recent Changes
- Created `memory-bank/` directory structure
- Established `projectbrief.md` with core requirements and project scope
- Documented `productContext.md` with user experience goals and success metrics
- Currently populating remaining core memory bank files

## Next Steps
1. Begin module development in `web/modules/under_development/`
2. Utilize Drupal core APIs and contributed module APIs for functionality
3. Follow established QA workflows (PHPUnit, PHPStan, PHPCS) for code quality
4. Update memory bank documentation as modules are developed

## Active Decisions and Considerations

### Architecture Decisions
- **DDEV Choice**: Using DDEV for containerized development provides consistency and eliminates "works on my machine" issues
- **Drupal 11 Focus**: Latest stable version ensures forward compatibility and modern development practices
- **Module-Centric Design**: All tooling and workflows optimized for module development rather than site building

### Current Patterns and Preferences
- **Composer-First Workflow**: All dependencies managed via Composer, scripted installation processes
- **Quality-First Approach**: Integrated QA tools (PHPUnit, PHPStan, PHPCS) as first-class citizens
- **Minimal Profile**: Using minimal installation profile to reduce complexity and focus on module functionality

### Learnings and Project Insights
- Project structure follows standard Drupal recommended-project layout
- Comprehensive QA tooling already configured in composer.json
- DDEV configuration exists (`.ddev/` directory present)
- Custom scripts provide streamlined workflows for common tasks
- Patches system in place for contrib module modifications

## Important Patterns
- **Testing Strategy**: Automated testing focused on contrib modules in `web/modules/contrib/`
- **Code Standards**: PHPStan with strict rules, deprecation checking, and Drupal coding standards
- **Development Tools**: Developer Console, Devel module for enhanced debugging
- **Configuration Management**: Ready for config export/import workflows

## Current Environment Status
- Base Drupal 11 project structure established
- All development dependencies configured
- QA tools integrated and scripted
- DDEV environment ready for use
- Memory bank system complete and operational
- Ready for module development in `web/modules/under_development/`

This active context will be updated as work progresses to maintain current state awareness for future Cline sessions.
