# Blog
一、排序
##   1、插入排序

``` c#
   static void InsertSort(int[] dataArray)
   {
      {
        int iValue = dataArray[i];       //保存拿出来进行比较的值
        bool isInsert = false;           //判断是否插入
        for(int j=i-1,j>=o,j--)          //以J的for的循环作为界限，往前循环作为一个新的数组                             
          {                              //反向遍历，依次用J的下一个数与新数组挨个比较
            if(dataArray[j] > iValue)
            {
              dataArray[j+1] = dataArray[j];
            }
            else
            {
              dataArray[j+1] = iValue;
              isInsert = true;
              break;
            }
          }
          if(!isInsert)
          {
            dataArray[0] = iValue;     
          }        
      }
   }
   
```

## 2、简单选择排序

``` c#
static void SelectSort(int[] dataArray)
{
  for (int i=0,i<dataArray.Length-1,i++)
  {
    int min = dataArray[i];
    int minIndex = i;
    for (int j=i+1,j<dataArray.Length,j++)  //第一次循环，求的数组中的最小值
    {
      if(dataArray[j]<min)
      {
        min = dataArray[j];
        minIndex = j;
      }
    }
    if(minIndex != i)                        //第一次循环，如果第一个数不是最小值
    {
      int temp =dataArray[i];                //位置互换，接下来的循环从第二个数开始
      dataArray[i] = dataArray[minIndex];    //依此类推
      dataArray[minIndex] = temp;
    }
  }
}
```

## 3、快速排序

``` c#
//对数组dataArray中索引从left到right之间的数做排序
static void QuickSort(int[] dataArray, int left, int right)
{
  if(left < right)
  {
    int x = dataArray[left]; //基准数，把比他小或者等于他的放在他的左边，然后把比他大的放在他的右边
    int i = left;
    int j = right; //用来做循环的标志位
                    
    while(true && i<j) //当 i == j的时候，说明找到了一个中间位置，这个中间位置就是基准数应该在的位置
    {       
    //从后往前比较（从右向左比较）找一个比X小（或者=）的数字，放在我们的坑里，坑位于 i 的位置
     while (true && i<j)
      {
        if(dataArray[j] <= x)
        {
          dataArray[i] = dataArray[j];
          break;
        }
        else
        {
          j--; //向左移动到下一个数字，然后做比较
        }
       }
        //从前往后（从左向右）找一个比X大的数字，放在我们的坑里 现在的坑位于 j 的位置
     while(true && i<j)
      {
       if(dataArray[i] > x)
        {
          dataArray[j] = dataArray[i];
          break;
        }
      else
        {
           i++;
        }
      }
    }  
    //跳出循环 现在 i==j ，i 是中间位置
    dataArray[i] = x;  //left - i - right 
    QuickSort(dataArray, left , i-1);
    QuickSort(dataArray, i+1 , right);
  }
}

