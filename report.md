# Report
# Report on malloc implementation

## Introduction

This report discusses the implementation of malloc, a dynamic memory allocator. The malloc implementation uses an explicit free list, fence posts, and constant time coalescing.

## Explicit free list

The explicit free list is implemented using a linked list. The head of the linked list points to the first free block. Each free block in the linked list has a size and a pointer to the next free block.

## Fence posts

Fence posts are implemented by adding a small amount of memory after each allocated block. This amount of memory is equal to the size of the `struct free_block` structure.

## Constant time coalescing

The constant time coalescing is implemented by merging adjacent free blocks of memory into larger free blocks. This is done by traversing the linked list of free blocks and merging any blocks that are adjacent to each other.

## Optimizations

The following optimizations have been attempted in the malloc implementation:

* Using a linked list to store the free blocks of memory allows for quick and efficient searching for a free block that is large enough to satisfy a memory allocation request.
* Adding a fence post after each allocated block prevents the allocated blocks from being coalesced together. This can help to prevent fragmentation in the heap.
* Merging adjacent free blocks of memory into larger free blocks can help to improve the efficiency of the memory allocator.

## Garbage collector

A garbage collector was not implemented in this malloc implementation. A garbage collector is a system that automatically frees memory that is no longer being used. This can be helpful in preventing memory leaks. However, garbage collectors can also be complex and inefficient.

## Implementation challenges

Two implementation challenges that were encountered in the malloc implementation are:

* Keeping track of the free blocks of memory. This can be challenging, especially if the heap is large and there are many free blocks.
* Merging adjacent free blocks of memory. This can be tricky, especially if the free blocks are not contiguous.

## Testing and benchmarking

Two key observations from testing and benchmarking the malloc implementation are:

* The explicit free list implementation is efficient for small and medium-sized heaps. However, it can be inefficient for large heaps.
* The constant time coalescing implementation can improve the efficiency of the memory allocator. However, it can also be more complex to implement.

No major bugs were encountered in the malloc implementation. However, some minor changes were made to the implementation after testing and benchmarking. For example, the way that the free blocks are stored in the linked list was changed to improve the efficiency of the memory allocator.

## Conclusion

The malloc implementation presented in this report uses an explicit free list, fence posts, and constant time coalescing. The implementation has been optimized for small and medium-sized heaps. However, it can be inefficient for large heaps. Future work could explore more efficient ways to implement the malloc algorithm for large heaps.

<!-- You should write your report in this file. Remember to check that it's 
     formatted correctly in the pdf produced by the CI! -->
