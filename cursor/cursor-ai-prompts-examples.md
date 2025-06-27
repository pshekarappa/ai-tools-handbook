# Cursor AI Prompts & Examples for Frontend Development

## Table of Contents

1. [Component Development Prompts](#component-development-prompts)
2. [State Management Prompts](#state-management-prompts)
3. [Testing & Quality Assurance](#testing--quality-assurance)
4. [Performance Optimization](#performance-optimization)
5. [Debugging & Troubleshooting](#debugging--troubleshooting)
6. [Code Review & Refactoring](#code-review--refactoring)
7. [API Integration](#api-integration)
8. [Accessibility & SEO](#accessibility--seo)
9. [Build & Deployment](#build--deployment)
10. [Team Collaboration](#team-collaboration)

---

## Component Development Prompts

### React Component Creation

#### Basic Component with TypeScript

```typescript
// Prompt:
"Create a React functional component named UserProfile with the following requirements:
- TypeScript with strict typing
- Props interface for user data (id, name, email, avatar, role)
- JSX structure with semantic HTML
- CSS modules for styling
- PropTypes for runtime validation
- JSDoc comments for documentation
- Error handling for missing props
- Accessibility attributes (ARIA labels, roles)
- Responsive design considerations"

// Expected Output Example:
interface UserProfileProps {
  user: {
    id: string;
    name: string;
    email: string;
    avatar?: string;
    role: 'admin' | 'user' | 'moderator';
  };
  onEdit?: () => void;
  onDelete?: () => void;
}

/**
 * UserProfile component displays user information with optional edit/delete actions
 * @param props - Component props
 * @returns JSX.Element
 */
const UserProfile: React.FC<UserProfileProps> = ({
  user,
  onEdit,
  onDelete
}) => {
  // Implementation with error handling, accessibility, and styling
};
```

#### Complex Interactive Component

```typescript
// Prompt:
"Create a SearchableProductGrid component with the following features:
- Search input with debounced API calls
- Filter options (category, price range, rating)
- Sorting options (price, popularity, rating)
- Infinite scrolling pagination
- Loading states and error handling
- Responsive grid layout
- Product card hover effects
- Add to cart functionality
- Accessibility compliance
- Performance optimization with React.memo"

// Usage in prompt:
"Tech stack: React 18, TypeScript, Styled Components, React Query, Intersection Observer API"
```

### Custom Hooks Development

#### Data Fetching Hook

```typescript
// Prompt:
"Create a custom React hook called useProductData that:
- Fetches product data from API endpoint
- Handles loading, error, and success states
- Implements caching with expiration
- Supports pagination and filtering
- Includes retry logic for failed requests
- Provides data transformation capabilities
- Returns TypeScript-typed data
- Integrates with React Query for optimization
- Includes cleanup on component unmount"

// Implementation guidance:
interface UseProductDataOptions {
  category?: string;
  priceRange?: [number, number];
  sortBy?: 'price' | 'rating' | 'popularity';
  enabled?: boolean;
}

const useProductData = (options: UseProductDataOptions) => {
  // Hook implementation
};
```

#### Form Management Hook

```typescript
// Prompt:
"Create a comprehensive form management hook called useFormValidation that:
- Manages form state and validation
- Supports nested object validation
- Provides real-time validation feedback
- Handles async validation (email uniqueness, etc.)
- Includes field-level and form-level validation
- Supports custom validation rules
- Manages touched/dirty state
- Provides form submission handling
- Includes accessibility features
- Works with popular validation libraries (Yup, Zod)"
```

---

## State Management Prompts

### Redux Toolkit Integration

#### Complete Store Setup

```typescript
// Prompt:
"Set up a complete Redux Toolkit store for an e-commerce application with:
- User authentication slice (login, logout, profile)
- Shopping cart slice (add, remove, update quantities)
- Product catalog slice (search, filters, categories)
- Order management slice (create, track, history)
- UI state slice (modals, notifications, loading)
- Middleware for logging and API calls
- DevTools configuration
- TypeScript integration with typed hooks
- Persistence with localStorage
- Error handling and retry logic"

// Store structure example:
const store = configureStore({
  reducer: {
    auth: authSlice.reducer,
    cart: cartSlice.reducer,
    products: productsSlice.reducer,
    orders: ordersSlice.reducer,
    ui: uiSlice.reducer,
  },
  middleware: (getDefaultMiddleware) =>
    getDefaultMiddleware({
      serializableCheck: {
        ignoredActions: [FLUSH, REHYDRATE, PAUSE, PERSIST, PURGE, REGISTER],
      },
    }).concat(apiSlice.middleware),
});
```

#### RTK Query API Integration

```typescript
// Prompt:
"Create RTK Query API slice for product management with:
- CRUD operations (create, read, update, delete)
- Search and filtering endpoints
- Bulk operations support
- Optimistic updates for better UX
- Cache invalidation strategies
- Error handling with user-friendly messages
- Loading states management
- Pagination support
- File upload capabilities
- Real-time updates with WebSocket integration"
```

### Context API Patterns

#### Theme Provider Implementation

```typescript
// Prompt:
"Create a comprehensive theme provider using React Context that:
- Manages light/dark mode toggle
- Supports custom color schemes
- Handles responsive breakpoints
- Provides typography scale
- Includes animation preferences
- Supports accessibility preferences (reduced motion, high contrast)
- Persists theme selection in localStorage
- Provides TypeScript types for theme values
- Includes theme switching animations
- Works with CSS-in-JS libraries"
```

---

## Testing & Quality Assurance

### Unit Testing with Jest & RTL

#### Component Testing Strategy

```typescript
// Prompt:
"Create comprehensive unit tests for a LoginForm component using Jest and React Testing Library:
- Test rendering with different props
- Test form submission with valid/invalid data
- Test validation error messages
- Test loading states during submission
- Test accessibility features (screen reader support)
- Test keyboard navigation
- Test error handling scenarios
- Mock API calls and test different responses
- Test form reset functionality
- Include edge cases and boundary conditions"

// Test structure example:
describe('LoginForm', () => {
  beforeEach(() => {
    // Setup
  });

  describe('Rendering', () => {
    it('should render login form with required fields', () => {
      // Test implementation
    });
  });

  describe('User Interactions', () => {
    it('should handle form submission with valid data', async () => {
      // Test implementation
    });
  });

  describe('Error Handling', () => {
    it('should display validation errors for invalid input', async () => {
      // Test implementation
    });
  });
});
```

#### Integration Testing

```typescript
// Prompt:
"Create integration tests for a shopping cart workflow:
- Test adding products to cart from product list
- Test updating quantities in cart
- Test removing items from cart
- Test cart persistence across page refreshes
- Test cart synchronization with authentication
- Test checkout process integration
- Mock API endpoints with MSW (Mock Service Worker)
- Test error scenarios (network failures, server errors)
- Test loading states and user feedback
- Include performance testing for large cart sizes"
```

### E2E Testing with Playwright/Cypress

#### User Journey Testing

```typescript
// Prompt:
"Create end-to-end tests for a complete user journey using Playwright:
- User registration and email verification
- User login and profile setup
- Product browsing and search
- Adding items to cart and wishlist
- Checkout process with payment
- Order confirmation and tracking
- User logout and session management
- Test across different browsers and devices
- Include visual regression testing
- Handle dynamic content and loading states"

// Example test structure:
test.describe('E-commerce User Journey', () => {
  test('complete purchase flow', async ({ page }) => {
    // Navigate to homepage
    await page.goto('/');

    // Search for product
    await page.fill('[data-testid="search-input"]', 'laptop');
    await page.click('[data-testid="search-button"]');

    // Add to cart and checkout
    // Test implementation
  });
});
```

---

## Performance Optimization

### Bundle Analysis & Optimization

#### Webpack Bundle Optimization

```javascript
// Prompt:
"Analyze and optimize our React application bundle:
- Identify large dependencies and suggest alternatives
- Implement code splitting for route-based chunks
- Set up dynamic imports for heavy components
- Configure tree shaking for unused code elimination
- Optimize images and assets (WebP, lazy loading)
- Implement service worker for caching
- Set up bundle analyzer for ongoing monitoring
- Configure compression (gzip, brotli)
- Optimize CSS delivery (critical CSS, async loading)
- Set up performance budgets and alerts"

// Webpack config example:
module.exports = {
  optimization: {
    splitChunks: {
      chunks: 'all',
      cacheGroups: {
        vendor: {
          test: /[\\/]node_modules[\\/]/,
          name: 'vendors',
          chunks: 'all',
        },
        common: {
          name: 'common',
          minChunks: 2,
          chunks: 'all',
        },
      },
    },
  },
};
```

#### React Performance Optimization

```typescript
// Prompt:
"Optimize this React component for performance:
- Implement React.memo for unnecessary re-renders prevention
- Use useMemo for expensive calculations
- Optimize useCallback for stable function references
- Implement virtual scrolling for large lists
- Add lazy loading for images and components
- Optimize state updates to minimize re-renders
- Use React DevTools Profiler to identify bottlenecks
- Implement error boundaries for graceful error handling
- Add performance monitoring and metrics
- Consider server-side rendering for initial load"

// Example optimization:
const OptimizedProductList = React.memo(({ products, onProductClick }) => {
  const memoizedProducts = useMemo(() =>
    products.filter(product => product.isAvailable),
    [products]
  );

  const handleProductClick = useCallback((productId) => {
    onProductClick(productId);
  }, [onProductClick]);

  return (
    <VirtualizedList
      items={memoizedProducts}
      renderItem={({ item }) => (
        <ProductCard
          key={item.id}
          product={item}
          onClick={handleProductClick}
        />
      )}
    />
  );
});
```

---

## Debugging & Troubleshooting

### Common React Issues

#### Memory Leak Detection

```typescript
// Prompt:
"Help me debug memory leaks in this React component:
- Identify potential memory leak sources
- Check for event listeners not being cleaned up
- Review useEffect cleanup functions
- Analyze closure references that prevent garbage collection
- Check for React refs that hold DOM references
- Review third-party library integrations
- Provide solutions with proper cleanup patterns
- Add memory profiling and monitoring
- Include prevention strategies for future development"

// Common memory leak patterns and solutions:
useEffect(() => {
  const handleScroll = () => {
    // Handle scroll
  };

  window.addEventListener('scroll', handleScroll);

  // Cleanup function to prevent memory leaks
  return () => {
    window.removeEventListener('scroll', handleScroll);
  };
}, []);
```

#### State Management Issues

```typescript
// Prompt:
"Debug this state management issue in Redux:
- Actions are dispatched but state doesn't update
- Component doesn't re-render when state changes
- State updates are causing performance issues
- Async actions are not working correctly
- DevTools show unexpected state transitions
- Multiple components have stale state
- Provide step-by-step debugging approach
- Include Redux DevTools usage
- Suggest performance optimizations
- Add proper error handling"
```

### Network & API Issues

#### API Error Handling

```typescript
// Prompt:
"Create a comprehensive error handling system for API calls:
- Handle different HTTP status codes appropriately
- Implement retry logic with exponential backoff
- Provide user-friendly error messages
- Log errors for debugging and monitoring
- Handle network timeouts and connection issues
- Implement offline support with caching
- Add error boundaries for graceful degradation
- Include loading states and user feedback
- Support error recovery and retry mechanisms
- Integrate with error tracking services (Sentry, LogRocket)"

// Error handling implementation:
const apiErrorHandler = {
  handleError: (error: ApiError) => {
    switch (error.status) {
      case 400:
        return 'Please check your input and try again.';
      case 401:
        return 'Please log in to continue.';
      case 403:
        return 'You do not have permission to perform this action.';
      case 404:
        return 'The requested resource was not found.';
      case 500:
        return 'Server error. Please try again later.';
      default:
        return 'An unexpected error occurred.';
    }
  },

  shouldRetry: (error: ApiError) => {
    return error.status >= 500 || error.status === 429;
  }
};
```

---

## Code Review & Refactoring

### Legacy Code Modernization

#### Class to Functional Component Migration

```typescript
// Prompt:
"Convert this class component to a functional component with hooks:
- Replace componentDidMount with useEffect
- Convert state management to useState/useReducer
- Replace lifecycle methods with appropriate hooks
- Maintain all existing functionality
- Improve performance with React.memo if needed
- Add proper TypeScript types
- Update prop handling and default props
- Ensure accessibility is maintained
- Add comprehensive tests for the converted component
- Include migration strategy for similar components"

// Before (Class Component):
class UserProfile extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      user: null,
      loading: true,
      error: null
    };
  }

  componentDidMount() {
    this.fetchUser();
  }

  fetchUser = async () => {
    // Implementation
  };

  render() {
    // Render logic
  }
}

// After (Functional Component):
const UserProfile: React.FC<UserProfileProps> = ({ userId }) => {
  const [user, setUser] = useState<User | null>(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState<string | null>(null);

  useEffect(() => {
    fetchUser();
  }, [userId]);

  const fetchUser = useCallback(async () => {
    // Implementation
  }, [userId]);

  // Render logic
};
```

#### Architecture Refactoring

```typescript
// Prompt:
"Refactor this monolithic component into smaller, reusable components:
- Identify logical component boundaries
- Extract reusable UI components
- Separate business logic into custom hooks
- Implement proper prop drilling or context usage
- Maintain TypeScript typing throughout
- Ensure accessibility is preserved
- Add comprehensive testing for each new component
- Document component interfaces and usage
- Consider performance implications of component splitting
- Provide migration guide for other developers"
```

### Code Quality Improvements

#### TypeScript Migration

```typescript
// Prompt:
"Migrate this JavaScript React project to TypeScript:
- Add TypeScript configuration and dependencies
- Create type definitions for props and state
- Add interface definitions for API responses
- Convert component files from .js to .tsx
- Add type safety for event handlers
- Create utility types for common patterns
- Configure strict mode and handle all type errors
- Add type checking to CI/CD pipeline
- Update testing setup for TypeScript
- Provide team training materials for TypeScript adoption"

// Migration example:
// Before (JavaScript):
const ProductCard = ({ product, onAddToCart }) => {
  const handleClick = () => {
    onAddToCart(product.id);
  };

  return (
    <div className="product-card">
      <h3>{product.name}</h3>
      <p>${product.price}</p>
      <button onClick={handleClick}>Add to Cart</button>
    </div>
  );
};

// After (TypeScript):
interface Product {
  id: string;
  name: string;
  price: number;
  image: string;
  description: string;
}

interface ProductCardProps {
  product: Product;
  onAddToCart: (productId: string) => void;
}

const ProductCard: React.FC<ProductCardProps> = ({ product, onAddToCart }) => {
  const handleClick = useCallback(() => {
    onAddToCart(product.id);
  }, [product.id, onAddToCart]);

  return (
    <div className="product-card">
      <h3>{product.name}</h3>
      <p>${product.price}</p>
      <button onClick={handleClick}>Add to Cart</button>
    </div>
  );
};
```

---

## API Integration

### RESTful API Integration

#### Complete API Service Layer

```typescript
// Prompt:
"Create a comprehensive API service layer for our React application:
- Implement base API client with axios/fetch
- Add request and response interceptors
- Handle authentication token management
- Implement automatic token refresh
- Add request caching and deduplication
- Include error handling and retry logic
- Support different environments (dev, staging, prod)
- Add request/response logging
- Implement rate limiting handling
- Include TypeScript types for all endpoints"

// API service implementation:
class ApiService {
  private baseURL: string;
  private authToken: string | null = null;

  constructor(baseURL: string) {
    this.baseURL = baseURL;
    this.setupInterceptors();
  }

  private setupInterceptors() {
    // Request interceptor
    axios.interceptors.request.use(
      (config) => {
        if (this.authToken) {
          config.headers.Authorization = `Bearer ${this.authToken}`;
        }
        return config;
      },
      (error) => Promise.reject(error)
    );

    // Response interceptor
    axios.interceptors.response.use(
      (response) => response,
      async (error) => {
        if (error.response?.status === 401) {
          await this.refreshToken();
          return axios.request(error.config);
        }
        return Promise.reject(error);
      }
    );
  }

  // API methods
  async get<T>(endpoint: string): Promise<T> {
    // Implementation
  }

  async post<T>(endpoint: string, data: any): Promise<T> {
    // Implementation
  }
}
```

### GraphQL Integration

#### Apollo Client Setup

```typescript
// Prompt:
"Set up Apollo Client for GraphQL integration:
- Configure Apollo Client with caching
- Set up authentication handling
- Implement error handling and retry logic
- Add optimistic updates for better UX
- Configure subscription support for real-time data
- Set up code generation for TypeScript types
- Add offline support with cache persistence
- Implement query performance optimization
- Add debugging and development tools
- Create reusable query and mutation hooks"

// Apollo Client configuration:
const client = new ApolloClient({
  uri: process.env.REACT_APP_GRAPHQL_ENDPOINT,
  cache: new InMemoryCache({
    typePolicies: {
      Product: {
        fields: {
          reviews: {
            merge(existing = [], incoming) {
              return [...existing, ...incoming];
            },
          },
        },
      },
    },
  }),
  link: from([
    onError(({ graphQLErrors, networkError, operation, forward }) => {
      if (graphQLErrors) {
        graphQLErrors.forEach(({ message, locations, path }) =>
          console.log(
            `[GraphQL error]: Message: ${message}, Location: ${locations}, Path: ${path}`
          )
        );
      }
      if (networkError) console.log(`[Network error]: ${networkError}`);
    }),
    createAuthLink(),
    createHttpLink({
      uri: process.env.REACT_APP_GRAPHQL_ENDPOINT,
    }),
  ]),
});
```

---

## Accessibility & SEO

### WCAG Compliance

#### Comprehensive Accessibility Implementation

```typescript
// Prompt:
"Make this component fully accessible according to WCAG 2.1 AA standards:
- Add proper ARIA labels and roles
- Implement keyboard navigation support
- Ensure proper focus management
- Add screen reader support
- Handle color contrast requirements
- Implement proper heading hierarchy
- Add skip links and landmarks
- Support high contrast mode
- Include focus indicators
- Test with screen readers and accessibility tools"

// Accessibility example:
const AccessibleModal: React.FC<ModalProps> = ({
  isOpen,
  onClose,
  title,
  children
}) => {
  const modalRef = useRef<HTMLDivElement>(null);
  const previousFocusRef = useRef<HTMLElement | null>(null);

  useEffect(() => {
    if (isOpen) {
      previousFocusRef.current = document.activeElement as HTMLElement;
      modalRef.current?.focus();
    } else {
      previousFocusRef.current?.focus();
    }
  }, [isOpen]);

  const handleKeyDown = (event: KeyboardEvent) => {
    if (event.key === 'Escape') {
      onClose();
    }
  };

  if (!isOpen) return null;

  return (
    <div
      className="modal-overlay"
      onClick={onClose}
      role="dialog"
      aria-modal="true"
      aria-labelledby="modal-title"
    >
      <div
        ref={modalRef}
        className="modal-content"
        onClick={(e) => e.stopPropagation()}
        onKeyDown={handleKeyDown}
        tabIndex={-1}
      >
        <h2 id="modal-title">{title}</h2>
        <button
          className="modal-close"
          onClick={onClose}
          aria-label="Close modal"
        >
          ×
        </button>
        {children}
      </div>
    </div>
  );
};
```

### SEO Optimization

#### Next.js SEO Implementation

```typescript
// Prompt:
"Implement comprehensive SEO for a Next.js e-commerce site:
- Add dynamic meta tags based on page content
- Implement structured data (JSON-LD)
- Set up Open Graph and Twitter Card meta tags
- Add canonical URLs and handle duplicates
- Implement breadcrumb navigation
- Add XML sitemap generation
- Set up robots.txt configuration
- Implement image optimization with alt text
- Add page speed optimization
- Configure internationalization for multi-language support"

// SEO component example:
interface SEOProps {
  title: string;
  description: string;
  canonical?: string;
  ogImage?: string;
  structuredData?: any;
}

const SEO: React.FC<SEOProps> = ({
  title,
  description,
  canonical,
  ogImage,
  structuredData,
}) => {
  return (
    <Head>
      <title>{title}</title>
      <meta name="description" content={description} />
      <meta name="viewport" content="width=device-width, initial-scale=1" />

      {canonical && <link rel="canonical" href={canonical} />}

      {/* Open Graph */}
      <meta property="og:type" content="website" />
      <meta property="og:title" content={title} />
      <meta property="og:description" content={description} />
      {ogImage && <meta property="og:image" content={ogImage} />}

      {/* Twitter Card */}
      <meta name="twitter:card" content="summary_large_image" />
      <meta name="twitter:title" content={title} />
      <meta name="twitter:description" content={description} />
      {ogImage && <meta name="twitter:image" content={ogImage} />}

      {/* Structured Data */}
      {structuredData && (
        <script
          type="application/ld+json"
          dangerouslySetInnerHTML={{
            __html: JSON.stringify(structuredData),
          }}
        />
      )}
    </Head>
  );
};
```

---

## Build & Deployment

### CI/CD Pipeline Setup

#### GitHub Actions Configuration

```yaml
# Prompt:
"Create a comprehensive CI/CD pipeline for a React application:
- Set up automated testing on pull requests
- Implement code quality checks (ESLint, Prettier)
- Add security scanning for dependencies
- Configure build optimization and caching
- Set up deployment to multiple environments
- Implement rollback capabilities
- Add performance monitoring and alerts
- Configure automated accessibility testing
- Set up bundle size monitoring
- Include smoke tests for deployed applications"

# Example GitHub Actions workflow:
name: CI/CD Pipeline

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
        with:
          node-version: '18'
          cache: 'npm'

      - run: npm ci
      - run: npm run lint
      - run: npm run type-check
      - run: npm run test -- --coverage
      - run: npm run build

      - name: Upload coverage to Codecov
        uses: codecov/codecov-action@v3

      - name: Bundle size analysis
        run: npm run analyze:bundle
```

### Docker Configuration

#### Multi-stage Docker Build

```dockerfile
# Prompt:
"Create an optimized Docker configuration for a React application:
- Use multi-stage build for smaller production image
- Implement proper caching layers
- Add security best practices
- Configure environment variables handling
- Set up health checks
- Implement graceful shutdown
- Add logging configuration
- Optimize for container orchestration
- Include development and production variants
- Add security scanning in build process"

# Dockerfile example:
# Build stage
FROM node:18-alpine AS builder

WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production && npm cache clean --force

COPY . .
RUN npm run build

# Production stage
FROM nginx:alpine AS production

COPY --from=builder /app/build /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

HEALTHCHECK --interval=30s --timeout=3s --start-period=5s --retries=3 \
  CMD curl -f http://localhost:80/ || exit 1

CMD ["nginx", "-g", "daemon off;"]
```

---

## Team Collaboration

### Code Review Guidelines

#### PR Template and Checklist

```markdown
# Prompt:

"Create a comprehensive pull request template for frontend development:

- Include checklist for code quality standards
- Add sections for testing verification
- Include performance impact assessment
- Add accessibility compliance check
- Include security review items
- Add documentation updates verification
- Include breaking changes notification
- Add deployment considerations
- Include reviewer guidance
- Add automated check integration"

## Pull Request Template

### Description

Brief description of changes and motivation.

### Type of Change

- [ ] Bug fix (non-breaking change that fixes an issue)
- [ ] New feature (non-breaking change that adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] Performance improvement
- [ ] Code refactoring
- [ ] Documentation update

### Testing

- [ ] Unit tests added/updated
- [ ] Integration tests added/updated
- [ ] E2E tests added/updated
- [ ] Manual testing completed
- [ ] Accessibility testing completed

### Code Quality

- [ ] Code follows team style guidelines
- [ ] Self-review completed
- [ ] Code is properly commented
- [ ] No console.log statements in production code
- [ ] TypeScript errors resolved
- [ ] ESLint warnings addressed

### Performance

- [ ] Bundle size impact assessed
- [ ] Performance implications considered
- [ ] Memory usage evaluated
- [ ] Loading time impact measured

### Security

- [ ] No sensitive data exposed
- [ ] Input validation implemented
- [ ] Authentication/authorization considered
- [ ] XSS prevention measures in place

### Deployment

- [ ] Environment variables updated
- [ ] Database migrations included (if applicable)
- [ ] Feature flags configured
- [ ] Rollback plan documented
```

### Knowledge Sharing

#### Documentation Standards

````markdown
# Prompt:

"Create a comprehensive documentation standard for our frontend team:

- Component documentation with examples
- API integration documentation
- Architecture decision records (ADRs)
- Troubleshooting guides
- Onboarding documentation for new team members
- Code style and conventions guide
- Testing strategies documentation
- Performance optimization guidelines
- Security best practices
- Deployment procedures"

## Component Documentation Template

### ComponentName

#### Overview

Brief description of what the component does and when to use it.

#### Props

| Prop    | Type                     | Required | Default   | Description          |
| ------- | ------------------------ | -------- | --------- | -------------------- |
| title   | string                   | Yes      | -         | The title to display |
| variant | 'primary' \| 'secondary' | No       | 'primary' | Visual variant       |

#### Usage Examples

```tsx
// Basic usage
<ComponentName title="Hello World" />

// With all props
<ComponentName
  title="Hello World"
  variant="secondary"
  onClick={handleClick}
/>
```
````

#### Accessibility

- Supports keyboard navigation
- Includes ARIA labels
- High contrast mode compatible

#### Testing

- Unit tests cover all prop combinations
- Accessibility tests included
- Visual regression tests available

```

---

This comprehensive collection of prompts and examples provides your frontend team with practical, actionable guidance for leveraging Cursor AI effectively. Each prompt is designed to be specific enough to generate useful code while being flexible enough to adapt to your team's specific needs and technology stack.

Remember to:
1. Customize prompts based on your specific tech stack
2. Include your team's coding standards and conventions
3. Always review and test AI-generated code
4. Iterate and improve prompts based on results
5. Share successful prompts with your team

These prompts will help your team maintain consistency, improve code quality, and accelerate development while ensuring best practices are followed throughout your projects.
```
