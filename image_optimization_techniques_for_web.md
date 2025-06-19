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

### Use srcSet attribute in React

```jsx
const cardImage = () => {
    return (
        <img 
            src="small-img.jpg"
            srcSet="small-img.jpg 300w, medium-img.jpg 600w, large-img.jpg 900w"
            alt="Responsive image"
        />
    )
}

export default cardImage;
```

## Using WebP & AVIF format
Use WebP & AVIF format which provides better compression & quality. However always have fallback options of jpeg & gif format.

## Using CDNs
You can use CDN to host/cache images where first time request from user served by main server also image transferred to the edge server. Subsequent requests for the same resource are served by edge server closest to the user.


# Context provider pattern

```js #AppContextProvider.js
import { createContext, useState } from "react";

const AppContext =  createContext({
    
});

const AppContextProvider = (props) => {

    const [isAuthenticated, setIsAuthenticated] = useState(false);

    return (
        <AppContext.Provider value={{
            isAuthenticated: isAuthenticated,
            setIsAuthenticated: () => {

            }
        }}>
            { props.children }
        </AppContext.Provider>
    )
}

export default AppContextProvider;
```