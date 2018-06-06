```
//二分查找，递归实现。
function binarySearch(target,arr) {
    var start= 0;
    var end=arr.length-1;

    var mid = parseInt(start+(end-start)/2);
    if(target==arr[mid]){
        return mid;
    }else if(target>arr[mid]){
        return binarySearch(target,arr,mid+1,end);
    }else{
        return binarySearch(target,arr,start,mid-1);
    }
    return -1;
}
```

```
//不使用递归实现
function binarySearch(target,arr) {
    var start   = 0;
    var end     = arr.length-1;

    while (start<=end){
        var mid = parseInt(start+(end-start)/2);
        if(target==arr[mid]){
            return mid;
        }else if(target>arr[mid]){
            start= mid+1;
        }else{
            end= mid-1;
        }
    }
    return -1;
}
```



