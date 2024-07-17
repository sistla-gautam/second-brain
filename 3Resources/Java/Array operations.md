- deletion in the middle
	[https://www.digitalocean.com/community/tutorials/java-remove-array-elements](https://www.digitalocean.com/community/tutorials/java-remove-array-elements)
    - we create a new array of 1 size lesser        
    - we iterate through all values to see if the value exists        
    - if the elements do not match, we transfer over the element to the next array        
    - if the elements match the required value, we do not transfer, and simply go to the next element in the array
        ```java
        int[] arr = new int[]{1,2,3,4,5};
        int[] arr_new = new int[arr.length-1];
        int j=3;
        for(int i=0, k=0;i<arr.length;i++){
            if(arr[i]!=j){
                arr_new[k]=arr[i];
                k++;
            }
        }
        ```