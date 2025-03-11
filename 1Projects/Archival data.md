- pass new argument in the `getSeriesTagValues` function as `isArchival`
- pass this to the `processSeriesTagValues` function
- this function will then call the `getSeriesDataValues` from `dataMapperUtil`
- This `dataMapperUtil` `getSeriesDataValues` will then call the `getSeriesDataResponse` function
- this function will then do the final checking
![[Pasted image 20250227165607.png]]
---
## updated requirements
- the archival will not be a new row in the datasourcedef
- instead it will be a new column in the timeseries row

---
## documentation 

```js
getSeriesTagValues(
    tagData,
    callBack,
    mappingId,
    fromDate,
    toDate,
    samplesCount,
    window,
    grouping,
    index,
    params,
    isArchival
  )
```


1. **getSeriesTagValues** (tagData, callBack, mappingId, fromDate, toDate, samplesCount, window, grouping, index, isArchival) - This method accepts:
    
    1. tagData - tagData for which value is required.
        
    2. callBack function - the taglist with mapped values is returned through this callBack method, along with mappingId.
        
    3. mappingId - graphic file name or dashboard template name.
        
    4. fromDate - date from where series data need to be picked.
        
    5. toDate - date till where series data needs to be picked.
        
    6. samplesCount - number of sample data to be given within the range provided.
        
    7. window - this parameter will return messages between untill (current time) minus window. This parameter is expressed in format `PnDTnHnMn.nS` based on [![](https://en.wikipedia.org/static/favicon/wikipedia.ico)ISO 8601](https://en.wikipedia.org/wiki/ISO_8601#Durations)
        
    8. grouping - this parameter will come in conjunction with window. It groups the messages between until minus window in grouping numbers. This too follows window duration format.  
          
        This method returns tagData (tag_source) , value, timestamp.  
        This method supports mapping for Series data. It supports two type of data (one at a time)
        
    9. ==Provided fromDate, toDate, sampleCount - for the given tagData and the message between fromDate minus toDate is grouped to get data aggregated the sampleCount no of data. ex - P2DT4H==
        
    10. Provided window and grouping - for the given tagData, the message between untill minus window is grouped by grouping data. ex- PT12H

    11. Provided a boolean to switch between archival data or series data
          
        **tagData , callBack and mappingId are fixed parameters for both cases.**