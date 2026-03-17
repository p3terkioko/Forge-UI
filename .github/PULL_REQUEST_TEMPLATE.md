## What this PR does

<!-- A clear description of what was built or changed -->

Closes #<!-- issue number -->

## Type of change

- [ ] New feature
- [ ] Bug fix
- [ ] Refactor
- [ ] Documentation

## Checklist

### Code quality
- [ ] `npm run lint` passes with no errors
- [ ] `npm run typecheck` passes with no errors
- [ ] No `any` types introduced
- [ ] No hardcoded hex values or pixel spacing values
- [ ] All API calls go through `src/lib/api.ts`
- [ ] Business logic is in hooks, not in components

### Testing
- [ ] Full end to end flow tested locally with the backend running
- [ ] All states tested: loading, empty, error, and success
- [ ] Tested at 375px (mobile)
- [ ] Tested at 1280px (desktop)
- [ ] Tested in light mode
- [ ] Tested in dark mode

### Components
- [ ] New components have a `.stories.tsx` file
- [ ] New API response shapes have types defined in `src/types/`
- [ ] `src/components/README.md` updated if a new component was added

## Decisions made

<!-- Any implementation decisions the reviewer should know about. Why did you approach it this way? Were there alternatives? -->

## Screenshots

<!-- If this PR changes the UI, add screenshots at mobile and desktop widths in both light and dark mode -->