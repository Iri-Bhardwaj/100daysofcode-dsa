#include <stdio.h>
#include <stdlib.h>

#define MAX 100000

int main() {
    int n;
    scanf("%d", &n);

    int arr[n];
    for (int i = 0; i < n; i++)
        scanf("%d", &arr[i]);

    // Hash map for prefix sums
    int *freq = (int *)calloc(2 * MAX + 1, sizeof(int));
    int offset = MAX;

    int prefix_sum = 0;
    long long count = 0;

    // Prefix sum = 0 initially occurs once
    freq[offset] = 1;

    for (int i = 0; i < n; i++) {
        prefix_sum += arr[i];

        // If this prefix sum was seen before,
        // then subarrays with sum zero exist
        count += freq[prefix_sum + offset];

        // Increase frequency
        freq[prefix_sum + offset]++;
    }

    printf("%lld\n", count);

    free(freq);
    return 0;
}
