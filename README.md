# Reverse a linked list

```typescript
type LinkedList = {
  value: number;
  next: LinkedList | null;
};

// input
const list = {
  value: 6,
  next: {
    value: 10,
    next: {
      value: 12,
      next: {
        value: 3,
        next: null
      }
    }
  }
};

const reverse = (
  currentElement: LinkedList,
  previousElement: LinkedList
): LinkedList => {
  const reversedElement = {
    value: currentElement.value,
    next: previousElement
  };

  if (currentElement.next) {
    return reverse(currentElement.next, reversedElement);
  } else {
    return reversedElement;
  }
};

const reverseLinkedList = (linkedList: LinkedList): LinkedList => {
  return reverse(linkedList, null);
};

const result = reverseLinkedList(list)
console.log("result: ", result);


/*
output: 

const list = {
  value: 3,
  next: {
    value: 12,
    next: {
      value: 10,
      next: {
        value: 6,
        next: null
      }
    }
  }
}
*/
```
