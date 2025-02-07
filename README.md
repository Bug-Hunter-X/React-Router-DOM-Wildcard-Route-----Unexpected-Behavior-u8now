# React Router DOM Wildcard Route (*) Unexpected Behavior

This repository demonstrates an uncommon bug in React Router DOM v6 related to the wildcard route (`*`). When a wildcard route is placed after other routes, it unexpectedly matches all routes before those other routes can be rendered, effectively overriding them. This is different from the expected behavior of the wildcard route, intended to act as a fallback for unmatched routes.

The problem lies in the order of routes defined within the `<Routes>` component.  If the wildcard route `*` appears before other routes, the intended behavior is observed, but if placed after, it overshadows all other defined routes. 

## Solution

The solution is simple: place the wildcard route (`*`) at the end of your route definitions within `<Routes>`.  This ensures that the wildcard route only matches if no other routes match first.