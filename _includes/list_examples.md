# Custom List Examples

This document shows how to use the custom list styles in your Jekyll posts.

## 1. Including the CSS

Add this to your layout file or post front matter:

```html
<link rel="stylesheet" href="/assets/css/custom.css">
```

## 2. Using Custom Lists in Markdown

### Custom Arrow List
```html
<ul class="custom-list">
  <li>First item with custom arrow</li>
  <li>Second item</li>
  <li>Third item</li>
</ul>
```

### Checklist Style
```html
<ul class="checklist">
  <li>Completed task one</li>
  <li>Completed task two</li>
  <li>Completed task three</li>
</ul>
```

### Numbered Feature List
```html
<ol class="feature-list">
  <li>Feature one with circular number</li>
  <li>Feature two with circular number</li>
  <li>Feature three with circular number</li>
</ol>
```

### Icon List
```html
<ul class="icon-list">
  <li data-icon="🚀">Deployment feature</li>
  <li data-icon="⚡">Performance optimization</li>
  <li data-icon="🔒">Security enhancement</li>
</ul>
```

### Highlighted List
```html
<ul class="highlight-list">
  <li>Important point one</li>
  <li>Important point two</li>
  <li>Important point three</li>
</ul>
```

### Compact List
```html
<ul class="compact-list">
  <li>Compact item 1</li>
  <li>Compact item 2</li>
  <li>Compact item 3</li>
</ul>
```

## 3. Using Jekyll Include

In your post front matter, define your list items:

```yaml
---
title: My Post
features:
  - "Feature one description"
  - "Feature two description"
  - "Feature three description"
---
```

Then in your post content:

```liquid
{% include custom_list.html items=page.features type="feature" %}
```

Available types:
- `custom` - Arrow style list
- `checklist` - Checkmark style
- `feature` - Numbered circles
- `icon` - Custom icons
- `highlight` - Highlighted boxes
- `compact` - Minimal spacing

## 4. Adding Custom Classes

```liquid
{% include custom_list.html items=page.items type="custom" class="mt-3 mb-3" %}
```
