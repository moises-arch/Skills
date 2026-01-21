# Architecture Patterns

## 1. Separation of Concerns (SoC)
Divide your application into distinct sections, each addressing a separate concern.
- **Presentation Layer**: UI Components, Pages (dumb components).
- **Business Logic Layer**: Custom hooks, Services, Helper functions.
- **Data Access Layer**: API calls, Database queries, Server Actions.

## 2. Repository Pattern (Adapted for Server Actions)
Abstract data access logic behind a consistent API.
```typescript
// data-access/users.ts
export const getUserById = async (id: string) => { ... }

// actions/users.ts (Server Action)
import { getUserById } from '@/data-access/users'
export const fetchUser = async (id: string) => {
  const user = await getUserById(id)
  return user
}
```

## 3. Feature-Based Architecture
Organize code by feature rather than by technical role.
```text
src/
  features/
    auth/
      components/
      hooks/
      actions/
    dashboard/
      components/
      hooks/
```

## 4. Compound Component Pattern
For complex UI components that share state.
```tsx
<Select>
  <SelectTrigger />
  <SelectContent>
    <SelectItem />
  </SelectContent>
</Select>
```

## 5. Composition > Inheritance
Build complex components by combining simpler ones (Composition) rather than extending classes (Inheritance).
