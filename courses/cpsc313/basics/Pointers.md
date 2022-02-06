# Pointers

## Operators
- `*` = dereference operator
- `&` = address of operator
```C
// Initialize pointer
int x = 10;
int* p = &x; // pointer p contains the address of x in memory
*p = 20; // value of x set to 20
```

## Segmentation Faults
Occurs when you access memory that you are not supposed to.
```C
// Dereferencing an uninitialized pointer
char* p = NULL;
*p = 'a'; // SEG FAULT!
```

## Dangling Pointers
When a pointer points to something that no longer exists.
```C
char* p = NULL;

{ // local scope
	char c;
	p = &c;
}

// c does not exist anymore outside the parentheses
*p = 'a'; // SEG FAULT!
```

## Memory Leak
When you allocate memory on the heap, but do not deallocate it = wasted memory.
```C
int* ptr = (int*) malloc(sizeof(int)) // allocate memory on heap
*ptr = 10;
return 0; // return without free'ing ptr; should call free(ptr) before returning
```