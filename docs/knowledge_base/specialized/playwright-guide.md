# 🎭 Playwright Automation Guide

> **Quick Reference for Test Automation**
> Framework: Playwright (TypeScript/JavaScript)

---

## 1. Project Setup

```bash
# Initialize Playwright project
npm init playwright@latest

# Install in existing project
npm install -D @playwright/test

# Install browsers
npx playwright install
```

---

## 2. Basic Test Structure

```typescript
import { test, expect } from '@playwright/test';

test.describe('Feature Name', () => {
  test.beforeEach(async ({ page }) => {
    await page.goto('https://example.com');
  });

  test('should do something', async ({ page }) => {
    // Arrange
    await page.fill('#email', 'user@example.com');
    
    // Act
    await page.click('button[type="submit"]');
    
    // Assert
    await expect(page).toHaveURL(/dashboard/);
  });
});
```

---

## 3. Page Object Model (POM)

```typescript
// pages/LoginPage.ts
import { Page, Locator } from '@playwright/test';

export class LoginPage {
  readonly page: Page;
  readonly emailInput: Locator;
  readonly passwordInput: Locator;
  readonly submitButton: Locator;

  constructor(page: Page) {
    this.page = page;
    this.emailInput = page.locator('[data-testid="email"]');
    this.passwordInput = page.locator('[data-testid="password"]');
    this.submitButton = page.locator('button[type="submit"]');
  }

  async goto() {
    await this.page.goto('/login');
  }

  async login(email: string, password: string) {
    await this.emailInput.fill(email);
    await this.passwordInput.fill(password);
    await this.submitButton.click();
  }
}
```

Usage:
```typescript
import { LoginPage } from './pages/LoginPage';

test('login with valid credentials', async ({ page }) => {
  const loginPage = new LoginPage(page);
  await loginPage.goto();
  await loginPage.login('user@example.com', 'password123');
  await expect(page).toHaveURL(/dashboard/);
});
```

---

## 4. Locator Strategies (Priority Order)

| Strategy | Example | Recommended |
| :--- | :--- | :---: |
| **data-testid** | `[data-testid="submit"]` | ✅ Best |
| **Role** | `getByRole('button', { name: 'Submit' })` | ✅ Best |
| **Label** | `getByLabel('Email')` | ✅ Good |
| **Placeholder** | `getByPlaceholder('Enter email')` | ✅ Good |
| **Text** | `getByText('Sign In')` | ⚠️ Fragile |
| **CSS** | `.btn-primary` | ⚠️ Fragile |
| **XPath** | `//button[@id="submit"]` | ❌ Avoid |

---

## 5. Common Actions

```typescript
// Navigation
await page.goto('https://example.com');
await page.goBack();
await page.reload();

// Input
await page.fill('#input', 'text');
await page.type('#input', 'text', { delay: 100 });  // Slow type
await page.clear('#input');

// Click
await page.click('button');
await page.dblclick('button');
await page.click('button', { force: true });  // Skip visibility check

// Select
await page.selectOption('select', 'value');
await page.selectOption('select', { label: 'Option Text' });

// Checkbox/Radio
await page.check('#checkbox');
await page.uncheck('#checkbox');

// File Upload
await page.setInputFiles('input[type="file"]', 'path/to/file.pdf');

// Hover
await page.hover('.menu-item');

// Keyboard
await page.keyboard.press('Enter');
await page.keyboard.type('Hello');
```

---

## 6. Assertions

```typescript
// Visibility
await expect(locator).toBeVisible();
await expect(locator).toBeHidden();

// Text
await expect(locator).toHaveText('Expected Text');
await expect(locator).toContainText('partial');

// Value
await expect(locator).toHaveValue('input value');

// URL
await expect(page).toHaveURL(/pattern/);
await expect(page).toHaveURL('https://exact.com');

// Count
await expect(locator).toHaveCount(5);

// Attribute
await expect(locator).toHaveAttribute('disabled', '');

// Screenshot comparison
await expect(page).toHaveScreenshot('name.png');
```

---

## 7. Waiting Strategies

```typescript
// Auto-waiting (built-in, preferred)
await page.click('button');  // Waits automatically

// Explicit wait
await page.waitForSelector('.loading', { state: 'hidden' });
await page.waitForURL(/dashboard/);
await page.waitForLoadState('networkidle');
await page.waitForTimeout(1000);  // ❌ Avoid fixed waits

// Wait for API response
await page.waitForResponse(resp => 
  resp.url().includes('/api/users') && resp.status() === 200
);
```

---

## 8. API Testing

```typescript
test('API test', async ({ request }) => {
  // GET
  const response = await request.get('/api/users');
  expect(response.status()).toBe(200);
  const body = await response.json();
  expect(body.users).toHaveLength(10);

  // POST
  const createResponse = await request.post('/api/users', {
    data: { name: 'John', email: 'john@example.com' }
  });
  expect(createResponse.status()).toBe(201);
});
```

---

## 9. Configuration (playwright.config.ts)

```typescript
import { defineConfig } from '@playwright/test';

export default defineConfig({
  testDir: './tests',
  timeout: 30000,
  retries: 2,
  workers: 4,
  reporter: [['html', { open: 'never' }]],
  
  use: {
    baseURL: 'https://example.com',
    screenshot: 'only-on-failure',
    video: 'retain-on-failure',
    trace: 'on-first-retry',
  },

  projects: [
    { name: 'chromium', use: { browserName: 'chromium' } },
    { name: 'firefox', use: { browserName: 'firefox' } },
    { name: 'webkit', use: { browserName: 'webkit' } },
  ],
});
```

---

## 10. Running Tests

```bash
# Run all tests
npx playwright test

# Run specific file
npx playwright test login.spec.ts

# Run with UI
npx playwright test --ui

# Run headed (see browser)
npx playwright test --headed

# Debug mode
npx playwright test --debug

# Generate report
npx playwright show-report
```

---

*Reference: https://playwright.dev/docs*
