# Data Model: Docusaurus Documentation Structure

## Entities

### Documentation Page
- **Fields**:
  - id: string (unique identifier)
  - title: string (page title)
  - content: string (markdown content)
  - frontmatter: object (metadata)
    - sidebar_label: string (navigation label)
    - sidebar_position: number (order in sidebar)
    - description: string (SEO description)
    - keywords: array<string> (SEO keywords)
  - path: string (URL path)
  - slug: string (URL-friendly version of title)

### Module
- **Fields**:
  - id: string (module identifier)
  - title: string (module title)
  - description: string (brief description)
  - chapters: array<Chapter> (list of chapters in the module)
  - position: number (order in documentation)

### Chapter
- **Fields**:
  - id: string (chapter identifier)
  - title: string (chapter title)
  - content: string (markdown content)
  - module_id: string (reference to parent module)
  - position: number (order within module)
  - path: string (relative path to markdown file)

### Navigation Item
- **Fields**:
  - type: enum ('doc', 'category', 'link')
  - label: string (display text)
  - id: string (reference to doc or category)
  - items: array<NavigationItem> (children for category type)
  - href: string (external link for link type)
  - collapsed: boolean (initial collapse state)

### Site Configuration
- **Fields**:
  - title: string (site title)
  - tagline: string (site tagline)
  - url: string (deployment URL)
  - baseUrl: string (base path)
  - favicon: string (favicon path)
  - organizationName: string (GitHub org/user)
  - projectName: string (GitHub repo name)
  - themeConfig: object (theme-specific settings)

## Relationships
- Module contains many Chapters (1:M)
- Chapter belongs to one Module (M:1)
- Site Configuration contains many Navigation Items (1:M)
- Navigation Item may contain many Navigation Items (self-referencing)

## States
- Documentation Page: draft, published, archived
- Module: active, inactive, deprecated
- Chapter: incomplete, in-review, published

## Validation Rules
- Page title must be unique within site
- Module ID must be unique
- Chapter position must be unique within module
- Navigation item ID must correspond to an existing document