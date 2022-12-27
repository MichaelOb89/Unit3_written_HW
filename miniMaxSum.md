# Mini-Max Sum
## Given five positive integers, find the minimum and maximum values that can be calculated by summing exactly four of the five integers. Then print the respective minimum and maximum values as a single line of two space-separated long integers.

To solve this problem I saved the value of the sum of the whole array in a constant called sum. While looping through the array to calculate the sum I evaluated each item in the array to identify the smallest and largest integers.

I then printed the maximum sum as the sum of all integers, minus the smallest value, and in similar fashion, the minimum sum by removing the greatest value.

```
function miniMaxSum(arr) {
    // Write your code here
    let min = arr[0]
    let max = arr[0]
    let sum = 0
    for(let i=0;i<arr.length;i++){
        if(arr[i]<min){
            min = arr[i]
        }
        if(arr[i]>max){
            max = arr[i]
        }
        sum+=arr[i]
    }
    console.log(sum-max, sum-min)
}
```