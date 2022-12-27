# Plus Minus
## Given an array of integers, calculate the ratios of its elements that are positive, negative, and zero. Print the decimal value of each fraction on a new line with  places after the decimal.

To solve this problem I looped through the given array, and for each item in the array evaluated if the the value was greater than zero or less than zero. Then, added one to a integer that represented wether the value was positive, negative or zero. After looping through the array, to print the values in javaScript I used console log.

```
function plusMinus(arr) {
    // Write your code here
    let pos = 0
    let neg = 0
    let zer = 0
    for(let i=0;i<arr.length;i++){
        if(arr[i]>0){
            pos++
        } else if(arr[i]<0){
            neg++
        } else{
            zer++
        }
    }
    console.log((pos/arr.length).toPrecision(6))
    console.log((neg/arr.length).toPrecision(6))
    console.log((zer/arr.length).toPrecision(6))
}
```