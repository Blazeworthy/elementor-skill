---
name: elementor-page-builder
description: Create Elementor page templates for WordPress using JSON. Use when building landing pages, sections, headers, footers, or any visual layout. Reference the 3000+ templates in /templates for patterns.
---

# Elementor Page Builder Skill

Generate Elementor-compatible JSON templates for WordPress.

## Template Structure

```json
{
  "content": [...elements],
  "page_settings": [],
  "version": "0.4",
  "title": "template-name",
  "type": "container"
}
```

## Element Structure

Every element follows this pattern:

```json
{
  "id": "8char_id",
  "elType": "container|widget",
  "isInner": true|false,
  "settings": {...},
  "elements": [...children]
}
```

For widgets, add `widgetType`:
```json
{
  "id": "abc12345",
  "elType": "widget",
  "widgetType": "heading",
  "isInner": false,
  "settings": {...},
  "elements": []
}
```

## Container Settings

```json
{
  "settings": {
    "flex_direction": "column",
    "boxed_width": {"unit": "px", "size": 1290, "sizes": []},
    "flex_gap": {"column": "35", "row": "35", "isLinked": true, "unit": "px", "size": 35},
    "flex_justify_content": "center",
    "flex_align_items": "center",
    "flex_wrap": "wrap",
    "content_width": "full",
    "width": {"unit": "%", "size": 50, "sizes": []},
    "background_background": "classic",
    "background_color": "#F5F5F5",
    "padding": {"unit": "px", "top": "120", "right": "40", "bottom": "120", "left": "40", "isLinked": false},
    "padding_tablet": {"unit": "px", "top": "80", "right": "40", "bottom": "80", "left": "40", "isLinked": false},
    "padding_mobile": {"unit": "px", "top": "60", "right": "20", "bottom": "60", "left": "20", "isLinked": false},
    "margin": {"unit": "px", "top": "0", "right": "0", "bottom": "0", "left": "0", "isLinked": true},
    "border_radius": {"unit": "px", "top": "20", "right": "20", "bottom": "20", "left": "20", "isLinked": true},
    "_title": "Section Name"
  }
}
```

### Responsive Variants

Add `_tablet` or `_mobile` suffix for responsive overrides:
- `padding_tablet`, `padding_mobile`
- `width_tablet`, `width_mobile`
- `flex_direction_mobile`
- `flex_gap_tablet`, `flex_gap_mobile`
- `flex_wrap_mobile`
- `border_radius_mobile`

## Common Widgets

### Heading

```json
{
  "id": "heading01",
  "elType": "widget",
  "widgetType": "heading",
  "isInner": false,
  "settings": {
    "title": "Your Heading Text",
    "header_size": "h1",
    "align": "center",
    "title_color": "#000000",
    "typography_typography": "custom",
    "typography_font_family": "Manrope",
    "typography_font_size": {"unit": "px", "size": 52, "sizes": []},
    "typography_font_size_tablet": {"unit": "px", "size": 42, "sizes": []},
    "typography_font_size_mobile": {"unit": "px", "size": 38, "sizes": []},
    "typography_font_weight": "800",
    "typography_line_height": {"unit": "em", "size": 1.1, "sizes": []},
    "typography_letter_spacing": {"unit": "px", "size": -2, "sizes": []},
    "typography_text_transform": "uppercase",
    "_margin": {"unit": "px", "top": "-9", "right": "0", "bottom": "-8", "left": "0", "isLinked": false}
  },
  "elements": []
}
```

### Button

```json
{
  "id": "button01",
  "elType": "widget",
  "widgetType": "button",
  "isInner": false,
  "settings": {
    "text": "Learn More",
    "link": {"url": "#", "is_external": "", "nofollow": "", "custom_attributes": ""},
    "align": "left",
    "icon_indent": {"unit": "px", "size": 0, "sizes": []},
    "typography_typography": "custom",
    "typography_font_family": "Manrope",
    "typography_font_size": {"unit": "px", "size": 15, "sizes": []},
    "typography_font_weight": "800",
    "typography_line_height": {"unit": "em", "size": 1, "sizes": []},
    "button_text_color": "#FFFFFF",
    "background_color": "#000000",
    "button_background_hover_color": "#9F9F9F",
    "button_hover_border_color": "#9F9F9F",
    "border_border": "solid",
    "border_width": {"unit": "px", "top": "1", "right": "1", "bottom": "1", "left": "1", "isLinked": true},
    "border_color": "#000000",
    "border_radius": {"unit": "px", "top": "0", "right": "0", "bottom": "0", "left": "0", "isLinked": true},
    "text_padding": {"unit": "px", "top": "20", "right": "40", "bottom": "20", "left": "40", "isLinked": false}
  },
  "elements": []
}
```

