# Typescript recipes

### Add any properties to an interface

By default, interfaces not allows other properties that those specified. 

You can however allow custom properties by using the  \[key: string\]: any; in an interface

### Dynamic property name

```typescript
interface Post {
    title: string; 
    visible: boolean; 
    // Allows any type
    [key: string]: any; 
}
```

You can also extend an existing interface 

Original interface

```typescript
interface Post {
    title: string; 
    visible: boolean; 
}
```

### Extend interface

```typescript
interface PostExtended extends Post {
    [key: string]: any;  
}
```

### Override interface

You can also override an interface by replacing the way a given prop is defined

```typescript
export interface TdProjectDisplay extends Omit { code: string; }
```

### Ask typescript to ignore an error

```typescript
let text: string
// the following error will be ignored! 
// @ts-ignore 
text = 2;
```

