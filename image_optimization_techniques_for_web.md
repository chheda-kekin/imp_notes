# Image Optimization Techniques

## Loading images lazily

Loading images only when they're coming into viewport/displayed.

e.g.

```html
<img src="myimg.jpg" height="130px" width="140px" loading="lazy" />
```

Corresponding JSX would be,

```jsx
    function App() {
        return (
            <>
                <div>
                    <img src="myimg.jpg" height="130px" width="140px" loading="lazy" />
                </div>
            </>
        )
    }
```

## Using responsive images:
Using different image sizes based on user's screen size & resolution.

## Using WebP & AVIF format
Use WebP & AVIF format which provides better compression & quality. However always have fallback options of jpeg & gif format.