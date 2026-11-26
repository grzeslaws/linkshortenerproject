# Clerk Authentication and Route Protection

## Provider

- Clerk is the only authentication and session system allowed in this application.
- Do not implement custom passwords, login cookies, manual session verification, or alternative auth providers.
- Keep Clerk keys and secrets in environment variables. Never commit them or expose them to client code.
- Use Clerk components and APIs from the installed `@clerk/nextjs` package.
- Keep the `<ClerkProvider>` setup in `app/layout.tsx`.

## Modal Sign-In and Sign-Up

- Launch sign-in with `<SignInButton mode="modal" />`.
- Launch sign-up with `<SignUpButton mode="modal" />`.
- Every sign-in and sign-up control must use modal mode.
- Catch-all routes may render `<SignIn />` or `<SignUp />` for direct URLs and fallback navigation.
- Do not build custom credentials forms or an alternate account creation flow.
- Wrap Clerk components that depend on request state in `<Suspense>`.
- Force successful sign-ins and sign-ups to redirect to `/dashboard` through the `ClerkProvider` redirect props.

## Protected Routes

- `/dashboard` requires an active Clerk session.
- Protect the `/dashboard` page with `await auth.protect()` before protected data or UI is rendered.
- Add `auth.protect()` to protected Route Handlers and Server Functions; page or layout protection alone is insufficient.
- Add a nearby `loading.tsx` for a page that protects its entire render.
- Signed-in users who visit `/` must be redirected to `/dashboard`.
- Signed-out users may remain public at `/` unless a later requirement changes the route policy.
- Do not rely on a layout, redirect, or proxy check as the only authorization boundary.

Use `await auth()` from `@clerk/nextjs/server` when a route needs to inspect session state without immediately rejecting it. In Clerk v7, use `await auth.protect()` for resource-level authentication.

## Proxy

- Keep `proxy.ts` using bare `clerkMiddleware()`.
- Keep the existing Clerk API and static-asset matcher entries.
- Do not add `createRouteMatcher`; it is deprecated in the installed Clerk SDK.
- Treat proxy/session checks as routing conveniences, not authorization.

## Authorization

- Authentication answers who the user is; authorization answers what the user may access.
- Check authorization for every mutation and sensitive read.
- Scope user-owned database records by the authenticated Clerk user ID.
- Do not accept ownership or role claims from client input as authorization evidence.
- Fail closed and never expose another user's links, analytics, or account data.