### Image

```json
{
  "id": "image01",
  "elType": "widget",
  "widgetType": "image",
  "isInner": false,
  "settings": {
    "image": {"id": 30, "url": "https://example.com/image.png", "alt": "", "source": "library"},
    "image_size": "custom",
    "image_custom_dimension": {"width": "310", "height": "525"},
    "align": "center",
    "link_to": "custom",
    "link": {"url": "#", "is_external": "", "nofollow": "", "custom_attributes": ""},
    "width": {"unit": "%", "size": 100, "sizes": []},
    "width_mobile": {"unit": "%", "size": 100, "sizes": []},
    "_element_width_mobile": "auto",
    "_animation": "fadeIn",
    "animation_duration": "fast",
    "_animation_delay": 500
  },
  "elements": []
}
```

### Text Editor

```json
{
  "id": "text01",
  "elType": "widget",
  "widgetType": "text-editor",
  "isInner": false,
  "settings": {
    "editor": "<p>Your paragraph content here with <strong>formatting</strong>.</p>",
    "align": "left",
    "text_color": "#9F9F9F",
    "typography_typography": "custom",
    "typography_font_family": "Manrope",
    "typography_font_size": {"unit": "px", "size": 17, "sizes": []},
    "typography_font_weight": "500",
    "typography_line_height": {"unit": "em", "size": 1.6, "sizes": []}
  },
  "elements": []
}
```

### Icon

```json
{
  "id": "icon01",
  "elType": "widget",
  "widgetType": "icon",
  "isInner": false,
  "settings": {
    "selected_icon": {"value": "fas fa-star", "library": "fa-solid"},
    "align": "center",
    "primary_color": "#000000",
    "secondary_color": "#FFFFFF",
    "size": {"unit": "px", "size": 40, "sizes": []},
    "rotate": {"unit": "deg", "size": 0, "sizes": []},
    "icon_padding": {"unit": "px", "size": 15, "sizes": []},
    "border_radius": {"unit": "px", "size": 50, "sizes": []}
  },
  "elements": []
}
```

### Icon Box

```json
{
  "id": "iconbox01",
  "elType": "widget",
  "widgetType": "icon-box",
  "isInner": false,
  "settings": {
    "selected_icon": {"value": "fas fa-check", "library": "fa-solid"},
    "title_text": "Feature Title",
    "description_text": "Feature description goes here.",
    "position": "left",
    "title_size": "h3",
    "primary_color": "#000000",
    "icon_space": {"unit": "px", "size": 20, "sizes": []},
    "title_color": "#000000",
    "description_color": "#9F9F9F",
    "title_typography_typography": "custom",
    "title_typography_font_family": "Manrope",
    "title_typography_font_weight": "700"
  },
  "elements": []
}
```

### Divider

```json
{
  "id": "divider01",
  "elType": "widget",
  "widgetType": "divider",
  "isInner": false,
  "settings": {
    "style": "solid",
    "weight": {"unit": "px", "size": 1, "sizes": []},
    "color": "#E5E5E5",
    "width": {"unit": "%", "size": 100, "sizes": []},
    "align": "center",
    "gap": {"unit": "px", "size": 20, "sizes": []}
  },
  "elements": []
}
```

### Social Icons

