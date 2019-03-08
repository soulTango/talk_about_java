**直接排序**

实现过程：（假设是升序排序）第一次循环把最小的值放在第一位，第二次把次小的值放在第二位，以此操作直到还剩最后一个数。外循环就是前面所说的第一次，第二次...直到还剩最后一个数，内循环实现交换，最小值，次小值...依次放到对应的位置。

代码如下：

 private static int[] directSort(int[] arr) {

        int length = arr.length;
        int temp;
        int minIndexNow; //目前最小值的下标
        int minNow; //目前最小值的值
        for (int i = 0; i < length-1; i++){
            minIndexNow = i;
            minNow = arr[i];
            for (int j = i+1; j < length; j++){
                if(minNow > arr[j]){
                    minIndexNow = j;
                    minNow = arr[j];
                }
            }
            //代码块，交换此时的最小值
            {
                temp = arr[minIndexNow];
                arr[minIndexNow] = arr[i];
                arr[i] = temp;
            }

        }
        return arr;
    }