# Git Repository Fix Guide

## Problem
You're getting errors when pushing to GitHub because:
1. `node_modules` folder was accidentally committed (contains large files >100MB)
2. `.next` build folder was also committed
3. These folders should be ignored by Git

## Solution Steps

### Step 1: Remove large files from Git history
```bash
# Remove node_modules from Git tracking (but keep the folder locally)
git rm -r --cached node_modules/

# Remove .next build folder from Git tracking
git rm -r --cached .next/

# Remove other build artifacts
git rm -r --cached *.tsbuildinfo
```

### Step 2: Verify .gitignore is working
```bash
# Check that .gitignore exists (should show the file)
ls -la .gitignore

# If .gitignore doesn't exist, the mv command might have failed
# Create it manually:
cp gitignore.txt .gitignore
```

### Step 3: Commit the changes
```bash
# Add the updated .gitignore
git add .gitignore

# Commit the removal of large files
git commit -m "Remove node_modules and build files from Git tracking

- Add proper .gitignore file
- Remove node_modules/ from repository
- Remove .next/ build folder
- Remove TypeScript build info files"
```

### Step 4: Force push to update remote repository
```bash
# Force push to overwrite the remote repository
git push origin master --force
```

### Alternative: Clean Repository Approach
If the above doesn't work, here's a clean slate approach:

```bash
# 1. Create a new branch with only the source files
git checkout --orphan clean-master

# 2. Add only the necessary files
git add src/
git add public/
git add *.json
git add *.js
git add *.ts
git add *.md
git add .gitignore
git add components.json
git add postcss.config.mjs
git add eslint.config.mjs

# 3. Commit the clean version
git commit -m "Initial commit: Clean Uni Go Transport landing page

- Next.js 15+ with TypeScript
- Framer Motion animations
- Tailwind CSS styling
- Responsive design
- Yellow/white color palette"

# 4. Delete old master and rename clean branch
git branch -D master
git branch -m master

# 5. Force push the clean repository
git push origin master --force
```

## Files That Should Be Committed
✅ **Include these:**
- `src/` folder (all source code)
- `public/` folder (static assets)
- `package.json` and `package-lock.json`
- `tsconfig.json`
- `next.config.ts`
- `tailwind.config.js` (if exists)
- `postcss.config.mjs`
- `eslint.config.mjs`
- `components.json`
- `README.md`
- `.gitignore`
- Any `.md` files (documentation)

❌ **Never commit these:**
- `node_modules/` (dependencies)
- `.next/` (build output)
- `out/` (export output)
- `build/` (build folder)
- `.env*` (environment files)
- `*.tsbuildinfo` (TypeScript build cache)
- `.DS_Store` (macOS files)

## Verification
After fixing, verify your repository is clean:

```bash
# Check what files are tracked
git ls-files

# Check repository size (should be much smaller now)
du -sh .git

# Verify .gitignore is working
git status
# Should not show node_modules or .next folders
```

## Future Prevention
- Always check `.gitignore` exists before first commit
- Use `git status` before committing to see what files will be added
- Never commit `node_modules/` or build folders
- Use `git add .` carefully - prefer specific file additions

## Repository Size
After cleanup, your repository should be:
- **Before**: >100MB (due to node_modules)
- **After**: <10MB (only source code)

This will allow successful pushes to GitHub without file size limit errors.
