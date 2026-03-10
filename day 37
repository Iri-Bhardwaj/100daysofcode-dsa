typedef struct {
    int* heap;
    int size;
    int capacity;
} KthLargest;

void swap(int* a, int* b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

void minHeapify(int* heap, int idx, int size) {
    int smallest = idx;
    int left = 2 * idx + 1;
    int right = 2 * idx + 2;

    if (left < size && heap[left] < heap[smallest])
        smallest = left;
    if (right < size && heap[right] < heap[smallest])
        smallest = right;

    if (smallest != idx) {
        swap(&heap[idx], &heap[smallest]);
        minHeapify(heap, smallest, size);
    }
}

void heapPush(KthLargest* obj, int val) {
    obj->heap[obj->size] = val;
    int curr = obj->size;
    obj->size++;

    while (curr > 0 && obj->heap[(curr - 1) / 2] > obj->heap[curr]) {
        swap(&obj->heap[curr], &obj->heap[(curr - 1) / 2]);
        curr = (curr - 1) / 2;
    }
}

void heapPop(KthLargest* obj) {
    obj->heap[0] = obj->heap[obj->size - 1];
    obj->size--;
    minHeapify(obj->heap, 0, obj->size);
}

int kthLargestAdd(KthLargest* obj, int val) {
    if (obj->size < obj->capacity) {
        heapPush(obj, val);
    } else if (val > obj->heap[0]) {
        heapPop(obj);
        heapPush(obj, val);
    }
    return obj->heap[0];
}

KthLargest* kthLargestCreate(int k, int* nums, int numsSize) {
    KthLargest* obj = (KthLargest*)malloc(sizeof(KthLargest));
    obj->heap = (int*)malloc(k * sizeof(int));
    obj->size = 0;
    obj->capacity = k;

    for (int i = 0; i < numsSize; i++) {
        kthLargestAdd(obj, nums[i]);
    }
    return obj;
}

void kthLargestFree(KthLargest* obj) {
    free(obj->heap);
    free(obj);
}
