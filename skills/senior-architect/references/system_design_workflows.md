# System Design & Workflows

## 1. Feature Implementation Flow (RFC Process)
Before coding complex features:
1.  **Problem Statement**: What are we solving?
2.  **Proposed Solution**: High-level approach.
3.  **Data Model Changes**: Schema updates (SQL).
4.  **API Design**: Endpoints or Actions input/output.
5.  **UI/UX States**: Loading, Error, Empty, Success.
6.  **Security Review**: RLS policies, input validation.

## 2. Database Schema Design Workflow
1.  **Identify Entities**: Nouns in your requirements (User, Project, Asset).
2.  **Define Relationships**: 1:1, 1:N, M:N.
3.  **Normalize**: Remove redundancy (3NF).
4.  **Denormalize (Carefully)**: Only for specific performance bottlenecks(e.g., storing `count` on a parent record if accessed frequently).
5.  **Index**: Add indices on columns frequently used in `WHERE`, `ORDER BY`, and `JOIN` clauses.

## 3. Performance Optimization Workflow
1.  **Measure**: Use Lighthouse, Vercel Analytics, or `console.time`.
2.  **Identify Bottleneck**: Backend Query? Network Waterfall? Large JS Bundle? Re-renders?
3.  **Optimize Backend**: Add DB indexes, cache expensive queries, optimize SQL.
4.  **Optimize Frontend**: Implement Virtualization, Code Splitting (Lazy Load), Memoization, Optimistic Updates.
5.  **Verify**: Measure again to confirm improvement.
