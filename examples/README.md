# Three.js Examples

A minimalist Three.js example showcase system with a layout similar to three.js-dev.

## Features

- **Left sidebar with thumbnails**: Display all available examples with preview images
- **Right iframe display area**: Real-time preview of selected examples
- **Search functionality**: Search examples by name or description
- **Responsive design**: Support for mobile devices
- **CDN dependencies**: Use CDN to import Three.js and related libraries, no local dependencies required

## File Structure

```
examples/
├── index.html                    # Main page with left sidebar and right display area
├── webgl_animation_keyframes_laptop.html  # Laptop animation example
├── screenshots.html              # Thumbnail generation tool
├── screenshots/                  # Thumbnail directory (optional)
│   └── webgl_animation_keyframes_laptop.png
└── README.md                     # This file
```

## Usage

1. **Access main page**: Open `index.html`
2. **Select example**: Click on any example thumbnail in the left sidebar
3. **View animation**: The right iframe area will display the selected example
4. **Search examples**: Use the search box at the top to quickly find examples
5. **View source code**: Click the code button in the top right to view source code

## Adding New Examples

### 1. Create Example File

Create a new HTML file in the `examples/` directory, for example `my_example.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>My Example</title>
    <script src="https://cdn.jsdelivr.net/npm/three/build/three.min.js"></script>
    <!-- Other required CDN libraries -->
</head>
<body>
    <div id="container"></div>
    <script>
        // Your Three.js code
    </script>
</body>
</html>
```

### 2. Update index.html

Add the new example to the `examples` object in `index.html`:

```javascript
const examples = {
    'animations': [
        {
            file: 'webgl_animation_keyframes_laptop',
            title: 'Laptop Animation',
            description: 'A 3D laptop model with closing animation and typing effect'
        },
        {
            file: 'my_example',  // New example
            title: 'My Example',
            description: 'Description of my example'
        }
    ]
};
```

### 3. Generate Thumbnail (Optional)

1. Open `screenshots.html`
2. Add a new thumbnail generation function
3. Generate and download the thumbnail
4. Save the thumbnail to the `screenshots/` directory

## Technical Details

- **Layout**: Responsive layout implemented using CSS Grid and Flexbox
- **Theme**: Support for light and dark theme switching
- **Search**: Real-time search with title and description matching
- **iframe**: Use iframe to isolate examples and avoid style conflicts
- **CDN**: Use jsDelivr CDN to load Three.js and related libraries

## Browser Compatibility

- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

## Notes

- Example files should use CDN to import dependencies, avoid local file dependencies
- Thumbnails are recommended to use 400x300 pixel PNG format
- Example files should be able to run independently without external resources
- It is recommended to add appropriate error handling for each example

## Customization

You can customize the theme by modifying CSS variables:

```css
:root {
    --color-blue: #049EF4;        /* Primary color */
    --panel-width: 300px;         /* Left sidebar width */
    --background-color: #fff;     /* Background color */
    --text-color: #444;           /* Text color */
}
``` 