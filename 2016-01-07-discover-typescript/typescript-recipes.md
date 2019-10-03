# Typescript recipes

### Add any properties to an interface

By default, interfaces not allows other properties that those specified. 

You can however allow custom properties by using the  \[key: string\]: any; in an interface

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

Extendable interface 

```typescript
interface PostExtended extends Post {
    [key: string]: any;  
}
```



