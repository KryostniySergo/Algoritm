
``` Python
def binarySearch(sortedArray: list[int], target: int):
    low = 0
    high = len(sortedArray) - 1
    
    while low <= high:
        # Формула middle элемента сортированного массива
        middle = low + (high - low) // 2
        middle_item = sortedArray[middle]
        print(f"middle: {middle_item}")

        if middle_item < target:
            low = middle + 1
        elif middle_item > target:
            high = middle - 1
        else:
            # target found
            return middle_item
    # target not found
    return None

  
test1: list[int] = [1,2,3,4,5]
test2: list[int] = [i for i in range(0, 10000)]
target: int = 621
print(binarySearch(test2, target))
```

# Главная формула
##### Формула middle элемента сортированного массива
```Python
middle = low + (high - low) // 2
```
При 
```Python
low = 0
high = len(sortedArray) - 1
```


---


![[Pasted image 20241130022910.png]]

```Python
def binarySearch(sortedArray: list[int], target: int):
    low = 0
    high = len(sortedArray) - 1

    while low <= high:
        # Формула middle элемента сортированного массива
        middle = low + (high - low) // 2
        left_item = sortedArray[middle]
        right_item = sortedArray[middle + 1]
        
        if left_item > right_item:
            return [left_item, right_item]
        else:
            high = middle - 1
    # target not found
    return None

test: list[int] = [6, 7, 1, 2, 3, 4, 5]
target: int = 621

print(binarySearch(test, target))
```
