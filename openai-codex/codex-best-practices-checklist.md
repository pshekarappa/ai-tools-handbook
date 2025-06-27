# OpenAI Codex Best Practices Checklist for Frontend Engineers

## Quick Reference Guide for Daily Development

### ✅ Pre-Development Setup

#### Project Context Configuration

- [ ] **Define project structure** in initial prompts
- [ ] **Specify technology stack** (React, Vue, Angular, etc.)
- [ ] **Include coding standards** (ESLint config, style guide)
- [ ] **Document architectural patterns** being used
- [ ] **Set up TypeScript** configuration details
- [ ] **Define component patterns** (atomic design, etc.)

#### Tool Integration

- [ ] **Configure IDE integration** (VS Code, WebStorm)
- [ ] **Set up API access** and authentication
- [ ] **Install necessary extensions** for enhanced experience
- [ ] **Configure code formatting** (Prettier, ESLint)
- [ ] **Set up version control** integration

### ✅ Prompt Engineering Excellence

#### Context-Rich Prompting

- [ ] **Always provide project context** before asking for code
- [ ] **Include specific requirements** and constraints
- [ ] **Reference existing code patterns** when available
- [ ] **Specify output format** (TypeScript, JSX, etc.)
- [ ] **Include error handling requirements**
- [ ] **Mention accessibility needs** upfront

#### Effective Prompt Structure

```markdown
## Template for Feature Requests

"In our [framework] [version] application using:

- [State management solution]
- [Styling approach]
- [Testing framework]
- [Other key dependencies]

Create a [component/feature] that:

- [Primary functionality]
- [User interaction requirements]
- [Performance requirements]
- [Accessibility requirements]
- [Testing requirements]

Following our patterns in [reference files/components]"
```

#### Incremental Development

- [ ] **Start with basic structure** before adding complexity
- [ ] **Request one feature at a time** for complex components
- [ ] **Build up functionality iteratively**
- [ ] **Test each increment** before proceeding
- [ ] **Refactor and optimize** in separate steps

### ✅ Code Quality Assurance

#### TypeScript Best Practices

- [ ] **Request strict TypeScript types** for all components
- [ ] **Ask for interface definitions** upfront
- [ ] **Include generic type patterns** where appropriate
- [ ] **Request type guards** for runtime safety
- [ ] **Generate utility types** for common patterns

#### Component Architecture

- [ ] **Follow single responsibility principle**
- [ ] **Request proper prop interfaces**
- [ ] **Include default props** where appropriate
- [ ] **Implement error boundaries**
- [ ] **Add loading and error states**
- [ ] **Include proper ref forwarding**

#### Performance Considerations

- [ ] **Request React.memo** for expensive components
- [ ] **Ask for useCallback** on event handlers
- [ ] **Include useMemo** for expensive calculations
- [ ] **Implement lazy loading** for large components
- [ ] **Request virtual scrolling** for large lists
- [ ] **Optimize bundle splitting**

### ✅ Testing Strategy

#### Test Coverage Requirements

- [ ] **Request unit tests** for all components
- [ ] **Include integration tests** for user flows
- [ ] **Generate accessibility tests**
- [ ] **Create performance tests** for critical paths
- [ ] **Include error scenario tests**
- [ ] **Add visual regression tests** where needed

#### Testing Framework Integration

- [ ] **Specify testing framework** (Jest, Vitest, etc.)
- [ ] **Include testing utilities** (React Testing Library)
- [ ] **Request mock strategies** for external dependencies
- [ ] **Generate test data factories**
- [ ] **Include custom render functions**

### ✅ Accessibility Compliance

#### WCAG 2.1 Requirements

- [ ] **Request ARIA attributes** for interactive elements
- [ ] **Include keyboard navigation** support
- [ ] **Add screen reader compatibility**
- [ ] **Implement focus management**
- [ ] **Include semantic HTML** structure
- [ ] **Request color contrast compliance**
- [ ] **Add reduced motion support**

#### Accessibility Testing

- [ ] **Generate axe-core tests**
- [ ] **Include keyboard navigation tests**
- [ ] **Request screen reader testing guidance**
- [ ] **Add high contrast mode support**
- [ ] **Include touch accessibility** for mobile

### ✅ Security Best Practices

#### Input Validation

- [ ] **Request input sanitization** for user data
- [ ] **Include XSS prevention** measures
- [ ] **Add CSRF protection** where needed
- [ ] **Implement rate limiting** for API calls
- [ ] **Request proper error handling** without data leaks

#### Authentication & Authorization

- [ ] **Secure token handling** in components
- [ ] **Proper session management**
- [ ] **Role-based access control**
- [ ] **Secure storage practices**
- [ ] **Audit logging requirements**

### ✅ Performance Optimization

#### Bundle Optimization

- [ ] **Request code splitting** strategies
- [ ] **Implement lazy loading** for routes
- [ ] **Optimize third-party libraries**
- [ ] **Use tree shaking** effectively
- [ ] **Minimize bundle size** impact

#### Runtime Performance

