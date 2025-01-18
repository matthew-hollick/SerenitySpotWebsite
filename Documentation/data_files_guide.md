# Data Files Guide for Serenity Spot Website

This guide explains how to use and modify the YAML data files that control the content of the Serenity Spot website.

## File Structure

The website content is managed through YAML files in the `data/` directory:

- `banner.yaml` - Hero section at the top of the page
- `spotlight1.yaml`, `spotlight2.yaml`, `spotlight3.yaml` - Service sections
- `gallery.yaml` - Testimonials section
- `findUs.yaml` - Location and contact information section

## Content Formatting

### Basic YAML Structure

All YAML files use indentation for structure. The basic format is:
```yaml
key: "value"
nested_key:
  sub_key: "value"
```

### Markdown and HTML Support

Content fields support both Markdown and HTML formatting:

1. **Lists** (using Markdown):
```yaml
content: |
  Benefits include:
  
  - First item
  - Second item
  - Third item
```

2. **HTML with Classes**:
```yaml
content: |
  Regular text
  
  <p class="special">Highlighted text</p>
  
  <div class="highlight">Important notice</div>
```

### Available CSS Classes

- `special` - Creates a highlighted box or text
- `highlight` - Emphasizes text
- `content-align-left` - Left-aligns content
- `content-align-right` - Right-aligns content
- `style1`, `style2` - Different section styles
- `orient-left`, `orient-right` - Controls section layout
- `image-position-center` - Centers images
- `onscroll-image-fade-in` - Adds fade-in animation

## File-Specific Guidelines

### banner.yaml
```yaml
title: "Main Title"
subtitle: "Subtitle"
content: |
  Main content with optional HTML
button:
  text: "Button Text"
  url: "#section-id"
image: "images/banner.jpg"
```

### spotlight{1,2,3}.yaml
```yaml
title: "Section Title"
content: |
  Content with optional formatting
  
  - List items
  - More items
  
  <p class="special">Pricing or special info</p>
image: "images/section-image.jpg"
link: "#contact"
style: "style1 orient-right content-align-left image-position-center onscroll-image-fade-in"
```

### gallery.yaml
```yaml
title: "Gallery Title"
content: "Section description"
images:
  - image: "images/gallery/1.jpg"
    thumb: "images/gallery/thumbs/1.jpg"
    title: "Image Title"
    description: "Image description or testimonial"
```

### findUs.yaml
```yaml
title: "Section Title"
content: |
  <div class="special">
    Custom formatted content
  </div>
items:
  - title: "Item Title"
    content: "Item content"
    icon: "fa-icon-name"
```

## Best Practices

1. Always use the `|` operator for multi-line content
2. Keep indentation consistent (2 spaces recommended)
3. Use HTML classes for special formatting
4. Use relative paths for images (`images/filename.jpg`)
5. Test the site after making changes

## Common Tasks

### Adding a New Service
1. Copy an existing spotlight YAML file
2. Update the content and image path
3. Add the partial to `layouts/index.html`

### Updating Prices
Find the `<p class="special">` tags in the spotlight files and update the prices.

### Adding Testimonials
Add new entries to the `images` list in `gallery.yaml`.

### Modifying Contact Info
Update the `items` list in `findUs.yaml`.
