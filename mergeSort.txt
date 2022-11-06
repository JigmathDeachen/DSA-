public class mergeSort {
    static void sort(int arr[],int start,int end)
    {
        if(start>=end)
        {
            return;
        }
            int mid=(start+end)/2;
            sort(arr,start,mid);
            sort(arr,mid+1,end);
             merge(arr,start,end);
    }
    static void merge(int arr[],int start,int end)
    {
        int mid=(start+end)/2;
        // length of  sub array
        int len1=mid-start+1;
        int len2=end-mid;
        // create arrys
        int []first =new int[len1];
        int []second=new int[len2];
        int k=start;
        for(int i=0;i<len1;i++)
        {
            first[i]=arr[k++];
        }
        k=mid+1;
        for(int i=0;i<len2;i++) {
            second[i] = arr[k++];
        }
        // merge two sub arrays
        int index1=0;
        int index2=0;
        k=start;
        while(index1<len1 && index2<len2)
        {
            if(first[index1]< second[index2])
            {
                arr[k++]=first[index1++];
            }
            else
            {
                arr[k++]=second[index2++];
            }
        }
        while(index1<len1)
        {
            arr[k++]=first[index1++];
        }
        while(index2<len2)
        {
            arr[k++]=second[index2++];
        }
    }
    public static void main(String[] args) {
        int arr[]={3,2,1,5,4,7,6};


       sort(arr,0,arr.length-1);
        for(int i=0; i<arr.length;i++)
        {
            System.out.print(arr[i]+" ");
        }
    }
}