- [ ] **Optimize re-renders** with proper dependencies
- [ ] **Implement virtualization** for large datasets
- [ ] **Use Web Workers** for heavy computations
- [ ] **Optimize images** and media
- [ ] **Implement proper caching** strategies

### ✅ Large-Scale Application Patterns

#### Scalable Architecture

- [ ] **Design for team collaboration**
- [ ] **Implement consistent patterns**
- [ ] **Create reusable components**
- [ ] **Design for maintainability**
- [ ] **Plan for internationalization**

#### State Management

- [ ] **Choose appropriate state solution** (Redux, Zustand, etc.)
- [ ] **Implement proper data flow**
- [ ] **Design normalized state structure**
- [ ] **Include optimistic updates**
- [ ] **Handle error states** gracefully

### ✅ Code Review and Quality

#### Pre-Review Checklist

- [ ] **Run automated tests** before review
- [ ] **Check bundle size impact**
- [ ] **Verify accessibility compliance**
- [ ] **Test on multiple devices**
- [ ] **Validate performance metrics**

#### Review Criteria

- [ ] **Code follows team standards**
- [ ] **Components are properly tested**
- [ ] **Accessibility requirements met**
- [ ] **Performance impact is acceptable**
- [ ] **Security considerations addressed**
- [ ] **Documentation is complete**

### ✅ Documentation Standards

#### Component Documentation

- [ ] **Include prop interface documentation**
- [ ] **Add usage examples**
- [ ] **Document styling customization**
- [ ] **Include accessibility notes**
- [ ] **Add performance considerations**
- [ ] **Document breaking changes**

#### Storybook Integration

- [ ] **Create stories for all variants**
- [ ] **Include interaction testing**
- [ ] **Add accessibility addon**
- [ ] **Document design tokens**
- [ ] **Include visual regression**

### ✅ Deployment and Monitoring

#### Pre-Deployment

- [ ] **Run performance audits**
- [ ] **Check accessibility compliance**
- [ ] **Validate browser compatibility**
- [ ] **Test with real data**
- [ ] **Verify error handling**

#### Monitoring Setup

- [ ] **Implement error tracking**
- [ ] **Add performance monitoring**
- [ ] **Include user analytics**
- [ ] **Set up alerting**
- [ ] **Create performance budgets**

## Common Anti-Patterns to Avoid

### ❌ Poor Prompt Practices

- **Vague requests**: "Make this component better"
- **No context provided**: Generic requests without project details
- **Too complex at once**: Requesting entire applications
- **No specifications**: Missing requirements and constraints
- **Ignoring existing patterns**: Not referencing current codebase

### ❌ Code Quality Issues

- **Skipping TypeScript**: Not requesting proper types
- **Missing error handling**: Components without error states
- **No accessibility**: Ignoring WCAG requirements
- **Poor performance**: Not considering optimization
- **Missing tests**: Components without test coverage

### ❌ Security Oversights

- **Unsanitized inputs**: Missing input validation
- **Hardcoded secrets**: Including sensitive data in code
- **Missing authentication**: Unprotected components
- **XSS vulnerabilities**: Improper data handling
- **Insecure defaults**: Weak security configurations

### ❌ Performance Problems

- **Bundle bloat**: Large, unoptimized bundles
- **Memory leaks**: Uncleared intervals and listeners
- **Excessive re-renders**: Missing optimization hooks
- **Blocking operations**: Synchronous heavy computations
- **Poor caching**: Missing or incorrect cache strategies

## Success Metrics and KPIs

### Development Velocity

- **Time to create components**: 60-80% reduction
- **Bug fix time**: 40-50% improvement
- **Code review speed**: 30-40% faster
- **Documentation time**: 70-80% reduction

### Code Quality Metrics

- **Test coverage**: Maintain >90%
- **Accessibility score**: WCAG 2.1 AA compliance
- **Performance score**: Core Web Vitals > 90
- **Security vulnerabilities**: Minimize to zero

### Team Productivity

- **Feature delivery speed**: 2-3x faster
- **Technical debt reduction**: 25-30% improvement
- **Knowledge sharing**: Improved team alignment
- **Developer satisfaction**: Higher engagement scores

## Quick Command Reference

### Common Prompt Patterns

```bash
# Component Creation
"Create a [component-type] component with [features] using [technology] following [standards]"

# Bug Fixing
"Debug this [issue-type] in [component] with [symptoms] using [debugging-approach]"

# Optimization
"Optimize this [code-type] for [performance-metric] considering [constraints]"

# Testing
"Generate [test-type] tests for [component] covering [scenarios] using [framework]"

# Documentation
"Document this [code-type] including [sections] for [audience] following [format]"
```

### Integration Commands

```bash
# API Integration
"Connect this component to [API] handling [data-flow] with [error-handling]"

# State Management
"Integrate with [state-solution] managing [data-type] with [patterns]"

# Styling
"Style this component using [approach] following [design-system] with [responsive-behavior]"
```

---

_Use this checklist as your daily companion when working with OpenAI Codex to ensure consistent, high-quality frontend development practices._
