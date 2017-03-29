# Blog
##一、排序
##   1、插入排序
-   static void InsertSort(int[] dataArray)
-   {
-    for(int i=0,i<dataArray.Length,i++)
-      {
-        int iValue = dataArray[i];
-        bool isInsert = false;
-        for(int j=i-1,j>=o,j--)
-          {
-            if(dataArray[j] > iValue)
-            {
-              dataArray[j+1] = dataArray[j];
-            }
-            else
-            {
-              dataArray[j+1] = iValue;
-              isInsert = true;
-              break;
-            }
-          }
-          if(!isInsert)
-          {
-            dataArray[0] = iValue;
-          }
-      }
-   }
