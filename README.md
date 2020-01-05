# Memory Manager
A custom memory manager designed specifically for game engines. It's architecture consists of three Fixed Size Allocators and a Heap Manager. This project also includes a comprehensive Unit Test to test allocations done by the Memory System as a cohesive unit.

The Fixed Size Allocators get memory from the Heap Manager but manage it independently. They use a BitArray class to do so, which is basically to be treated as an array of bits, indicating the blocks available for allocation within the allocator. This class also provides methods to set the bits and to find the first set bit. Using BitArrays is beneficial because it allows for all allocations and frees to be done in O(1), giving a performance boost which game engines strive for. 

The Heap Manager on the other hand provides the standard alloc and free methods, by using two Doubly Linked Lists of inline Block Descriptors. It also provides a garbage collection method that can also consolidate fragmented memory. This was achieved by adding a boolean to the Block Descriptor to check for garbage collection.

This was an assignment for the course 'C++ Game Programming' in my master's program, which was completed within 24 hours.
