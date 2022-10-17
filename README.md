# quinoa-vite

Example with Quinoa, Vite and Vue that triggers
```
ERROR [io.ver.cor.net.imp.ConnectionBase] (vert.x-eventloop-thread-1) Invalid object PooledUnsafeDirectByteBuf(freed)
```

because it lacks the hmr-part in vite.config.js. The correct config is: 

```javascript
import {defineConfig} from 'vite'
import react from '@vitejs/plugin-react'

// https://vitejs.dev/config/
export default defineConfig({
    plugins: [react()],
    server: {
        hmr: {
            port: 5173
        }
    }
})

```

```
mvn clean compile quarkus:dev
```


