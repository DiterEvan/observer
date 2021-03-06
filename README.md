# Observerjs

An easy way to **Parent - Iframe Child** communication

## Instalación

```
npm install --save observerjs
```

## Usage

**Include module:**

```javascript
// import
import Observer from 'observerjs';

// create object
const observer = new Observer();

```

**In parent:**

```javascript
// Subscribe to events from iframe child
observer.suscribe('close', () => { app.close(); });

// Emit events to iframe child
Observer.emit('init', '*', iframe.contentWindow);
Observer.emit('open', '*', iframe.contentWindow);

```

**In iframe child:**

```javascript
// Suscribe to events from parent
observer.suscribe('init', () => { app.init(); });
observer.suscribe('open', () => { app.open(); });

// Emit events to parent
Observer.emit('close', '*', window.parent);

```