```json
{
  "id": "social01",
  "elType": "widget",
  "widgetType": "social-icons",
  "isInner": false,
  "settings": {
    "social_icon_list": [
      {"_id": "fb", "social_icon": {"value": "fab fa-facebook-f", "library": "fa-brands"}, "link": {"url": "#"}},
      {"_id": "tw", "social_icon": {"value": "fab fa-twitter", "library": "fa-brands"}, "link": {"url": "#"}},
      {"_id": "ig", "social_icon": {"value": "fab fa-instagram", "library": "fa-brands"}, "link": {"url": "#"}},
      {"_id": "li", "social_icon": {"value": "fab fa-linkedin-in", "library": "fa-brands"}, "link": {"url": "#"}}
    ],
    "shape": "rounded",
    "icon_color": "custom",
    "icon_primary_color": "#FFFFFF",
    "icon_secondary_color": "#000000",
    "icon_size": {"unit": "px", "size": 14, "sizes": []},
    "icon_padding": {"unit": "em", "size": 0.8, "sizes": []},
    "icon_spacing": {"unit": "px", "size": 10, "sizes": []}
  },
  "elements": []
}
```

### Icon List

```json
{
  "id": "iconlist01",
  "elType": "widget",
  "widgetType": "icon-list",
  "isInner": false,
  "settings": {
    "icon_list": [
      {"_id": "item1", "text": "First item", "selected_icon": {"value": "fas fa-check", "library": "fa-solid"}, "link": {"url": "#"}},
      {"_id": "item2", "text": "Second item", "selected_icon": {"value": "fas fa-check", "library": "fa-solid"}, "link": {"url": "#"}},
      {"_id": "item3", "text": "Third item", "selected_icon": {"value": "fas fa-check", "library": "fa-solid"}, "link": {"url": "#"}}
    ],
    "view": "traditional",
    "icon_color": "#000000",
    "icon_color_hover": "#9F9F9F",
    "text_color": "#000000",
    "text_color_hover": "#9F9F9F",
    "text_indent": {"unit": "px", "size": 10, "sizes": []},
    "icon_size": {"unit": "px", "size": 14, "sizes": []},
    "space_between": {"unit": "px", "size": 15, "sizes": []}
  },
  "elements": []
}
```

## Animations

Add animations to any element:

```json
{
  "settings": {
    "_animation": "fadeIn",
    "animation_duration": "fast",
    "_animation_delay": 500
  }
}
```

Or on containers:
```json
{
  "settings": {
    "animation": "fadeIn",
    "animation_duration": "fast",
    "animation_delay": 750
  }
}
```

Animation types: `fadeIn`, `fadeInUp`, `fadeInDown`, `fadeInLeft`, `fadeInRight`, `zoomIn`, `bounceIn`, `slideInUp`, `slideInDown`

Duration: `slow`, `normal`, `fast`

## Color Palette (from templates)

```
Primary Text:     #000000
Secondary Text:   #9F9F9F
Background Light: #F5F5F5
Background White: #FFFFFF
Accent:           #ECC5C5 (or your brand color)
```

## Typography Pattern

```json
{
  "typography_typography": "custom",
  "typography_font_family": "Manrope",
  "typography_font_size": {"unit": "px", "size": 17, "sizes": []},
  "typography_font_weight": "500",
  "typography_line_height": {"unit": "em", "size": 1.6, "sizes": []},
  "typography_letter_spacing": {"unit": "px", "size": 0, "sizes": []},
  "typography_text_transform": "none"
}
```

Font weights: `300`, `400`, `500`, `600`, `700`, `800`, `900`

## ID Generation

Generate 8-character alphanumeric IDs:
```javascript
const id = Math.random().toString(16).slice(2, 10);
```

## Template Reference

See `/templates` directory for 3000+ production templates:
- `c1.json` to `c3120.json` - Section containers

Each template follows the same structure and can be used as reference for specific layouts.

## Import Methods

1. **WordPress Import**: Templates > Saved Templates > Import Templates
2. **Copy/Paste**: In Elementor editor, right-click > Paste from Clipboard
3. **REST API**: POST to `/wp-json/elementor/v1/template-library/templates`

## Best Practices

1. Use containers with `isInner: false` for outer wrappers
2. Use containers with `isInner: true` for nested layouts
3. Always include responsive variants (`_tablet`, `_mobile`)
4. Use negative margins for typography optical alignment
5. Keep consistent padding patterns (120/80/60 for desktop/tablet/mobile)
6. Use `_title` setting to name containers for editor clarity
