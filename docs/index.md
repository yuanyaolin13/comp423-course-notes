# Welcome to Yuanyao's Course Notes

This is my home page. I will use it to organize and share my course notes.

## TEST
``` py linenums="1"
def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
```