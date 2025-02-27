- pass new argument in the `getSeriesTagValues` function as `isArchival`
- pass this to the `processSeriesTagValues` function
- this function will then call the `getSeriesDataValues` from `dataMapperUtil`
- This `dataMapperUtil` `getSeriesDataValues` will then call the `getSeriesDataResponse` function
- this function will then do the final checking
![[Pasted image 20250227165607.png]]