# Study Guide
## Data Structures
### Set
### List
### Map
- use hashmap

### Linked List
### Array List
### stack
### queue
### hash-set
- no dupes

### hash-map
- yay dupes
 
### binary tree
### heap
- binary tree where if a is a parent of b then the key of a is ordered in respect to the key of b

### graph
- finite set of vertices or nodes with connections

### red-black tree
## Sorting
### insertion sort
1. for i ← 1 to length(A)-1
    j ← i
    while j > 0 and A[j-1] > A[j]
        swap A[j] and A[j-1]
        j ← j - 1
    end while
end for
- Stable
- O(1) extra space
- O(n2) comparisons and swaps
- Adaptive: O(n) time when nearly sorted
- Very low overhead

### radix-sort
1. create queue for each digit 0-9
2. for each number in array to sort enqueue number in queue matching the significant digit
3. re-create the array by dequeueing each number in each of the queues in order
4. repeat on next significant digit
- stable
- can be O(n) if numbers represented in base n
- O(wn) w is word size usually at least O(n log(n))

### quick-sort
1. find upper and lower indicies, then take middle element as pivot to sort around
2. i, j are lower, higher indicies
3. while i <= j {while array[i] < pivot increment and while array[j] greater than pivot decrement to find elements that need to be swapped}
4. if i<=j swap elements array[i] and array[j] then increment i and decrement j
5. call quicksort from lower to j and if lower < j and from i to higher if i < higher
- Not stable
- O(lg(n)) extra space (see discussion)
- O(n2) time, but typically O(n·lg(n)) time
- Not adaptive

### merge-sort
1. check if array size = 1 if so return that array is sorted
2. if not find middle and call sort recursively on upper and lower half
3. call merge function on upper and lower parts
4. create array working copy
5. for (int i = lowerIndex; i <= higherIndex; i++) {
            tempMergArr[i] = array[i];
        }
        int i = lowerIndex;
        int j = middle + 1;
        int k = lowerIndex;
        while (i <= middle && j <= higherIndex) {
            if (tempMergArr[i] <= tempMergArr[j]) {
                array[k] = tempMergArr[i];
                i++;
            } else {
                array[k] = tempMergArr[j];
                j++;
            }
            k++;
        }
        while (i <= middle) {
            array[k] = tempMergArr[i];
            k++;
            i++;
        }

- Stable
- Θ(n) extra space for arrays (as shown)
- Θ(lg(n)) extra space for linked lists
- O(n·lg(n)) time
- Not adaptive
- Does not require random access to data

### heap-sort
1. heapify by running maxHeap from array midpoint to 0
2. in heapify left = 2*index, right = 2*index+1, maxIndex =index
3. if left is less than max index and arr[left] > arr[index] maxIndex = left; if right is less than max index and arr[right] > arr[maxINdex] maxIndex = right;
4. if maxIndex is not index swap maxIndex and index; maxHeap on array at maxIndex (where old index has been swapped to)
- Not stable
- O(1) extra space (see discussion)
- O(n·lg(n)) time
- Not really adaptive

## Algorithms
### Sorting
### divide-and-conquer
### greedy
### recursion
### binary search
1. set upper and lower bounds of the array
2. if lower is greater than upper stop as unsuccessful
3. find midpoint
4. if target is less than midpoint then midpoint+1 is new upper
5. if target is greater than midpoint then midpoint-1 is new lower
- O(log(n))

### Dijikstra
1. Make distance on every node infinite
2. Root distance = 0 and current = root
3. Set all nodes but root to visited = false
4. Create a *SET* of all the nodes with visited=false
5. for current node check distance of all unvisited neighbors
6. Calculate tentative distance to neighbor and if it's smaller than its current distance replace it
7. mark current node visited and remove it from unvisited set
8. if destination visited or all nodes in unvisited set have tentative distance of infinite return
9. set unvisited node with smallest tentative distance as current and repeat

### A*


## Graphs
### Objects & Pointers
### matrix
### adjacency list
### breadth-first
1. queue first element
2. while queue not empty dequeue element, perform operations, enqueue descendants

### depth first
1. stop cond if (null) return
2. dfs(node.left); dfs(node.right); print(node);

## OS
### Lock
1. lock lock
2. lock.lock()
3. lock.unlock()

### Synchronized
1. First, it is not possible for two invocations of synchronized methods on the same object to interleave. When one thread is executing a synchronized method for an object, all other threads that invoke synchronized methods for the same object block (suspend execution) until the first thread is done with the object.
2. Second, when a synchronized method exits, it automatically establishes a happens-before relationship with any subsequent invocation of a synchronized method for the same object. This guarantees that changes to the state of the object are visible to all threads.

### Mutex
1. thread locks a resource that can only be unlocked by that thread

### Semaphore
1. semaphore = new Semaphore(maxConcurrentRequests);
2. semaphore.acquire();
3. finally {
           semaphore.release();
}
4. access control structure allows x number of concurrent requests in process

### Deadlock
1. threads are blocked because 2 competing processes are waiting for the other to finish

### Livelock
1. threads not able to make progress but are not blocked
2. threads keep changing states responding to each other

### Starvation
1. When thread of lower priority never acquires lock because threads of higher priority continue to get it

## Bit Manipulation
1. 1 << 1 shift bit left (first operand is what to perform operation on 2nd is the number of places to shift
2. 0xFFFFFFF0 >> 4 shift bit right (signed meaning the bit it will move in on shifts is same as the most significant bit. For unsigned (always 0) use >>>
3. unary complement ~
4. bitwise and &
5. bitwise exclusive or ^
6. bitwise inclusive or |
7. Integer.parseInt(bitString, base)


java.util.Arrays.binarySearch(int[] a, int key)
java.util.Arrays.sort(int[])

