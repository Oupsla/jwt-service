# API
<a name="default"></a>

## default ⇒ <code>Promise.&lt;Object&gt;</code>
Instantiate the JWT service

**Kind**: global variable  
**Returns**: <code>Promise.&lt;Object&gt;</code> - A promise of the jwt service  

| Param | Type | Description |
| --- | --- | --- |
| services | <code>Object</code> | The services to inject |
| services.JWT | <code>function</code> | The JWT service configuration object |
| [services.log] | <code>function</code> | A logging function |
| [services.time] | <code>function</code> | A function returning the current timestamp |

**Example**  
```js
import initJWTService from 'jwt-service';

const jwt = await initJWTService({
  JWT: {
    secret: 'secret',
    duration: '2d',
    tolerance: '2h',
    algorithms: ['HS256'],
  },
  log: console.log.bind(console),
  time: Date.now.bind(Date),
});

const token = await jwt.sign({ my: 'payload' });
```
