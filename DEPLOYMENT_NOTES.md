# Kwaai-AI-Lab GitHub Organization Landing Page - Deployment Notes

## Summary

This directory contains the GitHub organization landing page for Kwaai-AI-Lab, designed according to the approved implementation plan.

## Files Created

### 1. `/profile/README.md` (1028 lines)
Main organization landing page that will be displayed at https://github.com/Kwaai-AI-Lab

**Structure:**
- Hero section with mission statement and navigation badges
- Table of contents with 3-track navigation
- Organization overview (mission, principles, technical focus)
- **Track 1: Personal AI Development** (4 workgroups, 14 repositories)
  - Personal AI Agent Workgroup (Led by Balaji Lakshmanan)
  - KwaaiNet DePIN Workgroup (Led by Brian Ragazzi)
  - Personal Agency Workgroup (Led by Steve Vitka)
  - User Experience & Applications
- **Track 2: Fundamental AI Research** (6 workgroups, 11 repositories)
  - State Space Models (Led by Daryle Serrant)
  - AI 4 Med (Led by Diego Galeano)
  - Physics Inspired (Led by Reza Rassool)
  - Homomorphic Encryption (Led by Sulimon Sattari)
  - Distributed Knowledge Base & Beyond Graph RAG
  - AI Alignment Research
- **Track 3: Policy & Governance** (3 workgroups)
  - AI Policy and Alignment (Led by Steve Vitka)
  - AI Trust "Loyal Agents"
  - "MyTerms" IEEE P7012
- Supporting Infrastructure (6 repositories)
- Quick Start Guides (KwaaiNet, pAI-OS, PAI-Assistant)
- Community section (Slack + contribution guidelines)
- Publications & Research
- Documentation links & footer

**Features:**
- All 28 repositories mapped to appropriate workgroups
- Consistent project cards with badges (language, status, visibility)
- Quick start guides with copy-paste code examples
- Professional technical tone targeting developers & researchers
- Responsive design with proper markdown formatting

### 2. `/CONTRIBUTING.md` (479 lines)
Comprehensive contribution guidelines referenced from the main README.

**Sections:**
- Code of Conduct
- Getting Started
- How to Contribute
- Development Workflow
- Coding Standards (Rust, Python, TypeScript/JavaScript)
- Pull Request Process
- Issue Guidelines
- Community

## Deployment Instructions

### Step 1: Create .github Repository on GitHub

1. Go to https://github.com/orgs/Kwaai-AI-Lab/repositories
2. Click "New repository"
3. Name: `.github` (exactly, with the leading dot)
4. Description: "Organization profile and community health files"
5. Visibility: **Public** (required for organization profile to work)
6. Do NOT initialize with README (we have our own files)
7. Click "Create repository"

### Step 2: Push Content to .github Repository

From this directory:

```bash
# Initialize git in the .github directory
cd .github
git init

# Add files
git add profile/README.md CONTRIBUTING.md

# Commit
git commit -m "feat: Add organization landing page and contribution guidelines

- Create comprehensive landing page with 3-track structure
- Map all 28 repositories to official workgroups
- Add quick start guides for flagship projects
- Include CONTRIBUTING.md with detailed guidelines

This aligns with the official Kwaai workgroup structure from
www.kwaai.ai/workgroups"

# Add remote (replace with actual URL after creating repo)
git remote add origin git@github.com:Kwaai-AI-Lab/.github.git

# Push to main branch
git branch -M main
git push -u origin main
```

### Step 3: Verify Deployment

1. Visit https://github.com/Kwaai-AI-Lab
2. The profile/README.md should now display as the organization landing page
3. Verify all sections render correctly
4. Test navigation (table of contents anchor links)
5. Check badge rendering
6. Test external links (website, Slack, repositories)

### Step 4: Mobile & Accessibility Check

- View on mobile device to ensure responsive design
- Verify all images have alt text
- Check color contrast for accessibility
- Test with screen reader if possible

### Step 5: Team Review

Share with team for review:
- Content accuracy (project descriptions, status)
- Repository links (verify all public repos are accessible)
- Workgroup leaders attribution
- Technical correctness

## Verification Checklist

After deployment, verify:

- [ ] Landing page displays at https://github.com/Kwaai-AI-Lab
- [ ] All badges render correctly (language, status, visibility)
- [ ] Table of contents anchor links work
- [ ] External links work (website, Slack)
- [ ] Public repository links are accessible
- [ ] Code blocks in Quick Start guides are properly formatted
- [ ] Mobile view is readable and properly formatted
- [ ] No broken markdown formatting
- [ ] Images/badges load quickly
- [ ] Contribution guidelines link works

## Maintenance Notes

### Updating the Landing Page

When repositories change or new projects are added:

1. Clone the .github repository
2. Edit `profile/README.md`
3. Update the appropriate track/workgroup section
4. Maintain consistent project card format
5. Update badge information if status changes
6. Commit and push changes

### Adding New Repositories

When adding a new repository to the organization:

1. Determine which track and workgroup it belongs to
2. Add a project card in the appropriate section
3. Include: name, badges, description, links, features
4. Maintain alphabetical or logical ordering within sections

### Updating Badges

Badge URLs follow this pattern:

**Language badges:**
```
![Language](https://img.shields.io/badge/Language-Color?style=flat-square&logo=language&logoColor=white)
```

**Status badges:**
```
![Status](https://img.shields.io/badge/Status-Label-Color?style=flat-square)
```

**Visibility badges:**
```
![Public](https://img.shields.io/badge/Visibility-Public-blue?style=flat-square)
![Private](https://img.shields.io/badge/Visibility-Private-red?style=flat-square)
```

**Status colors:**
- Production: green
- Active Development: yellow
- Beta: orange
- Prototype: orange
- Research: purple
- Legacy/Deprecated: lightgrey

## Technical Details

### Repository Mapping

**28 repositories** organized into:
- **Track 1** (Personal AI Development): 14 repos across 4 workgroups
- **Track 2** (Fundamental AI Research): 11 repos across 6 workgroups
- **Track 3** (Policy & Governance): 0 repos (standards work)
- **Supporting Infrastructure**: 6 repos

### Language Distribution

- **Rust**: 2 repos (KwaaiNet, PHE)
- **Python**: 10+ repos (pAI-OS, kwaai-pai, alignment, etc.)
- **TypeScript**: 4 repos (kwaai-ui, CommunitySolidServer, etc.)
- **JavaScript**: 3 repos (open-webui-kwaai, PAIAssistant, etc.)
- **Jupyter**: 3 repos (notebooks, research)
- **HTML**: 2 repos (demos)
- **HCL**: 1 repo (Terraform)

### Visibility Breakdown

- **Public**: 16 repositories
- **Private**: 12 repositories

All private repos are clearly marked with red visibility badges.

## Design Decisions

1. **Official 3-track structure**: Aligns with www.kwaai.ai/workgroups
2. **Workgroup leaders attribution**: Shows leadership where known
3. **Professional technical tone**: Targets developers & researchers
4. **Complete visibility**: All projects shown with clear badges
5. **Consistent formatting**: Every project follows same card structure
6. **Actionable quick starts**: Copy-paste examples for flagship products
7. **Scannable layout**: Headers, bullets, badges, tables for easy navigation

## Support

For questions about the landing page:
- Technical issues: Open issue in .github repository
- Content updates: Submit PR to .github repository
- General questions: #dev-general on Slack

---

**Created**: 2026-02-04
**Version**: 1.0
**Status**: Ready for deployment
