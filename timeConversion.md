# Time Conversion
## Given a time in 12 hour AM/PM format, convert it to military (24-hour) time. Note: - 12:00:00AM on a 12-hour clock is 00:00:00 on a 24-hour clock. - 12:00:00PM on a 12-hour clock is 12:00:00 on a 24-hour clock.

To Solve this problem I first evaluated the input string for whether the time given was AM or PM. 

For PM times, if the time starts with "12", the time is exactly the same, and by ommitting the PM at the end of the string the correct answer is obtained. For any other starting value at a PM time, by adding 12 to the hour value, we obtain the correct transformed time.

For AM times, if the time with "12", by replacing the "12" with "00", we obtain the transformed time. Otherwise the time needs no transformation, and by ommiting the AM at the end of the string, we have the correct answer.

```
function timeConversion(s) {
    // Write your code here
    if(s[s.length-2]=='P'){
        if(s.substring(0,2)=="12"){
            return s.substring(0,(s.length-2))
        } else if(s[0]!=0){
            return (s.substring(0,2)*1+12).toString()+s.substring(2,(s.length-2))
        } else {
            return (s.substring(1,2)*1+12).toString()+s.substring(2,(s.length-2))
        }
    } else{
        if(s.substring(0,2)=="12"){
            return "00"+s.substring(2,s.length-2)
        } else {
            return s.substring(0,s.length-2)
        }
    }
}
```