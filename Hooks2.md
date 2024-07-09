We will cover 30 hooks

# Level 1

Must to Know

1. useState
2. useEffect
3. useContext

### useState()

1. Importing Hooks:

When importing a hook from React, you use destructuring to access the specific hook you need. For example:

```javascript

import { useState } from 'react';

```

2. Usage Restrictions:

- Hooks can only be used inside functional components. They cannot be used in class components because class components have a different way of managing state and lifecycle methods.
- Hooks must be called at the top level of a functional component. This means you cannot call hooks inside loops, conditionals (if statements), or nested functions. They must be used in the same order on every render to ensure consistent behavior.otherwise it will show error.
- Why These Rules Matter:-
- Consistent Order of Hooks: React relies on the order of hooks to match up with their previous renders. Changing the order (e.g., by placing them inside conditions) can lead to bugs.
- Top-Level Calls: Ensuring hooks are called at the top level of your component keeps the logic predictable and avoids issues with state and effect dependencies.
- 


```javascript
import React,{useState} from "react";

function App(){
return (
<button>-</button>
<span>0<span>
<button>+</button>
)
}
```
































